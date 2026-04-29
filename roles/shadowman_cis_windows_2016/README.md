<!-- This was created with Claude Code -->

shadowman_cis_windows_2016
==========================

Ansible role to apply Windows Server 2016 CIS Benchmark

Requirements
------------

- Ansible 2.9 or higher
- Access to target systems with appropriate permissions

Role Variables
--------------

* **section01_patch**: Variable used in: Execute the section 1 tasks
  - Default: `True`

* **section02_patch**: Variable used in: Execute the section 2 tasks
  - Default: `True`

* **section09_patch**: Variable used in: Execute the section 9 tasks
  - Default: `True`

* **section17_patch**: Variable used in: Execute the section 17 tasks
  - Default: `True`

* **section18_patch**: Variable used in: Execute the section 18 tasks
  - Default: `True`

* **section19_patch**: Variable used in: Execute the section 19 tasks
  - Default: `True`

* **min_ansible_version**: Variable used in: Check ansible version
  - Default: `2.6`

* **complexity_high**: may fail in some cases.
  - Default: `False`

* **audit_complex**: indicate items requiring manual review.
  - Default: `True`

* **disruption_high**: but are disabled by default to avoid disruption.
  - Default: `False`

* **audit_disruptive**: setting to make them stand out.
  - Default: `True`

* **skip_for_travis**: IP address
  - Default: `False`

* **workaround_for_disa_benchmark**: Configuration parameter for shadowman_cis_windows_2016
  - Default: `True`

* **workaround_for_ssg_benchmark**: Security group identifier
  - Default: `True`

* **system_is_container**: tweak role to run in a non-privileged container
  - Default: `False`

* **is_implemented**: set to false to skip tasks that either have not been developed or cannot be automated
  - Default: `False`

* **long_running**: set to false to skip long running tasks
  - Default: `False`

* **win_skip_for_test**: IP address
  - Default: `False`

* **rule_1_1_1**: section01
  - Default: `True`

* **rule_1_1_2**: Rule or rules configuration
  - Default: `True`

* **rule_1_1_3**: Rule or rules configuration
  - Default: `True`

* **rule_1_1_4**: Rule or rules configuration
  - Default: `True`

* **rule_1_1_5**: Rule or rules configuration
  - Default: `True`

* **rule_1_1_6**: Rule or rules configuration
  - Default: `True`

* **rule_1_2_1**: Rule or rules configuration
  - Default: `True`

* **rule_1_2_2**: Rule or rules configuration
  - Default: `True`

* **rule_1_2_3**: Rule or rules configuration
  - Default: `True`

* **rule_2_2_1**: section02
  - Default: `True`

* **rule_2_2_2**: Rule or rules configuration
  - Default: `True`

* **rule_2_2_3**: Rule or rules configuration
  - Default: `True`

* **rule_2_2_4**: Rule or rules configuration
  - Default: `True`

* **rule_2_2_5**: Rule or rules configuration
  - Default: `True`

* **rule_2_2_6**: Rule or rules configuration
  - Default: `True`

* **rule_2_2_7**: Rule or rules configuration
  - Default: `True`

* **rule_2_2_8**: Rule or rules configuration
  - Default: `True`

* **rule_2_2_9**: Rule or rules configuration
  - Default: `True`

* **rule_2_2_10**: Rule or rules configuration
  - Default: `True`

* **rule_2_2_11**: Rule or rules configuration
  - Default: `True`

* **rule_2_2_12**: Rule or rules configuration
  - Default: `True`

* **rule_2_2_13**: Rule or rules configuration
  - Default: `True`

* **rule_2_2_14**: Rule or rules configuration
  - Default: `True`

* **rule_2_2_15**: Rule or rules configuration
  - Default: `True`

* **rule_2_2_16**: Rule or rules configuration
  - Default: `True`

* **rule_2_2_17**: Rule or rules configuration
  - Default: `True`

* **rule_2_2_18**: Rule or rules configuration
  - Default: `True`

* **rule_2_2_19**: Rule or rules configuration
  - Default: `True`

* **rule_2_2_20**: Rule or rules configuration
  - Default: `True`

* **rule_2_2_21**: Rule or rules configuration
  - Default: `True`

* **rule_2_2_22**: Rule or rules configuration
  - Default: `True`

* **rule_2_2_23**: Rule or rules configuration
  - Default: `True`

* **rule_2_2_24**: Rule or rules configuration
  - Default: `True`

* **rule_2_2_25**: Rule or rules configuration
  - Default: `True`

* **rule_2_2_26**: Rule or rules configuration
  - Default: `True`

* **rule_2_2_27**: Rule or rules configuration
  - Default: `True`

* **rule_2_2_28**: Rule or rules configuration
  - Default: `True`

* **rule_2_2_29**: Rule or rules configuration
  - Default: `True`

* **rule_2_2_30**: Rule or rules configuration
  - Default: `True`

* **rule_2_2_31**: Rule or rules configuration
  - Default: `True`

* **rule_2_2_32**: Rule or rules configuration
  - Default: `True`

* **rule_2_2_33**: Rule or rules configuration
  - Default: `True`

* **rule_2_2_34**: Rule or rules configuration
  - Default: `True`

* **rule_2_2_35**: Rule or rules configuration
  - Default: `True`

* **rule_2_2_36**: Rule or rules configuration
  - Default: `True`

* **rule_2_2_37**: Rule or rules configuration
  - Default: `True`

* **rule_2_2_38**: Rule or rules configuration
  - Default: `True`

* **rule_2_2_39**: Rule or rules configuration
  - Default: `True`

* **rule_2_2_40**: Rule or rules configuration
  - Default: `True`

* **rule_2_2_41**: Rule or rules configuration
  - Default: `True`

* **rule_2_2_42**: Rule or rules configuration
  - Default: `True`

* **rule_2_2_43**: Rule or rules configuration
  - Default: `True`

* **rule_2_2_44**: Rule or rules configuration
  - Default: `True`

* **rule_2_2_45**: Rule or rules configuration
  - Default: `True`

* **rule_2_2_46**: Rule or rules configuration
  - Default: `True`

* **rule_2_2_47**: Rule or rules configuration
  - Default: `True`

* **rule_2_2_48**: Rule or rules configuration
  - Default: `True`

* **rule_2_3_1_1**: Rule or rules configuration
  - Default: `True`

* **rule_2_3_1_2**: Rule or rules configuration
  - Default: `True`

* **rule_2_3_1_3**: Rule or rules configuration
  - Default: `True`

* **rule_2_3_1_4**: Rule or rules configuration
  - Default: `True`

* **rule_2_3_1_5**: Rule or rules configuration
  - Default: `True`

* **rule_2_3_1_6**: Rule or rules configuration
  - Default: `True`

* **rule_2_3_2_1**: Rule or rules configuration
  - Default: `True`

* **rule_2_3_2_2**: Rule or rules configuration
  - Default: `True`

* **rule_2_3_4_1**: Rule or rules configuration
  - Default: `True`

* **rule_2_3_4_2**: Rule or rules configuration
  - Default: `True`

* **rule_2_3_5_1**: Rule or rules configuration
  - Default: `True`

* **rule_2_3_5_2**: Rule or rules configuration
  - Default: `True`

* **rule_2_3_5_3**: Rule or rules configuration
  - Default: `True`

* **rule_2_3_6_1**: Rule or rules configuration
  - Default: `True`

* **rule_2_3_6_2**: Rule or rules configuration
  - Default: `True`

* **rule_2_3_6_3**: Rule or rules configuration
  - Default: `True`

* **rule_2_3_6_4**: Rule or rules configuration
  - Default: `True`

* **rule_2_3_6_5**: Rule or rules configuration
  - Default: `True`

* **rule_2_3_6_6**: Rule or rules configuration
  - Default: `True`

* **rule_2_3_7_1**: Rule or rules configuration
  - Default: `True`

* **rule_2_3_7_2**: Rule or rules configuration
  - Default: `True`

* **rule_2_3_7_3**: Rule or rules configuration
  - Default: `True`

* **rule_2_3_7_4**: Rule or rules configuration
  - Default: `True`

* **rule_2_3_7_5**: Rule or rules configuration
  - Default: `True`

* **rule_2_3_7_6**: Rule or rules configuration
  - Default: `True`

* **rule_2_3_7_7**: Rule or rules configuration
  - Default: `True`

* **rule_2_3_7_8**: Rule or rules configuration
  - Default: `True`

* **rule_2_3_7_9**: Rule or rules configuration
  - Default: `True`

* **rule_2_3_8_1**: Rule or rules configuration
  - Default: `True`

* **rule_2_3_8_2**: Rule or rules configuration
  - Default: `True`

* **rule_2_3_8_3**: Rule or rules configuration
  - Default: `True`

* **rule_2_3_9_1**: Rule or rules configuration
  - Default: `True`

* **rule_2_3_9_2**: Rule or rules configuration
  - Default: `True`

* **rule_2_3_9_3**: Rule or rules configuration
  - Default: `True`

* **rule_2_3_9_4**: Rule or rules configuration
  - Default: `True`

* **rule_2_3_9_5**: Rule or rules configuration
  - Default: `True`

* **rule_2_3_10_1**: Rule or rules configuration
  - Default: `True`

* **rule_2_3_10_2**: Rule or rules configuration
  - Default: `True`

* **rule_2_3_10_3**: Rule or rules configuration
  - Default: `True`

* **rule_2_3_10_4**: Rule or rules configuration
  - Default: `True`

* **rule_2_3_10_5**: Rule or rules configuration
  - Default: `True`

* **rule_2_3_10_6**: Rule or rules configuration
  - Default: `True`

* **rule_2_3_10_7**: Rule or rules configuration
  - Default: `True`

* **rule_2_3_10_8**: Rule or rules configuration
  - Default: `True`

* **rule_2_3_10_9**: Rule or rules configuration
  - Default: `True`

* **rule_2_3_10_10**: Rule or rules configuration
  - Default: `True`

* **rule_2_3_10_11**: Rule or rules configuration
  - Default: `True`

* **rule_2_3_10_12**: Rule or rules configuration
  - Default: `True`

* **rule_2_3_10_13**: Rule or rules configuration
  - Default: `True`

* **rule_2_3_11_1**: Rule or rules configuration
  - Default: `True`

* **rule_2_3_11_2**: Rule or rules configuration
  - Default: `True`

* **rule_2_3_11_3**: Rule or rules configuration
  - Default: `True`

* **rule_2_3_11_4**: Rule or rules configuration
  - Default: `True`

* **rule_2_3_11_5**: Rule or rules configuration
  - Default: `True`

* **rule_2_3_11_6**: Rule or rules configuration
  - Default: `True`

* **rule_2_3_11_7**: Rule or rules configuration
  - Default: `True`

* **rule_2_3_11_8**: Rule or rules configuration
  - Default: `True`

* **rule_2_3_11_9**: Rule or rules configuration
  - Default: `True`

* **rule_2_3_11_10**: Rule or rules configuration
  - Default: `True`

* **rule_2_3_13_1**: Rule or rules configuration
  - Default: `True`

* **rule_2_3_15_1**: Rule or rules configuration
  - Default: `True`

* **rule_2_3_15_2**: Rule or rules configuration
  - Default: `True`

* **rule_2_3_17_1**: Rule or rules configuration
  - Default: `True`

* **rule_2_3_17_2**: Rule or rules configuration
  - Default: `True`

* **rule_2_3_17_3**: Rule or rules configuration
  - Default: `True`

* **rule_2_3_17_4**: Rule or rules configuration
  - Default: `True`

* **rule_2_3_17_5**: Rule or rules configuration
  - Default: `True`

* **rule_2_3_17_6**: Rule or rules configuration
  - Default: `True`

* **rule_2_3_17_7**: Rule or rules configuration
  - Default: `True`

* **rule_2_3_17_8**: Rule or rules configuration
  - Default: `True`

* **rule_9_1_1**: section9
  - Default: `True`

* **rule_9_1_2**: Rule or rules configuration
  - Default: `True`

* **rule_9_1_3**: Rule or rules configuration
  - Default: `True`

* **rule_9_1_4**: Rule or rules configuration
  - Default: `True`

* **rule_9_1_5**: Rule or rules configuration
  - Default: `True`

* **rule_9_1_6**: Rule or rules configuration
  - Default: `True`

* **rule_9_1_7**: Rule or rules configuration
  - Default: `True`

* **rule_9_1_8**: Rule or rules configuration
  - Default: `True`

* **rule_9_2_1**: Rule or rules configuration
  - Default: `True`

* **rule_9_2_2**: Rule or rules configuration
  - Default: `True`

* **rule_9_2_3**: Rule or rules configuration
  - Default: `True`

* **rule_9_2_4**: Rule or rules configuration
  - Default: `True`

* **rule_9_2_5**: Rule or rules configuration
  - Default: `True`

* **rule_9_2_6**: Rule or rules configuration
  - Default: `True`

* **rule_9_2_7**: Rule or rules configuration
  - Default: `True`

* **rule_9_2_8**: Rule or rules configuration
  - Default: `True`

* **rule_9_3_1**: Rule or rules configuration
  - Default: `True`

* **rule_9_3_2**: Rule or rules configuration
  - Default: `True`

* **rule_9_3_3**: Rule or rules configuration
  - Default: `True`

* **rule_9_3_4**: Rule or rules configuration
  - Default: `True`

* **rule_9_3_5**: Rule or rules configuration
  - Default: `True`

* **rule_9_3_6**: Rule or rules configuration
  - Default: `True`

* **rule_9_3_7**: Rule or rules configuration
  - Default: `True`

* **rule_9_3_8**: Rule or rules configuration
  - Default: `True`

* **rule_9_3_9**: Rule or rules configuration
  - Default: `True`

* **rule_9_3_10**: Rule or rules configuration
  - Default: `True`

* **rule_17_1_1**: section17
  - Default: `True`

* **rule_17_1_2**: Rule or rules configuration
  - Default: `True`

* **rule_17_1_3**: Rule or rules configuration
  - Default: `True`

* **rule_17_2_1**: Rule or rules configuration
  - Default: `True`

* **rule_17_2_2**: Rule or rules configuration
  - Default: `True`

* **rule_17_2_3**: Rule or rules configuration
  - Default: `True`

* **rule_17_2_4**: Rule or rules configuration
  - Default: `True`

* **rule_17_2_5**: Rule or rules configuration
  - Default: `True`

* **rule_17_2_6**: Rule or rules configuration
  - Default: `True`

* **rule_17_3_1**: Rule or rules configuration
  - Default: `True`

* **rule_17_3_2**: Rule or rules configuration
  - Default: `True`

* **rule_17_4_1**: Rule or rules configuration
  - Default: `True`

* **rule_17_4_2**: Rule or rules configuration
  - Default: `True`

* **rule_17_5_1**: Rule or rules configuration
  - Default: `True`

* **rule_17_5_2**: Rule or rules configuration
  - Default: `True`

* **rule_17_5_3**: Rule or rules configuration
  - Default: `True`

* **rule_17_5_4**: Rule or rules configuration
  - Default: `True`

* **rule_17_5_5**: Rule or rules configuration
  - Default: `True`

* **rule_17_5_6**: Rule or rules configuration
  - Default: `True`

* **rule_17_6_1**: Rule or rules configuration
  - Default: `True`

* **rule_17_6_2**: Rule or rules configuration
  - Default: `True`

* **rule_17_6_3**: Rule or rules configuration
  - Default: `True`

* **rule_17_6_4**: Rule or rules configuration
  - Default: `True`

* **rule_17_7_1**: Rule or rules configuration
  - Default: `True`

* **rule_17_7_2**: Rule or rules configuration
  - Default: `True`

* **rule_17_7_3**: Rule or rules configuration
  - Default: `True`

* **rule_17_7_4**: Rule or rules configuration
  - Default: `True`

* **rule_17_7_5**: Rule or rules configuration
  - Default: `True`

* **rule_17_8_1**: Rule or rules configuration
  - Default: `True`

* **rule_17_9_1**: Rule or rules configuration
  - Default: `True`

* **rule_17_9_2**: Rule or rules configuration
  - Default: `True`

* **rule_17_9_3**: Rule or rules configuration
  - Default: `True`

* **rule_17_9_4**: Rule or rules configuration
  - Default: `True`

* **rule_17_9_5**: Rule or rules configuration
  - Default: `True`

* **rule_18_1_1_1**: section18
  - Default: `True`

* **rule_18_1_1_2**: Rule or rules configuration
  - Default: `True`

* **rule_18_1_2_2**: Rule or rules configuration
  - Default: `True`

* **rule_18_1_3**: Rule or rules configuration
  - Default: `True`

* **rule_18_2_1**: Rule or rules configuration
  - Default: `True`

* **rule_18_2_2**: Rule or rules configuration
  - Default: `True`

* **rule_18_2_3**: Rule or rules configuration
  - Default: `True`

* **rule_18_2_4**: Rule or rules configuration
  - Default: `True`

* **rule_18_2_5**: Rule or rules configuration
  - Default: `True`

* **rule_18_2_6**: Rule or rules configuration
  - Default: `True`

* **rule_18_3_1**: Rule or rules configuration
  - Default: `True`

* **rule_18_3_2**: Rule or rules configuration
  - Default: `True`

* **rule_18_3_3**: Rule or rules configuration
  - Default: `True`

* **rule_18_3_4**: Rule or rules configuration
  - Default: `True`

* **rule_18_3_5**: Rule or rules configuration
  - Default: `True`

* **rule_18_3_6**: Rule or rules configuration
  - Default: `True`

* **rule_18_3_7**: Rule or rules configuration
  - Default: `True`

* **rule_18_4_1**: Rule or rules configuration
  - Default: `True`

* **rule_18_4_2**: Rule or rules configuration
  - Default: `True`

* **rule_18_4_3**: Rule or rules configuration
  - Default: `True`

* **rule_18_4_4**: Rule or rules configuration
  - Default: `True`

* **rule_18_4_5**: Rule or rules configuration
  - Default: `True`

* **rule_18_4_6**: Rule or rules configuration
  - Default: `True`

* **rule_18_4_7**: Rule or rules configuration
  - Default: `True`

* **rule_18_4_8**: Rule or rules configuration
  - Default: `True`

* **rule_18_4_9**: Rule or rules configuration
  - Default: `True`

* **rule_18_4_10**: Rule or rules configuration
  - Default: `True`

* **rule_18_4_11**: Rule or rules configuration
  - Default: `True`

* **rule_18_4_12**: Rule or rules configuration
  - Default: `True`

* **rule_18_5_4_1**: Rule or rules configuration
  - Default: `True`

* **rule_18_5_4_2**: Rule or rules configuration
  - Default: `True`

* **rule_18_5_5_1**: Rule or rules configuration
  - Default: `True`

* **rule_18_5_8_1**: Rule or rules configuration
  - Default: `True`

* **rule_18_5_9_1**: Rule or rules configuration
  - Default: `True`

* **rule_18_5_9_2**: Rule or rules configuration
  - Default: `True`

* **rule_18_5_10_2**: Rule or rules configuration
  - Default: `True`

* **rule_18_5_11_2**: Rule or rules configuration
  - Default: `True`

* **rule_18_5_11_3**: Rule or rules configuration
  - Default: `True`

* **rule_18_5_11_4**: Rule or rules configuration
  - Default: `True`

* **rule_18_5_14_1**: Rule or rules configuration
  - Default: `True`

* **rule_18_5_19_2_1**: Rule or rules configuration
  - Default: `True`

* **rule_18_5_20_1**: Rule or rules configuration
  - Default: `True`

* **rule_18_5_20_2**: Rule or rules configuration
  - Default: `True`

* **rule_18_5_21_1**: Rule or rules configuration
  - Default: `True`

* **rule_18_5_21_2**: Rule or rules configuration
  - Default: `True`

* **rule_18_7_1_1**: Rule or rules configuration
  - Default: `True`

* **rule_18_8_3_1**: Rule or rules configuration
  - Default: `True`

* **rule_18_8_4_1**: Rule or rules configuration
  - Default: `True`

* **rule_18_8_4_2**: Rule or rules configuration
  - Default: `True`

* **rule_18_8_5_1**: Rule or rules configuration
  - Default: `True`

* **rule_18_8_5_2**: Rule or rules configuration
  - Default: `True`

* **rule_18_8_5_3**: Rule or rules configuration
  - Default: `True`

* **rule_18_8_5_4**: Rule or rules configuration
  - Default: `True`

* **rule_18_8_5_5**: Rule or rules configuration
  - Default: `True`

* **rule_18_8_5_6**: Rule or rules configuration
  - Default: `True`

* **rule_18_8_5_7**: Rule or rules configuration
  - Default: `True`

* **rule_18_8_14_1**: Rule or rules configuration
  - Default: `True`

* **rule_18_8_21_2**: Rule or rules configuration
  - Default: `True`

* **rule_18_8_21_3**: Rule or rules configuration
  - Default: `True`

* **rule_18_8_21_4**: Rule or rules configuration
  - Default: `True`

* **rule_18_8_21_5**: Rule or rules configuration
  - Default: `True`

* **rule_18_8_22_1_1**: Rule or rules configuration
  - Default: `True`

* **rule_18_8_22_1_2**: Rule or rules configuration
  - Default: `True`

* **rule_18_8_22_1_3**: Rule or rules configuration
  - Default: `True`

* **rule_18_8_22_1_4**: Rule or rules configuration
  - Default: `True`

* **rule_18_8_22_1_5**: Rule or rules configuration
  - Default: `True`

* **rule_18_8_22_1_6**: Rule or rules configuration
  - Default: `True`

* **rule_18_8_22_1_7**: Rule or rules configuration
  - Default: `True`

* **rule_18_8_22_1_8**: Rule or rules configuration
  - Default: `True`

* **rule_18_8_22_1_9**: Rule or rules configuration
  - Default: `True`

* **rule_18_8_22_1_10**: Rule or rules configuration
  - Default: `True`

* **rule_18_8_22_1_11**: Rule or rules configuration
  - Default: `True`

* **rule_18_8_22_1_12**: Rule or rules configuration
  - Default: `True`

* **rule_18_8_22_1_13**: Rule or rules configuration
  - Default: `True`

* **rule_18_8_25_1**: Rule or rules configuration
  - Default: `True`

* **rule_18_8_27_1**: Rule or rules configuration
  - Default: `True`

* **rule_18_8_28_1**: Rule or rules configuration
  - Default: `True`

* **rule_18_8_28_2**: Rule or rules configuration
  - Default: `True`

* **rule_18_8_28_3**: Rule or rules configuration
  - Default: `True`

* **rule_18_8_28_4**: Rule or rules configuration
  - Default: `True`

* **rule_18_8_28_5**: Rule or rules configuration
  - Default: `True`

* **rule_18_8_28_6**: Rule or rules configuration
  - Default: `True`

* **rule_18_8_28_7**: Rule or rules configuration
  - Default: `True`

* **rule_18_8_34_6_1**: Rule or rules configuration
  - Default: `True`

* **rule_18_8_34_6_2**: Rule or rules configuration
  - Default: `True`

* **rule_18_8_34_6_3**: Rule or rules configuration
  - Default: `True`

* **rule_18_8_34_6_4**: Rule or rules configuration
  - Default: `True`

* **rule_18_8_36_1**: Rule or rules configuration
  - Default: `True`

* **rule_18_8_36_2**: Rule or rules configuration
  - Default: `True`

* **rule_18_8_37_1**: Rule or rules configuration
  - Default: `True`

* **rule_18_8_37_2**: Rule or rules configuration
  - Default: `True`

* **rule_18_8_47_5_1**: Rule or rules configuration
  - Default: `True`

* **rule_18_8_47_11_1**: Rule or rules configuration
  - Default: `True`

* **rule_18_8_49_1**: Rule or rules configuration
  - Default: `True`

* **rule_18_8_52_1_1**: Rule or rules configuration
  - Default: `True`

* **rule_18_8_52_1_2**: Rule or rules configuration
  - Default: `True`

* **rule_18_9_4_1**: Rule or rules configuration
  - Default: `True`

* **rule_18_9_6_1**: Rule or rules configuration
  - Default: `True`

* **rule_18_9_8_1**: Rule or rules configuration
  - Default: `True`

* **rule_18_9_8_2**: Rule or rules configuration
  - Default: `True`

* **rule_18_9_8_3**: Rule or rules configuration
  - Default: `True`

* **rule_18_9_10_1_1**: Rule or rules configuration
  - Default: `True`

* **rule_18_9_12_1**: Rule or rules configuration
  - Default: `True`

* **rule_18_9_13_1**: Rule or rules configuration
  - Default: `True`

* **rule_18_9_14_1**: Rule or rules configuration
  - Default: `True`

* **rule_18_9_15_1**: Rule or rules configuration
  - Default: `True`

* **rule_18_9_15_2**: Rule or rules configuration
  - Default: `True`

* **rule_18_9_16_1**: Rule or rules configuration
  - Default: `True`

* **rule_18_9_16_2**: Rule or rules configuration
  - Default: `True`

* **rule_18_9_16_3**: Rule or rules configuration
  - Default: `True`

* **rule_18_9_16_4**: Rule or rules configuration
  - Default: `True`

* **rule_18_9_26_1_1**: Rule or rules configuration
  - Default: `True`

* **rule_18_9_26_1_2**: Rule or rules configuration
  - Default: `True`

* **rule_18_9_26_2_1**: Rule or rules configuration
  - Default: `True`

* **rule_18_9_26_2_2**: Rule or rules configuration
  - Default: `True`

* **rule_18_9_26_3_1**: Rule or rules configuration
  - Default: `True`

* **rule_18_9_26_3_2**: Rule or rules configuration
  - Default: `True`

* **rule_18_9_26_4_1**: Rule or rules configuration
  - Default: `True`

* **rule_18_9_26_4_2**: Rule or rules configuration
  - Default: `True`

* **rule_18_9_30_2**: Rule or rules configuration
  - Default: `True`

* **rule_18_9_30_3**: Rule or rules configuration
  - Default: `True`

* **rule_18_9_30_4**: Rule or rules configuration
  - Default: `True`

* **rule_18_9_39_1**: Rule or rules configuration
  - Default: `True`

* **rule_18_9_43_1**: Rule or rules configuration
  - Default: `True`

* **rule_18_9_44_1**: Rule or rules configuration
  - Default: `True`

* **rule_18_9_52_1**: Rule or rules configuration
  - Default: `True`

* **rule_18_9_59_2_2**: Rule or rules configuration
  - Default: `True`

* **rule_18_9_59_3_2_1**: Rule or rules configuration
  - Default: `True`

* **rule_18_9_59_3_3_1**: Rule or rules configuration
  - Default: `True`

* **rule_18_9_59_3_3_2**: Rule or rules configuration
  - Default: `True`

* **rule_18_9_59_3_3_3**: Rule or rules configuration
  - Default: `True`

* **rule_18_9_59_3_3_4**: Rule or rules configuration
  - Default: `True`

* **rule_18_9_59_3_9_1**: Rule or rules configuration
  - Default: `True`

* **rule_18_9_59_3_9_2**: Rule or rules configuration
  - Default: `True`

* **rule_18_9_59_3_9_3**: Rule or rules configuration
  - Default: `True`

* **rule_18_9_59_3_9_4**: Rule or rules configuration
  - Default: `True`

* **rule_18_9_59_3_9_5**: Rule or rules configuration
  - Default: `True`

* **rule_18_9_59_3_10_1**: Rule or rules configuration
  - Default: `True`

* **rule_18_9_59_3_10_2**: Rule or rules configuration
  - Default: `True`

* **rule_18_9_59_3_11_1**: Rule or rules configuration
  - Default: `True`

* **rule_18_9_59_3_11_2**: Rule or rules configuration
  - Default: `True`

* **rule_18_9_60_1**: Rule or rules configuration
  - Default: `True`

* **rule_18_9_61_2**: Rule or rules configuration
  - Default: `True`

* **rule_18_9_61_3**: Rule or rules configuration
  - Default: `True`

* **rule_18_9_66_1**: Rule or rules configuration
  - Default: `True`

* **rule_18_9_77_3_1**: Rule or rules configuration
  - Default: `True`

* **rule_18_9_77_3_2**: Rule or rules configuration
  - Default: `True`

* **rule_18_9_77_7_1**: Rule or rules configuration
  - Default: `True`

* **rule_18_9_77_9_1**: Rule or rules configuration
  - Default: `True`

* **rule_18_9_77_10_1**: Rule or rules configuration
  - Default: `True`

* **rule_18_9_77_10_2**: Rule or rules configuration
  - Default: `True`

* **rule_18_9_77_13_3_1**: Rule or rules configuration
  - Default: `True`

* **rule_18_9_77_14**: Rule or rules configuration
  - Default: `True`

* **rule_18_9_77_15**: Rule or rules configuration
  - Default: `True`

* **rule_18_9_80_1_1**: Rule or rules configuration
  - Default: `True`

* **rule_18_9_84_1**: Rule or rules configuration
  - Default: `True`

* **rule_18_9_84_2**: Rule or rules configuration
  - Default: `True`

* **rule_18_9_85_1**: Rule or rules configuration
  - Default: `True`

* **rule_18_9_85_2**: Rule or rules configuration
  - Default: `True`

* **rule_18_9_85_3**: Rule or rules configuration
  - Default: `True`

* **rule_18_9_86_1**: Rule or rules configuration
  - Default: `True`

* **rule_18_9_95_1**: Rule or rules configuration
  - Default: `True`

* **rule_18_9_95_2**: Rule or rules configuration
  - Default: `True`

* **rule_18_9_97_1_1**: Rule or rules configuration
  - Default: `True`

* **rule_18_9_97_1_2**: Rule or rules configuration
  - Default: `True`

* **rule_18_9_97_1_3**: Rule or rules configuration
  - Default: `True`

* **rule_18_9_97_2_1**: Rule or rules configuration
  - Default: `True`

* **rule_18_9_97_2_2**: Rule or rules configuration
  - Default: `True`

* **rule_18_9_97_2_3**: Rule or rules configuration
  - Default: `True`

* **rule_18_9_97_2_4**: Rule or rules configuration
  - Default: `True`

* **rule_18_9_98_1**: Rule or rules configuration
  - Default: `True`

* **rule_18_9_99_2_1**: Rule or rules configuration
  - Default: `True`

* **rule_18_9_102_1_1**: Rule or rules configuration
  - Default: `True`

* **rule_18_9_102_1_2**: Rule or rules configuration
  - Default: `True`

* **rule_18_9_102_1_3**: Rule or rules configuration
  - Default: `True`

* **rule_18_9_102_2**: Rule or rules configuration
  - Default: `True`

* **rule_18_9_102_3**: Rule or rules configuration
  - Default: `True`

* **rule_18_9_102_4**: Rule or rules configuration
  - Default: `True`

* **rule_19_1_3_1**: section19
  - Default: `True`

* **rule_19_1_3_2**: Rule or rules configuration
  - Default: `True`

* **rule_19_1_3_3**: Rule or rules configuration
  - Default: `True`

* **rule_19_1_3_4**: Rule or rules configuration
  - Default: `True`

* **rule_19_5_1_1**: Rule or rules configuration
  - Default: `True`

* **rule_19_6_6_1_1**: Rule or rules configuration
  - Default: `True`

* **rule_19_7_4_1**: Rule or rules configuration
  - Default: `True`

* **rule_19_7_4_2**: Rule or rules configuration
  - Default: `True`

* **rule_19_7_7_1**: Rule or rules configuration
  - Default: `True`

* **rule_19_7_7_2**: Rule or rules configuration
  - Default: `True`

* **rule_19_7_7_3**: Rule or rules configuration
  - Default: `True`

* **rule_19_7_7_4**: Rule or rules configuration
  - Default: `True`

* **rule_19_7_26_1**: Rule or rules configuration
  - Default: `True`

* **rule_19_7_41_1**: Rule or rules configuration
  - Default: `True`

* **rule_19_7_45_2_1**: Rule or rules configuration
  - Default: `True`

* **is_hyperv_installed**: is_hyperv_installed is a true/false for having hyper-visor installed
  - Default: `False`

* **win16cis_admin_username**: win16cis_admin_username is the name the administrator account will be renamed to
  - Default: `ansibleadmin`

* **win16cis_guest_username**: win16cis_guest_username is the name the guest account will be renamed to
  - Default: `ansibleguest`

* **sedebugprivilege**: This SID is the same for standalone, member, domain controller for 'Administrators' group
  - Default: `*S-1-5-32-544`

* **pass_age**: Configuration parameter for shadowman_cis_windows_2016
  - Default: `60`

* **lockoutduration**: Configuration parameter for shadowman_cis_windows_2016
  - Default: `15`

* **lockoutbadcount**: Numeric count or quantity
  - Default: `3`

* **resetlockoutcount**: Numeric count or quantity
  - Default: `15`

* **passwordhistorysize**: Password or authentication credential
  - Default: `24`

* **maximumpasswordage**: Password or authentication credential
  - Default: `60`

* **minimumpasswordage**: Password or authentication credential
  - Default: `1`

* **minimumpasswordlength**: Password or authentication credential
  - Default: `14`

* **laps_passwordlength**: To conform to CIS standards please use a min value of 15 and max value of 127
  - Default: `15`

* **laps_passwordagedays**: To conform to CIS standards please use a max value of 30
  - Default: `30`

* **newadministratorname**: Resource name
  - Default: `ansibleadmin`

* **newguestname**: Resource name
  - Default: `ansibleguest`

* **legalnoticetext**: Configuration parameter for shadowman_cis_windows_2016
  - Default: `You are accessing a U.S. Government (USG) Information System (IS) that is provided for USG-authorized use only.

By using this IS (which includes any device attached to this IS), you consent to the following conditions:

-The USG routinely intercepts and monitors communications on this IS for purposes including, but not limited to, penetration testing, COMSEC monitoring, network operations and defense, personnel misconduct (PM), law enforcement (LE), and counterintelligence (CI) investigations.

-At any time, the USG may inspect and seize data stored on this IS.

-Communications using, or data stored on, this IS are not private, are subject to routine monitoring, interception, and search, and may be disclosed or used for any USG-authorized purpose.

-This IS includes security measures (e.g., authentication and access controls) to protect USG interests--not for your personal benefit or privacy.

-Notwithstanding the above, using this IS does not constitute consent to PM, LE or CI investigative searching or monitoring of the content of privileged communications, or work product, related to personal representation or services by attorneys, psychotherapists, or clergy, and their assistants. Such communications and work product are private and confidential. See User Agreement for details.
`

* **app_maxsize**: Size specification
  - Default: `32768`

* **sec_maxsize**: Size specification
  - Default: `196608`

* **sys_maxsize**: Size specification
  - Default: `32768`

* **legalnoticecaption**: Configuration parameter for shadowman_cis_windows_2016
  - Default: `DoD Notice and Consent Banner`

* **domain_firewall_log_path**: This is a variable to give some leway on where to store these log files
  - Default: `%SystemRoot%\System32\logfiles\firewall\domainfw.log`

* **domain_firewall_log_size**: To conform to CIS standards the value should be 16,384 or greater. Value is in KB
  - Default: `16,384`

* **private_firewall_log_path**: This is a variable to give some leway on where to store these log files
  - Default: `%SystemRoot%\System32\logfiles\firewall\privatefw.log`

* **private_firewall_log_size**: To conform to CIS stadnards the value should be 16,384 or greater. Value is in KB
  - Default: `16,384`

* **public_firewall_log_path**: This is a variable to give some leway on where to store these log files
  - Default: `%SystemRoot%\System32\logfiles\firewall\publicfw.log`

* **public_firewall_log_size**: To conform to CIS stadnards the value should be 16,384 or greater. Value is in KB
  - Default: `16,384`

* **win16cis_wupdate_options**: value 7 - Auto download, notify to install, notify to restart
  - Default: `4`

Dependencies
------------

None

Example Playbook
----------------

```yaml
- hosts: all
  roles:
    - role: shadowman_cis_windows_2016
      vars:
        section01_patch: <value>
        section02_patch: <value>
        section09_patch: <value>
```

License
-------

GNU General Public License v3.0 or later

Author Information
------------------

Red Hat Ansible Automation Platform
