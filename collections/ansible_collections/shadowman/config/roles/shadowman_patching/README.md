shadowman_patching
=========

Sample role to demonstrate running molecule inside of OpenShift Dev Spaces for RHEL patching. Molecule is configured to leverage the downstream API to create containers in the user's devspace namespace. This role does not require elevated permissions or modifications to OpenShift.

Requirements
------------

- The Kubernetes python module is required. This is installed to the DevSpace as part of the molecule prepare stage.
- The 'oc' binary is required. This is installed as part of the molecule prepare stage and added to ~/.bashrc. If you need to run oc commands you can source your bashrc file after running the prepare. `source ~/.bashrc`
- kubernetes.core collection
- community.okd or redhat.openshift collection
- Required collections are included in the requirements.yml file that can be installed with `ansible-galaxy install -r requirements.yml` command


Manually installing dependencies (rather than using `molecule prepare`)
-------------

Download the 'oc' binary from the downloads route local to the cluster and add to path

```
mkdir $HOME/bin
curl -o $HOME/bin/oc http://downloads.openshift-console.svc.cluster.local/amd64/linux/oc
chmod u+x $HOME/bin/oc
export PATH=$PATH:$HOME/bin
```

OpenShift Token is automatically injected. You can verify this by running the following commands:

```
oc whoami
oc get pods
```


Dependencies
------------

No dependencies other than the collections included in the requirements.yml

- kubernetes.core collection
- community.okd or redhat.openshift collection
- Required collections are included in the requirements.yml file that can be installed with `ansible-galaxy install -r requirements.yml` command


License
-------

GNU General Public License v3.0 or later
