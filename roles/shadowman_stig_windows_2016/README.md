<!-- This was created with Claude Code -->

shadowman_stig_windows_2016
===========================

Apply the DISA Windows Server 2016 STIG

Requirements
------------

- Ansible 2.9 or higher
- Access to target systems with appropriate permissions

Role Variables
--------------

* **win2016stig_cat1_patch**: Variable used in: Execute the category 1 (highest severity) tasks
  - Default: `True`

* **win2016stig_cat2_patch**: Variable used in: Execute the category 2 (medium severity) tasks
  - Default: `True`

* **win2016stig_cat3_patch**: Variable used in: Execute the category 3 (lowest severity) tasks
  - Default: `True`

* **win2016stig_min_ansible_version**: Variable used in: Check ansible version
  - Default: `2.6`

* **win2016stig_complexity_high**: may fail in some cases.
  - Default: `False`

* **win2016stig_audit_complex**: indicate items requiring manual review.
  - Default: `True`

* **win2016stig_disruption_high**: but are disabled by default to avoid disruption.
  - Default: `False`

* **win2016stig_audit_disruptive**: setting to make them stand out.
  - Default: `True`

* **winstig_skip_for_travis**: IP address
  - Default: `False`

* **winstig_skip_for_test**: Some tasks need to be skipped for CI/CD testing to work correctly
  - Default: `False`

* **win2016stig_workaround_for_disa_benchmark**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **win2016stig_workaround_for_ssg_benchmark**: Security group identifier
  - Default: `True`

* **win2016stig_system_is_container**: tweak role to run in a non-privileged container
  - Default: `False`

* **wn16_00_000010**: CAT 1 rules
  - Default: `True`

* **wn16_dc_000010**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_ms_000010**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_00_000040**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_00_000110**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_00_000120**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_00_000150**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_ac_000090**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_dc_000070**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_dc_000080**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_dc_000090**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_dc_000100**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_dc_000110**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_dc_000150**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_ms_000120**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_cc_000250**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_cc_000260**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_cc_000270**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_cc_000460**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_cc_000500**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_cc_000530**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_dc_000290**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_dc_000300**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_so_000020**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_so_000250**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_so_000260**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_so_000270**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_so_000300**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_so_000360**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_so_000380**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_ur_000030**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_ur_000090**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_ur_000130**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_00_000030**: CAT 2 rules
  - Default: `True`

* **wn16_00_000050**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_00_000060**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_00_000070**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_00_000080**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_00_000090**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_00_000100**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_00_000140**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_00_000160**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_00_000170**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_00_000180**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_00_000190**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_00_000210**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_00_000220**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_00_000230**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_00_000240**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_00_000250**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_00_000270**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_00_000280**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_00_000290**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_00_000300**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_00_000310**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_00_000320**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_00_000330**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_00_000340**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_00_000350**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_00_000360**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_00_000370**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_00_000380**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_00_000390**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_00_000400**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_00_000410**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_00_000420**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_00_000430**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_00_000440**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_ac_000010**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_ac_000020**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_ac_000030**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_ac_000040**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_ac_000050**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_ac_000060**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_ac_000070**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_ac_000080**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_dc_000020**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_dc_000030**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_dc_000040**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_dc_000050**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_dc_000060**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_dc_000120**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_dc_000130**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_dc_000140**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_dc_000170**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_dc_000180**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_dc_000190**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_dc_000200**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_dc_000210**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_dc_000220**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_au_000010**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_au_000020**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_au_000030**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_au_000040**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_au_000050**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_au_000060**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_au_000070**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_au_000080**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_dc_000230**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_au_000100**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_au_000120**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_au_000140**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_au_000150**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_au_000160**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_au_000170**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_dc_000240**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_dc_000250**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_dc_000260**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_dc_000270**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_au_000220**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_au_000230**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_au_000240**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_au_000250**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_au_000260**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_au_000270**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_au_000280**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_au_000290**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_au_000300**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_au_000310**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_au_000320**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_au_000330**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_au_000340**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_au_000350**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_au_000360**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_au_000370**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_au_000380**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_au_000390**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_au_000400**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_au_000410**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_au_000420**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_cc_000280**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_au_000440**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_au_000450**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_cc_000010**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_ms_000020**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_cc_000030**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_cc_000080**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_cc_000090**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_cc_000100**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_cc_000110**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_cc_000140**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_cc_000150**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_cc_000160**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_cc_000170**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_cc_000180**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_ms_000030**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_cc_000210**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_cc_000220**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_ms_000040**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_cc_000290**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_cc_000300**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_cc_000310**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_cc_000320**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_cc_000330**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_cc_000340**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_cc_000360**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_cc_000370**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_cc_000380**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_cc_000390**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_cc_000400**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_cc_000410**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_cc_000420**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_cc_000421**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_cc_000430**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_cc_000440**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_cc_000450**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_cc_000470**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_cc_000480**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_cc_000490**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_cc_000510**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_cc_000520**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_cc_000540**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_cc_000550**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_pk_000010**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_pk_000020**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_pk_000030**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_dc_000280**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_dc_000310**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_so_000030**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_so_000040**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_so_000050**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_dc_000320**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_dc_000330**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_so_000080**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_so_000090**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_so_000100**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_so_000110**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_so_000120**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_so_000130**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_so_000140**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_so_000150**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_ms_000050**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_so_000190**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_so_000200**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_so_000210**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_so_000230**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_so_000240**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_so_000290**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_ms_000310**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_so_000320**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_so_000330**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_so_000340**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_so_000350**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_so_000390**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_so_000400**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_so_000410**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_so_000420**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_so_000430**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_so_000460**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_so_000470**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_so_000480**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_so_000490**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_so_000500**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_so_000510**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_so_000520**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_so_000530**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_uc_000030**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_ur_000010**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_dc_000340**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_ms_000340**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_dc_000350**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_ur_000050**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_dc_000360**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_ur_000070**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_ur_000080**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_ur_000100**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_ur_000110**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_ur_000120**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_dc_000370**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_ms_000370**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_dc_000380**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_ms_000380**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_dc_000390**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_ms_000390**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_dc_000400**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_ms_000400**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_dc_000410**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_ms_000410**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_dc_000420**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_ms_000420**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_ur_000200**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_ur_000210**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_ur_000220**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_ur_000230**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_ur_000240**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_ur_000250**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_ur_000260**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_ur_000270**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_ur_000280**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_ur_000290**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_ur_000300**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_ur_000310**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_so_000180**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_so_000010**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_00_000411**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_00_000412**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_00_000460**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_au_000285**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_au_000286**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_dc_000430**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_00_000200**: CAT 3 rules
  - Default: `True`

* **wn16_00_000450**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_dc_000160**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_cc_000040**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_cc_000050**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_cc_000060**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_cc_000070**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_cc_000240**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_cc_000350**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_so_000160**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_so_000450**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_00_000470**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_00_000480**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `True`

* **wn16_ur_000130_sedebugprivilege**: This SID is the same for standalone, member, domain controller for 'Administrators' group
  - Default: `*S-1-5-32-544`

* **wn16_00_000030_pass_age**: CAT 2 defaults
  - Default: `60`

* **wn16_ac_000010_lockoutduration**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `15`

* **wn16_ac_000020_lockoutbadcount**: Numeric count or quantity
  - Default: `3`

* **wn16_ac_000030_resetlockoutcount**: Numeric count or quantity
  - Default: `15`

* **wn16_ac_000040_passwordhistorysize**: Password or authentication credential
  - Default: `24`

* **wn16_ac_000050_maximumpasswordage**: Password or authentication credential
  - Default: `60`

* **wn16_ac_000060_minimumpasswordage**: Password or authentication credential
  - Default: `1`

* **wn16_ac_000070_minimumpasswordlength**: Password or authentication credential
  - Default: `14`

* **wn16_so_000030_newadministratorname**: Resource name
  - Default: `ansibleadmin`

* **wn16_so_000040_newguestname**: Resource name
  - Default: `ansibleguest`

* **wn16_so_000150_legalnoticetext**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `You are accessing a U.S. Government (USG) Information System (IS) that is provided for USG-authorized use only.

By using this IS (which includes any device attached to this IS), you consent to the following conditions:

-The USG routinely intercepts and monitors communications on this IS for purposes including, but not limited to, penetration testing, COMSEC monitoring, network operations and defense, personnel misconduct (PM), law enforcement (LE), and counterintelligence (CI) investigations.

-At any time, the USG may inspect and seize data stored on this IS.

-Communications using, or data stored on, this IS are not private, are subject to routine monitoring, interception, and search, and may be disclosed or used for any USG-authorized purpose.

-This IS includes security measures (e.g., authentication and access controls) to protect USG interests--not for your personal benefit or privacy.

-Notwithstanding the above, using this IS does not constitute consent to PM, LE or CI investigative searching or monitoring of the content of privileged communications, or work product, related to personal representation or services by attorneys, psychotherapists, or clergy, and their assistants. Such communications and work product are private and confidential. See User Agreement for details.
`

* **wn16_cc_000300_app_maxsize**: Size specification
  - Default: `32768`

* **wn16_cc_000310_sec_maxsize**: Size specification
  - Default: `196608`

* **wn16_cc_000320_sys_maxsize**: Size specification
  - Default: `32768`

* **wn16_dc_000430_pass_age**: Configuration parameter for shadowman_stig_windows_2016
  - Default: `180`

* **wn16_so_000160_legalnoticecaption**: CAT 3 defaults
  - Default: `DoD Notice and Consent Banner`

Dependencies
------------

None

Example Playbook
----------------

```yaml
- hosts: all
  roles:
    - role: shadowman_stig_windows_2016
      vars:
        win2016stig_cat1_patch: <value>
        win2016stig_cat2_patch: <value>
        win2016stig_cat3_patch: <value>
```

License
-------

GNU General Public License v3.0 or later

Author Information
------------------

Red Hat Ansible Automation Platform
