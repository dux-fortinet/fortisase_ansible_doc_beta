security_endpoint_to_endpoint_policies - Endpoint to Endpoint Policy Resource
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.0.0

.. contents::
   :local:
   :depth: 1

Synopsis
--------
Endpoint to Endpoint Policy Resource.

Use API "/resource-api/v2/security/endpoint-to-endpoint-policies".

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
 <li><span class="li-head">params</span> The parameters of the module.<span class="li-required">[Required]</span><span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">primaryKey</span> <span class="li-required">[Required]</span><span class="li-normal">type: str</span></li>
 <li><span class="li-head">enabled</span> <span class="li-normal">type: bool</span></li>
 <li><span class="li-head">users</span> <span class="li-normal">type: list</span><span class="li-normal">elements: dict</span> <ul class="ul-self"> <li><span class="li-head">primaryKey</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">datasource</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['auth/ad-groups', 'auth/user-groups', 'auth/users']</span></li>
 </ul></li>
 <li><span class="li-head">sources</span> <span class="li-normal">type: list</span><span class="li-normal">elements: dict</span> <ul class="ul-self"> <li><span class="li-head">primaryKey</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">datasource</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['endpoint/ztna-tags']</span></li>
 </ul></li>
 <li><span class="li-head">services</span> <span class="li-normal">type: list</span><span class="li-normal">elements: dict</span> <ul class="ul-self"> <li><span class="li-head">primaryKey</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">datasource</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['security/service-groups', 'security/services']</span></li>
 </ul></li>
 <li><span class="li-head">action</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['accept', 'deny']</span></li>
 <li><span class="li-head">schedule</span> <span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">primaryKey</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">datasource</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['security/onetime-schedules', 'security/recurring-schedules', 'security/schedule-groups']</span></li>
 </ul></li>
 <li><span class="li-head">comments</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">profileGroup</span> <span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">group</span> <span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">primaryKey</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">datasource</span> <span class="li-normal">type: str</span></li>
 </ul></li>
 <li><span class="li-head">forceCertInspection</span> <span class="li-normal">type: bool</span></li>
 </ul></li>
 <li><span class="li-head">logTraffic</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['all', 'disable', 'utm']</span></li>
 </ul></li>
 </ul>



Examples
-------------

.. code-block:: yaml

  - name: Security endpoint to endpoint policies
    hosts: fortisase
    gather_facts: false
    vars:
      primaryKey: "saas_app_ansible"
    tasks:
      - name: Create/Update security endpoint to endpoint policies
        fortinet.fortisase.security_endpoint_to_endpoint_policies:
          state: present
          params:
            primaryKey: "{{ primaryKey }}"
            enabled: true
            users:
              - primaryKey: "gui_test"
                datasource: "auth/user-groups"
            services:
              - primaryKey: "ALL_TCP"
                datasource: "security/services"
            action: "accept"
            logTraffic: "all"
            schedule:
              primaryKey: "always"
              datasource: "security/recurring-schedules"
      - name: Delete security endpoint to endpoint policies
        fortinet.fortisase.security_endpoint_to_endpoint_policies:
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

