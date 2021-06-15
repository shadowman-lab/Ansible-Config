# Connecting ServiceNow and Ansible Tower


## Connect ServiceNow to Ansible Tower

## Notes
- These instructions assume that there is no MID-Server for ServiceNow, and that the ServiceNow instance and Ansible Tower can talk to each other directly over the public internet.
- This has been tested with:
  - Ansible Tower 3.6, 3.7
  - ServiceNow Orlando Release

- While the mid-server is an outbound connection from on-prem to the customer’s ServiceNow Instance, it subscribes to the “ECC Queue” allowing for bidirectional communication between an on-prem Tower and ServiceNow. Because it is polling, there can be a delay between the initiation of an action and the mid-server processing the request.

- If you create outbound REST messages in ServiceNow you can choose to have that executed directly from the ServiceNow instance or via a mid-server. 

- If you have a subscription to ServiceNow’s Standard IntegrationHub pack, there is a spoke for integrating with Ansible Tower so you don't have to write you own API requests.

## ServiceNow/Ansible Tower Integration Instructions

### Preparing Ansible Tower

#### 1)
In Ansible Tower, navigate to **Applications** on the left side of the screen. Click the **green plus button** on the right, which will present you with a Create Application dialog screen. Fill in the following fields:
| Parameter | Value |
|-----|-----|
| Name  | Descriptive name of the application that will contact Ansible Tower  |
|  Organization |  `Default` |
|  Authorization Grant Type |  `Authorization code` |
|  Redirect URIs |  `https://<snow_instance_id>.service-now.com/oauth_redirect.do` |
|  Client Type |  `Confidential` |

<img src="images/create_application.png" alt="Tower Create Application" title="Tower Create Application" width="1000" />

#### 2)
Click the green **Save** button on the right, at which point a window will pop up, presenting you with the Client ID and Client Secret needed for ServiceNow to make API calls into Ansible Tower. This will only be presented **ONCE**, so capture these values for later use.

<img src="images/application_secrets.png" alt="Tower Application Secrets" title="Tower Application Secrets" width="500" />

#### 3)
Next, navigate to **Settings-->System** on the left side of the screen. You’ll want to toggle the **Allow External Users to Create Oauth2 Tokens** option to ***on***. Click the green **Save** button to commit the change.

<img src="images/tower_settings.png" alt="Tower Settings" title="Tower Settings" width="1000" />

#### 4)
The Orlando release of the ServiceNow developer instance does not allow for the self-signed certificate provided by Ansible Tower. We need to equip our Tower instance with a certificate from a trusted Certificate Authority. The easiest way to accomplish this to SSH into Ansible Tower and run the Certbot ACME client in order to generate a certificate from LetsEncrypt (instructions can be found [here](https://letsencrypt.org/getting-started/)). It is important to place the contents of the certificate you generate (found at `/etc/letsencrypt/live/<tower domain>/cert.pem`), followed by the LetsEncrypt intermediate certificate (starting on a new line) at location Tower places its self-signed certificate, `/etc/tower/tower.cert`. The LetsEncrypt intermediate certificate can be found [here](https://letsencrypt.org/certs/lets-encrypt-x3-cross-signed.pem.txt). You must also replace the contents of `/etc/tower/tower.key` with the contents of `/etc/letsencrypt/live/<tower domain>/privkey.pem`. 

Be sure to restart the nginx service on your Tower server after updating the certificate and key.

An example of the generated certificate with the intermediate certificate appended (what needs to be place in `/etc/tower/tower.cert`) is pictured below:

<img src="images/fullchain_cert.png" alt="Tower Cert" title="Tower Cert" width="500" />

### Preparing ServiceNow

#### 5)
Moving over to ServiceNow, Navigate to **System Definition-->Certificates**. This will take you to a screen of all the certificates Service Now uses. Click on the **blue New button**, and fill in these details:
| Parameter | Value |
|-----|-----|
| Name  | Descriptive name of the certificate  |
|  Format |  `PEM` |
|  Type |  `Trust Store Cert` |
|  PEM Certificate |  The certificate to authenticate against Ansible Tower with. Use the certificate you just generated on your Tower server, located at `/etc/tower/tower.cert.` Copy the contents of this file (EXCLUDE the intermediate certificate) into the field in ServiceNow. |

<img src="images/tower_cert.png" alt="Tower Certificate" title="Tower Certificate" width="1000" />

Click the **Submit** button at the bottom.

#### 6)
In ServiceNow, Navigate to **System OAuth-->Application Registry**. This will take you to a screen of all the Applications ServiceNow communicates with. Click on the **blue New button**, and you will be asked What kind of Oauth application you want to set up. Select **Connect to a third party Oauth Provider**.

<img src="images/snow_app_reg.png" alt="SNOW Application Registry" title="SNOW Application Registry" width="800" />

#### 7)
On the new application screen, fill in these details:

<img src="images/snow_app_reg_deets.png" alt="SNOW Application Registry Details" title="SNOW Application Registry Details" width="800" />

| Parameter | Value |
|-----|-----|
| Name  | Descriptive Application Name  |
|  Client ID |  The Client ID you got from Ansible Tower |
|  Client Secret |  The Client Secret you got from Ansible Tower |
|  Default Grant Type |  `Authorization Code` |
|  Authorization URL |  `https://<tower_url>/api/o/authorize/` |
|  Token URL |  `https://<tower_url>/api/o/token/` |
|  Redirect URL |  `https://<snow_instance_id>.service-now.com/oauth_redirect.do` |

Click the **Submit** button at the bottom.

#### 8)
You should be taken out to the list of all Application Registries. Click back into the Application you just created. At the bottom, there should be two tabs: Click on the tab **Oauth Entity Scopes**. Under here, there is a section called **Insert a new row…**. Double click here, and fill in the field to say Writing Scope. Click on the **green check mark** to confirm this change. Then, right-click inside the grey area at the top where it says Application Registries and click Save in the menu that pops up.

<img src="images/write_scope.png" alt="SNOW Write Scope" title="SNOW Write Scope" width="800" />

#### 9)
The writing scope should now be Clickable. Click on it, and in the dialog window that you are taken to, type **write** in the Oauth scope box. Click the **Update** button at the bottom.

<img src="images/write_scope_deets.png" alt="SNOW Write Scope" title="SNOW Write Scope" width="800" />

#### 10)
Back in the Application Settings page, scroll back to the bottom and click the **Oauth Entity Profiles** tab. There should be an entity profile populated - click into it.

<img src="images/oauth_entity.png" alt="Oauth Entity" title="Oauth Entity" width="500" />

#### 11)
You will be taken to the Oauth Entity Profile Window. At the bottom, Type Writing Scope into the Oauth Entity Scope field. Click the green check mark and **update**.

<img src="images/oauth_entity_deets.png" alt="Oauth Entity" title="Oauth Entity" width="800" />

#### 12)
Navigate to **System Web Services-->Outbound-->REST Messages**. Click the blue **New** button. In the resulting dialog window, fill in the following fields:

<img src="images/rest_message.png" alt="REST Message" title="REST Message" width="800" />

| Parameter | Value |
|-----|-----|
| Name  | `Provision Cloud Webservers with Users`  |
|  Endpoint |  The url endpoint of the Ansible Tower action you wish to do. This can be taken from the browsable API at `https://<tower_url>/api` |
|  Authentication Type |  `Oauth 2.0` |
|  Oauth Profile |  Select the Oauth profile you created |

Right-click inside the grey area at the top; click **Save**.

#### 13)
Click the **Get Oauth Token** button on the REST Message screen. This will generate a pop-up window asking to authorize ServiceNow against your Ansible Tower instance/cluster. Click Authorize. ServiceNow will now have an Oauth2 token to authenticate against your Ansible Tower server.

<img src="images/snow_authorize.png" alt="SNOW Authorize" title="SNOW Authorize" width="500" />

#### 14)
Under the HTTP Methods section at the bottom, click the blue New button. At the new dialog window that appears, fill in the following fields:

<img src="images/snow_http_method.png" alt="SNOW HTTP Method" title="SNOW HTTP" width="1000" />

- **HTTP Method**: `POST`
- **Name**: Descriptive HTTP Method Name
- **Endpoint**: The url endpoint of the Ansible Tower action you wish to do. This can be taken from the browsable API at `https://<tower_url>/api`
- **HTTP Headers**: ***(under the HTTP Request tab)***
  - The only HTTP Header that should be required is `Content-Type: application/json`
- **HTTP Query Parameters**: ***(under the HTTP Request tab)***
  - If you wish to pass user-provided variables into your Job/Workflow Template, you can add them into the content field. The variable value needs to be in the format `${varname}`. An example for this demonstration:

```
{
	"extra_vars":
	{
		"num_instances": ${num_instances},
		"instance_size": "${instance_size}",
		"cloud_provider": "${cloud_provider}",
		"from_snow": true
	}
}
```
**NOTE** `from_snow` is hard coded to be true; we do not want the user to change this value as this request is in fact coming from ServiceNow.

#### 15)
As we user-provided parameters in the Content field, click on Auto-generate variables in order to generate variables for test runs. Populate the Test value column with some default values that you would like to test your call with (see below for an example). You can then kick off a RESTful call to Ansible Tower using these parameters with the **Test** link.

<img src="images/snow_test_vars.png" alt="SNOW Test Vars" title="SNOW Test Vars" width="700" />

### Testing connectivity between ServiceNow and Ansible Tower

#### 16)
Clicking the **Test** link will take you to a results screen, which should indicate that the Restful call was sent successfully to Ansible Tower. In this example, ServiceNow kicks off an Ansible Tower job Template, and the response includes the Job ID in Ansible Tower:  2764

<img src="images/test_job_snow.png" alt="SNOW Test Job" title="SNOW Test Job" width="800" />

You can confirm that this Job Template was in fact started by going back to Ansible Tower and clicking the **Jobs** section on the left side of the screen; a Job with the same ID should be in the list (and, depending on the playbook size, may still be in process). In the below picture, the job is still in progress, and we can confirm that ServiceNow is able to send the RESTful call to Tower:

<img src="images/test_job_tower.png" alt="Tower Test Job" title="Tower Test Job" width="800" />

### Creating a ServiceNow Catalog Item to Launch an Ansible Tower Job Template

#### 17)
Now that you are able to make outbound RESTful calls from ServiceNow to Ansible Tower, it’s time to create a catalog item for users to select in ServiceNow in a production self-service fashion. While in the HTTP Method options, click the **Preview Script Usage** link:

<img src="images/api_script.png" alt="Tower API Script" title="Tower API Script" width="800" />

Copy the resulting script the appears, and paste it into a text editor to reference later.

#### 18)
In ServiceNow, navigate to **Workflow-->Workflow Editor**. This will open a new tab with a list of all existing ServiceNow workflows. Click on the blue **New Workflow** button:

<img src="images/workflow_editor.png" alt="Workflow Editor" title="Workflow Editor" width="800" />

#### 19)
In the New Workflow dialog box that appears, fill in the following options:

<img src="images/new_workflow.png" alt="Workflow" title="Workflow" width="800" />

| Parameter | Value |
|-----|-----|
| Name | `Provision Cloud Webservers with Users` |
| Table | `Requested Item [sc_req_item]` |

Everything else can be left alone. Click the **Submit** button.

#### 20)
The resulting Workflow Editor will have only a Begin and End box. Click on the line (it will turn blue to indicate it has been selected), then press **delete** on your keyboard to get rid of it.

<img src="images/workflow_diagram_initial.png" alt="Workflow Diagram Initial" title="Workflow Diagram Initial" width="600" />

#### 21)
On the right side of the Workflow Editor Screen, select the Core tab and, under **Core Activities-->Utilities**, drag the Run Script option into the Workflow Editor. In the new dialog box that appears, type in a descriptive name (the name of the RESTful call will suffice, `Provision Webservers with Users`), and paste in the script you captured from before. For each variable, replace the default values with ***current.variables.[variablename]*** (see example below). Click **Submit** to save the Script.

If you want to utilize the Service Now request number and pass it to Ansible for closed loop automation, add in **r.setStringParameterNoEscape('ticket_number', current.request.getDisplayValue());** Replace 'ticket_number' with the variable name utilized in the Rest Message.

<img src="images/workflow_script.png" alt="Workflow Script" title="Workflow Script" width="1000" />

#### 22)
Draw a connection from **Begin**, to the newly created Run Script Box, and another from the **Run Script** box to **End**. Afterward, click on the three horizontal lines to the left of the Workflow name, and select the **Publish** option. You are now ready to associate this workflow with a catalog item.

<img src="images/workflow_final.png" alt="Workflow Final" title="Workflow Final" width="600" />

#### 23)
Navigate to **Service Catalog-->Catalog Definitions->Maintain Items**. Click the blue **New** button on the resulting item list. In the resulting dialog box, fill in the following fields:

<img src="images/catalog_item.png" alt="Catalog Item" title="Catalog Item" width="1000" />

| Parameter | Value |
|-----|-----|
| Name | `Provision Cloud Webservers with Users` |
| Catalog | The catalog that this item should be a part of |
| Category | Required if you wish users to be able to search for this item |


In the Process Engine tab, populate the Workflow field with the Workflow you just created. Click the Submit Button. You’ve now created a new catalog item!

#### 24)
Navigate back to the Catalog Item settings, and at the bottom, click the **New** button under the variables tab. In the window that results, populate the question you want to present to the user, and the variable name. You can also put a default value under the Default Value Tab. If you select a variable type of `Multiple Choice`, after submitting the changes you can add options under the ***Question Choices*** section at the bottom of the Variable settings page.

<img src="images/catalog_vars.png" alt="Catalog Vars" title="Catalog Vars" width="1000" />

Here are the fields required for each variable in this demo:
##### cloud_provider
| Parameter | Value |
|-----|-----|
| Type | `Multiple Choice` |
| Question | `Which Cloud provider to provision into?` |
| Name | `cloud_provider` |
| Default value | `aws` |

###### variable options
| Text | Value | Order |
|-----|-----|-----|
| `Amazon Web Services` | `aws` | `100` |
| Google Cloud Platform | `gcp` | `200` |

##### num_instances
| Parameter | Value |
|-----|-----|
| Type | `Single Line Text` |
| Question | `How many instances should be spun up? (Any value from 1 through 10)` |
| Name | `num_instances` |
| Default value | `3` |

##### instance_size
| Parameter | Value |
|-----|-----|
| Type | `Multiple Choice` |
| Question | `What size instance should be selected?` |
| Name | `instance_size` |
| Default value | `small` |

###### variable options
| Text | Value | Order |
|-----|-----|-----|
| `small` | `small` | `100` |
| `medium` | `medium` |  `200` |
| `large` | `large` |  `300` |

#### 25)
Lastly, to run this catalog item, navigate to **Self-Service-->Homepage** and search for the catalog item you just created. Once found, click the **order now** button. You can see the results page pop up in ServiceNow, and you can confirm that the Job is being run in Ansible Tower.

<img src="images/catalog_order.png" alt="Catalog Item" title="Catalog Item" width="1000" />

Congratulations! After completing these steps, you can now use a ServiceNow Catalog Item to launch the AWS/GCP Workflow Template in Ansible Tower. This is ideal for allowing end users to use a front end they are familiar with in order to perform this, and other automated tasks of varying complexities. This goes a long way toward reducing the time to value for the enterprise as a whole, rather than just the teams responsible for writing the playbooks being used.

## Have Ansible Tower reach out to ServiceNow

## Dependencies:

### Ansible Engine
- ansible version >= 2.9

### Python libraries

```bash
pip3 install pysnow
pip3 install netaddr

```
These python packages must be installed in the Ansible Tower Python virtual environment that is used to run playbooks that communicate with ServiceNow.

### Collections

```bash
ansible-galaxy collection install servicenow.servicenow
ansible-galaxy collection install servicenow.itsm
```

Or if using Ansible Tower and want to attach it to a project, create a file at **collections/requirements.yml** and add

```bash
collections:

  - name: servicenow.servicenow
    source: https://galaxy.ansible.com
```

This collection will be required when running >Ansible 2.10

### Create a custom credential

Creating a custom credential in Tower will allow you to pass in your ServiceNow instance, username, and password as environment variables. This means you won't need to include them in your playbook.

#### 1)
In Ansible Tower, navigate to **Credential Types** on the left side of the screen. Click the **green plus button** on the right, which will present you with a New Credential Type dialog screen. Fill in the following fields:
| Parameter | Value |
|-----|-----|
| Name  |  `ServiceNow Credential`  |
| Description | Description of your credential type |

Input Configuration

```
fields:
  - id: instance
    type: string
    label: Instance
  - id: username
    type: string
    label: Username
  - id: password
    type: string
    label: Password
    secret: true
required:
  - instance
  - username
  - password
```

Injector Configuration


```
env:
  SN_INSTANCE: '{{instance}}'
  SN_PASSWORD: '{{password}}'
  SN_USERNAME: '{{username}}'
```

<img src="images/credtype.png" alt="Tower Credential Type" title="Tower Credential Type" width="1000" />

| Parameter | Value |
|-----|-----|
| Name  |  `ServiceNow ITSM Credential`  |
| Description | Description of your credential type |

Input Configuration

```
fields:
  - id: instance
    type: string
    label: Instance
  - id: username
    type: string
    label: Username
  - id: password
    type: string
    label: Password
    secret: true
required:
  - instance
  - username
  - password
```

Injector Configuration


```
env:
  SN_HOST: '{{instance}}'
  SN_PASSWORD: '{{password}}'
  SN_USERNAME: '{{username}}'
```

<img src="images/itsmcredtype.png" alt="Tower Credential Type ITSM" title="Tower Credential Type ITSM" width="1000" />

#### 2) Create your ServiceNow Credential

In Ansible Tower, navigate to **Credentials** on the left side of the screen. Click the **green plus button** on the right, which will present you with a New Credential dialog screen. Fill in the following fields:


| Parameter | Value |
|-----|-----|
| Name | `ServiceNow Credential` |
| Description | Description of your credential |
| Organization |  `Default` |
| Credential Type | `ServiceNow Credential` |
| Instance | `<snow_instance_id> from URL before .service-now.com` |
| Username | `SNOW Username` |
| Password | `SNOW Password` |

<img src="images/cred.png" alt="Tower Credential" title="Tower Credential" width="1000" />

| Parameter | Value |
|-----|-----|
| Name | `ServiceNow ITSM Credential` |
| Description | Description of your credential |
| Organization |  `Default` |
| Credential Type | `ServiceNow ITSM Credential` |
| Instance | `<snow_instance_id> including .service-now.com` |
| Username | `SNOW Username` |
| Password | `SNOW Password` |

<img src="images/itsmcred.png" alt="Tower Credential ITSM" title="Tower Credential ITSM" width="1000" />

#### 3) Create a Job Template

Create a playbook in your repo utilzing your new Ansible collection referencing the apppropriate modules from https://galaxy.ansible.com/servicenow/servicenow. When creating your job template, ensure you select the ServiceNow credential that you created.

Congratulations! You can now have Tower reach out to SNOW to query and update records!

# Example playbooks

## Creating an incident in SNOW with custom fields that uses stored facts in Ansible to populate IP address, OS, and VM name
```
- name: Create an incident in ServiceNow
  hosts: "{{ vm_name }}"
  gather_facts: yes
  connection: local

  collections:
    - servicenow.itsm
  
  tasks: 
  
  - name: Create an incident in ServiceNow
    servicenow.itsm.incident:
      state: new
      description: "{{ sn_description | default(omit) }}"
      short_description: "{{ incident_description }}"
      caller: admin
      urgency: "{{ sn_urgency }}"
      impact: "{{ sn_impact }}"
      other:
        u_operating_system: "{{ os | default(omit) }}"
        u_ip_address: "{{ ip_addr | default(omit) }}"
        u_vm_name: "{{ inventory_hostname | default(omit) }}"       
    register: new_incident
    delegate_to: localhost

  - debug: 
      var: new_incident.record.number
```

## Update a ServiceNow catalog request using the ID passed from SNOW
```
- name: Update a catalog item in ServiceNow
  hosts: all
  gather_facts: no
  connection: local

  collections:
    - servicenow.servicenow
  
  tasks: 
  - name: Update a catalog work notes and state in ServiceNow
    servicenow.servicenow.snow_record:
      state: present
      number: "{{ ticket_number }}"
      table: sc_request
      data:
        request_state: "{{ request_state | default(omit) }}"
        work_notes: "{{ work_notes }}"
    delegate_to: localhost
    
```

## Have Ansible Tower use ServiceNow as an inventory source

## Dependencies:

### Ansible Engine
- ansible version >= 2.9

### Python libraries

```bash
pip3 install requests
pip3 install netaddr

```
These python packages must be installed in the Ansible Tower Python virtual environment that is used to run playbooks that communicate with ServiceNow.

### Collections

```bash
ansible-galaxy collection install servicenow.servicenow
```

Or if using Ansible Tower and want to attach it to a project, create a file at **collections/requirements.yml** and add

```bash
collections:

  - name: servicenow.servicenow
    source: https://galaxy.ansible.com
```

This collection will be required when running >Ansible 2.10

### Create a custom credential if not already done

Creating a custom credential in Tower will allow you to pass in your ServiceNow instance, username, and password as environment variables. This means you won't need to include them in your playbook.

#### 1)
In Ansible Tower, navigate to **Credential Types** on the left side of the screen. Click the **green plus button** on the right, which will present you with a New Credential Type dialog screen. Fill in the following fields:
| Parameter | Value |
|-----|-----|
| Name  |  `ServiceNow Credential`  |
| Description | Description of your credential type |

Input Configuration

```
fields:
  - id: instance
    type: string
    label: Instance
  - id: username
    type: string
    label: Username
  - id: password
    type: string
    label: Password
    secret: true
required:
  - instance
  - username
  - password
```

Injector Configuration


```
env:
  SN_INSTANCE: '{{instance}}'
  SN_PASSWORD: '{{password}}'
  SN_USERNAME: '{{username}}'
```

<img src="images/credtype.png" alt="Tower Credential Type" title="Tower Credential Type" width="1000" />

#### 2) Create your ServiceNow Credential

In Ansible Tower, navigate to **Credentials** on the left side of the screen. Click the **green plus button** on the right, which will present you with a New Credential dialog screen. Fill in the following fields:


| Parameter | Value |
|-----|-----|
| Name | `ServiceNow Credential` |
| Description | Description of your credential |
| Organization |  `Default` |
| Credential Type | `ServiceNow Credential` |
| Instance | `<snow_instance_id> from URL including .service-now.com` |
| Username | `SNOW Username` |
| Password | `SNOW Password` |

<img src="images/cred.png" alt="Tower Credential" title="Tower Credential" width="1000" />

#### 3) Inventory yml file

Create a playbook in your repo utilzing your new Ansible collection. Note, the instance field does require the full domain name at this time. Name the file now.yml or now.yaml. You can adjust the selection order, fields, compose, and keyed_groups per the documenation https://github.com/ServiceNowITOM/servicenow-ansible/blob/devel/docs/inventory.md
```
# my.SNOW.yml
plugin: servicenow.servicenow.now
instance: <snow_instance_id>.service-now.com
selection_order: [host_name,ip_address,name]
fields: [ip_address,host_name,sys_class_name,name,os,os_version,ram,cpu_core_count]
compose:
  ansible_host: sn_ip_address
keyed_groups:
  - key: sn_sys_class_name | lower
    prefix: ''
    separator: ''
```

#### 4) Create your ServiceNow Inventory

In Ansible Tower, navigate to **Inventories** on the left side of the screen. Click the **green plus button** on the right, which will present you with a New Inventory dialog screen. Fill in the following fields:


| Parameter | Value |
|-----|-----|
| Name | `ServiceNow Inventory` |
| Description | Description of your Inventory |
| Organization |  `Default` |

<img src="images/inventory.png" alt="Tower Inventory" title="Tower Inventory" width="1000" />

#### 5) Create your ServiceNow Source

In Ansible Tower, after you've saved, click to **Sources** on the top of the screen. Click the **green plus button** on the right, which will present you with a New Inventory dialog screen. Fill in the following fields:


| Parameter | Value |
|-----|-----|
| Name | `ServiceNow Inventory` |
| Description | Description of your Inventory |
| Source |  `Sourced from a Project` |
| Credential |  `ServiceNow Credential` |
| Project |  `Project that contains your now.yml playbook` |
| Inventory File |  `Type the exact location of the file in the repo i.e. inventories/now.yml` |

<img src="images/inventorysource.png" alt="Tower Inventory Source" title="Tower Inventory Source" width="1000" />

Save and then sync the inventory. You now have a dynamic inventory from ServiceNow

<!-- # Table Of Contents
- [Software Requirements](#requirements)
- [Variables](#variables)
  * [default-vars.yml](#default-variables)
  * [linux_users.yml](#linux-users)
- [Credentials](#credentials)
  * [gmail_creds.yml](#gmail-credentials)
  * [redhat-activation-key.yml](#redhat-activation-key)
  * [snow_creds.yml](#servicenow-credentials)
  * [tower_creds.yml](#tower-credentials)
  * [vault_creds.yml](#hashicorp-vault-credentials)

## Requirements -->
