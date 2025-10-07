endpoint_group_invitation_codes - Group-Based Invitation Code Resource
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.0.0

.. contents::
   :local:
   :depth: 1

Synopsis
--------
Group-Based Invitation Code Resource.

Use API "/resource-api/v2/endpoint/group-invitation-codes".

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
 <li><span class="li-head">expire_date</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">group_assignment</span> <span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">enabled</span> <span class="li-normal">type: bool</span></li>
 <li><span class="li-head">group</span> <span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">id</span> <span class="li-normal">type: int</span></li>
 <li><span class="li-head">path</span> <span class="li-normal">type: str</span></li>
 </ul></li>
 </ul></li>
 </ul></li>
 </ul>



Examples
-------------

.. code-block:: yaml

  - name: Endpoint group invitation codes
    hosts: fortisase
    gather_facts: false
    vars:
      primary_key: "group1"
    tasks:
      - name: Create/Update endpoint group invitation codes
        fortinet.fortisase.endpoint_group_invitation_codes:
          state: present
          params:
            primary_key: "{{ primary_key }}"
            expire_date: "2026-03-08T12:45:30Z"
            group_assignment:
              enabled: true
              group:
                id: "1"
                path: "All Groups"
      - name: Delete endpoint group invitation codes
        fortinet.fortisase.endpoint_group_invitation_codes:
          state: absent
          params:
            primary_key: "{{ primary_key }}"
  


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

