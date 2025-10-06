security_onetime_schedules - Onetime Schedule Resource
++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.0.0

.. contents::
   :local:
   :depth: 1

Synopsis
--------
Onetime Schedule Resource.

Use API "/resource-api/v2/security/onetime-schedules".

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
 <li><span class="li-head">expiration_days</span> <span class="li-normal">type: int</span></li>
 <li><span class="li-head">start_utc</span> <span class="li-normal">type: int</span></li>
 <li><span class="li-head">end_utc</span> <span class="li-normal">type: int</span></li>
 </ul></li>
 </ul>



Examples
-------------

.. code-block:: yaml

  - name: Security onetime schedules
    hosts: fortisase
    gather_facts: false
    vars:
      primary_key: "onetime_schedule_ansible"
    tasks:
      - name: Create/Update security onetime schedules
        fortinet.fortisase.security_onetime_schedules:
          state: present
          params:
            primary_key: "{{ primaryKey }}"
            start_utc: 1422835200
            end_utc: 1454371200
      - name: Delete security onetime schedules
        fortinet.fortisase.security_onetime_schedules:
          state: absent
          params:
            primary_key: "{{ primaryKey }}"
  


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

