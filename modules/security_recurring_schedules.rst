security_recurring_schedules - Recurring Schedule Resource
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.0.0

.. contents::
   :local:
   :depth: 1

Synopsis
--------
Recurring Schedule Resource.

Use API "/resource-api/v2/security/recurring-schedules".

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
 <li><span class="li-head">days</span> <span class="li-normal">type: list</span><span class="li-normal">elements: str</span></li>
 <li><span class="li-head">start_time</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">end_time</span> <span class="li-normal">type: str</span></li>
 </ul></li>
 </ul>



Examples
-------------

.. code-block:: yaml

  - name: Security recurring schedules
    hosts: fortisase
    gather_facts: false
    vars:
      primaryKey: "recurring_schedule_ansible"
    tasks:
      - name: Create/Update security recurring schedules
        fortinet.fortisase.security_recurring_schedules:
          state: present
          params:
            primaryKey: "{{ primaryKey }}"
            days:
              - "sunday"
              - "monday"
              - "tuesday"
              - "wednesday"
              - "thursday"
              - "friday"
            endTime: "17:00"
            startTime: "09:01"
      - name: Delete security recurring schedules
        fortinet.fortisase.security_recurring_schedules:
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

