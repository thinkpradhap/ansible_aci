0.virtualenv:
-----------

source vpod_check/bin/activate

1. How to run Ansible Playbook for all vPOD's (infra ping check + ping from leaf to External IP's):
--------------------------------------------------------------------------------------------------

ansible-playbook -i <inventory file> <playbook name>

For Eg.,
ansible-playbook -i pod8-aci-inventory vpod-sanity-check.yml

2. How to run Ansible Playbook for infra Ping Only:
---------------------------------------------------
- It will SSH to infra node and do ping from Infra node to all vPOD GW's (SVI)

For Eg.,
ansible-playbook -i pod8-aci-inventory vpod-sanity-check.yml --tags "infra_ping_all_vpods"

3. Ansible Playbook for ping from vPOD specific leaf to External IP's:
---------------------------------------------------------------------

vPOD0:
-----

ansible-playbook -i pod8-aci-inventory vpod-sanity-check.yml --tags "vpod0_leaf_ping_out"

vPOD1-CP:
---------

ansible-playbook -i pod8-aci-inventory vpod-sanity-check.yml --tags "vpod1_cp_leaf_ping_out"

vPOD1-DP:
---------

ansible-playbook -i pod8-aci-inventory vpod-sanity-check.yml --tags "vpod1_dp_leaf_ping_out"

vPOD2:
------

ansible-playbook -i pod8-aci-inventory vpod-sanity-check.yml --tags "vpod2_leaf_ping_out"

vPOD2 (CEPH GW's):
------------------

ansible-playbook -i pod8-aci-inventory vpod-sanity-check.yml --tags "vpod2_ceph_leaf_ping_out"

vPOD3:
------

ansible-playbook -i pod8-aci-inventory vpod-sanity-check.yml --tags "vpod3_leaf_ping_out"

vPOD100-CP:
-----------

ansible-playbook -i pod8-aci-inventory vpod-sanity-check.yml --tags "vpod100_leaf_ping_out"

vPOD101-CP:
-----------

ansible-playbook -i pod8-aci-inventory vpod-sanity-check.yml --tags "vpod101_cp_leaf_ping_out"

vPOD101-DP:
-----------

ansible-playbook -i pod8-aci-inventory vpod-sanity-check.yml --tags "vpod101_dp_leaf_ping_out"

