endpoint_ztna_profiles - ZTNA Profile Resource
++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.0.0

.. contents::
   :local:
   :depth: 1

Synopsis
--------
ZTNA Profile Resource.

Use API "/resource-api/v2/endpoint/ztna-profiles/{primaryKey}".

Requirements
------------

The below requirements are needed on the host that executes this module.

- ansible>=2.17.0


Parameters
----------
.. raw:: html

 <ul>
 <li><span class="li-head">state</span> The state of the module. "present" means update the resource. This resource can't be deleted, and does not support "absent" state.<span class="li-normal">type: str</span><span class="li-normal">choices: ['present', 'absent']</span><span class="li-normal">default: present</span></li>
 <li><span class="li-head">force_behavior</span> Specify this option to force the method to use to interact with the resource.<span class="li-normal">type: str</span><span class="li-normal">choices: ['none', 'read', 'create', 'update', 'delete']</span><span class="li-normal">default: none</span></li>
 <li><span class="li-head">bypass_validation</span> Bypass validation of the module.<span class="li-normal">type: bool</span><span class="li-normal">default: False</span></li>
 <li><span class="li-head">params</span> The parameters of the module.<span class="li-required">[Required]</span><span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">primary_key</span> <span class="li-required">[Required]</span><span class="li-normal">type: str</span></li>
 <li><span class="li-head">allow_automatic_sign_on</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">connection_rules</span> <span class="li-normal">type: list</span><span class="li-normal">elements: dict</span> <ul class="ul-self"> <li><span class="li-head">id</span> <span class="li-normal">type: int</span></li>
 <li><span class="li-head">address</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">uid</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">gateways</span> <span class="li-normal">type: list</span><span class="li-normal">elements: dict</span> <ul class="ul-self"> <li><span class="li-head">alias</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">private_app_count</span> <span class="li-normal">type: int</span></li>
 <li><span class="li-head">vip</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">redirect</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 </ul></li>
 <li><span class="li-head">mask</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">port</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">name</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">encryption</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 </ul></li>
 <li><span class="li-head">entra_id</span> <span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">application_id</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">domain_name</span> <span class="li-normal">type: str</span></li>
 </ul></li>
 </ul></li>
 </ul>



Examples
-------------

.. code-block:: yaml

  - name: Endpoint ZTNA profiles
    hosts: fortisase
    gather_facts: false
    vars:
      primary_key: "policy1"
    tasks:
      - name: Create a new endpoint profile, do nothing if the endpoint profile already exists
        fortinet.fortisase.endpoint_policies:
          state: present
          params:
            primary_key: "{{ primaryKey }}"
            enabled: true
      - name: Enable endpoint ZTNA profiles
        fortinet.fortisase.endpoint_ztna_profiles:
          state: present
          params:
            primary_key: "{{ primaryKey }}"
            allow_automatic_sign_on: "enable"
            connection_rules:
              - id: 1
                address: "192.168.1.1"
                uid: "1"
                gateways: []
                mask: "255.255.255.0"
                name: "test"
                port: "80"
                encryption: "enable"
            entra_id:
              application_id: "0"
              domain_name: "0"
  


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

