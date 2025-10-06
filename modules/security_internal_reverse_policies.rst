security_internal_reverse_policies - Internal Reverse Policy Resource
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.0.0

.. contents::
   :local:
   :depth: 1

Synopsis
--------
Internal Reverse Policy Resource.

Use API "/resource-api/v2/security/internal-reverse-policies".

Requirements
------------

The below requirements are needed on the host that executes this module.

- ansible>=2.17.0


Parameters
----------
.. raw:: html

 <ul>
 <li><span class="li-head">state</span> The state of the module. "present" means create or update the resource, "absent" means delete the resource.<span class="li-normal">type: str</span><span class="li-normal">choices: ['present', 'absent']</span><span class="li-normal">default: present</span></li>
 <li><span class="li-head">force_behavior</span> Specify this option to force the method to use to interact with the resource.<span class="li-normal">type: str</span><span class="li-normal">choices: ['none', 'read', 'create', 'update', 'delete']</span><span class="li-normal">default: none</span></li>
 <li><span class="li-head">bypass_validation</span> Bypass validation of the module.<span class="li-normal">type: bool</span><span class="li-normal">default: False</span></li>
 <li><span class="li-head">params</span> The parameters of the module.<span class="li-required">[Required]</span><span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">primary_key</span> <span class="li-required">[Required]</span><span class="li-normal">type: str</span></li>
 <li><span class="li-head">enabled</span> <span class="li-normal">type: bool</span></li>
 <li><span class="li-head">scope</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['all', 'specify', 'thin-edge', 'vpn-user']</span></li>
 <li><span class="li-head">sources</span> <span class="li-normal">type: list</span><span class="li-normal">elements: dict</span> <ul class="ul-self"> <li><span class="li-head">primary_key</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">datasource</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['network/host-groups', 'network/hosts', 'security/ip-threat-feeds']</span></li>
 </ul></li>
 <li><span class="li-head">services</span> <span class="li-normal">type: list</span><span class="li-normal">elements: dict</span> <ul class="ul-self"> <li><span class="li-head">primary_key</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">datasource</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['security/service-groups', 'security/services']</span></li>
 </ul></li>
 <li><span class="li-head">action</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['accept', 'deny']</span></li>
 <li><span class="li-head">schedule</span> <span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">primary_key</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">datasource</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['security/onetime-schedules', 'security/recurring-schedules', 'security/schedule-groups']</span></li>
 </ul></li>
 <li><span class="li-head">comments</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">profile_group</span> <span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">group</span> <span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">primary_key</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">datasource</span> <span class="li-normal">type: str</span></li>
 </ul></li>
 <li><span class="li-head">force_cert_inspection</span> <span class="li-normal">type: bool</span></li>
 </ul></li>
 <li><span class="li-head">log_traffic</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['all', 'disable', 'utm']</span></li>
 <li><span class="li-head">destinations</span> <span class="li-normal">type: list</span><span class="li-normal">elements: dict</span> <ul class="ul-self"> <li><span class="li-head">primary_key</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">datasource</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['infra/extenders', 'infra/fortigates', 'infra/ssids', 'network/host-groups', 'network/hosts']</span></li>
 </ul></li>
 </ul></li>
 </ul>



Examples
-------------

.. code-block:: yaml

  - name: Security internal reverse policies
    hosts: fortisase
    gather_facts: false
    vars:
      primaryKey: "reverse_policy_ansible"
    tasks:
      - name: Create/Update security internal reverse policies
        fortinet.fortisase.security_internal_reverse_policies:
          state: present
          params:
            primaryKey: "{{ primaryKey }}"
            enabled: true
            scope: "vpn-user"
            services:
              - primaryKey: "SSH"
                datasource: "security/services"
              - primaryKey: "RDP"
                datasource: "security/services"
            action: "deny"
            logTraffic: "all"
            profileGroup:
              group:
                primaryKey: "internal"
                datasource: "security/profile-groups"
              forceCertInspection: false
            sources:
              - primaryKey: "gui_test"
                datasource: "network/hosts"
            schedule:
              primaryKey: "always"
              datasource: "security/recurring-schedules"
            comments: "Allow IT Admins remote access to machines of mobile workers"
      - name: Delete security internal reverse policies
        fortinet.fortisase.security_internal_reverse_policies:
          state: absent
          params:
            primaryKey: "{{ primaryKey }}"
  


Return Values
-------------
.. raw:: html

 <ul>
 <li><span class="li-head">http_code</span> <span class="li-normal">type: int</span><span class="li-normal">returned: always</span></li>
 <li><span class="li-head">response</span> <span class="li-normal">type: raw</span><span class="li-normal">returned: always</span></li>
 </ul>


Authors
-------

- Xinwei Du (@dux-fortinet)

