endpoint_group_ad_user_profiles - Group & AD Users Profile Resource
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.0.0

.. contents::
   :local:
   :depth: 1

Synopsis
--------
Group & AD Users Profile Resource.

Use API "/resource-api/v2/endpoint/group-ad-user-profiles/{primaryKey}".

Requirements
------------

The below requirements are needed on the host that executes this module.

- ansible>=2.17.0


Parameters
----------
.. raw:: html

 <ul>
 <li><span class="li-head">state</span> The state of the module. "present" means update the resource. This resource can't be deleted, and does not support "absent" state.<span class="li-normal">type: str</span><span class="li-normal">choices: ['present', 'absent']</span><span class="li-normal">default: present</span></li>
 <li><span class="li-head">force_method</span> Specify this option to force the method to use to interact with the resource.<span class="li-normal">type: str</span><span class="li-normal">choices: ['none', 'get', 'post', 'put', 'delete']</span><span class="li-normal">default: none</span></li>
 <li><span class="li-head">bypass_validation</span> Bypass validation of the module.<span class="li-normal">type: bool</span><span class="li-normal">default: False</span></li>
 <li><span class="li-head">params</span> The parameters of the module.<span class="li-required">[Required]</span><span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">primaryKey</span> <span class="li-required">[Required]</span><span class="li-normal">type: str</span></li>
 <li><span class="li-head">adUserIds</span> <span class="li-normal">type: list</span><span class="li-normal">elements: int</span></li>
 <li><span class="li-head">groupIds</span> <span class="li-normal">type: list</span><span class="li-normal">elements: int</span></li>
 </ul></li>
 </ul>



Examples
-------------

.. code-block:: yaml

  - name: Update group ad user profile
    hosts: fortisase
    gather_facts: false
    tasks:
      - name: Create a new endpoint profile, do nothing if the endpoint profile already exists
        fortinet.fortisase.endpoint_policies:
          state: present
          params:
            primaryKey: "policy1"
            enabled: true
      - name: Update group ad user profile
        fortinet.fortisase.endpoint_group_ad_user_profiles:
          params:
            primaryKey: "policy1"
            adUserIds: []
            groupIds: []
  


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

