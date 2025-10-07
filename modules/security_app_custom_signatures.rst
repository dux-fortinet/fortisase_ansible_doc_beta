security_app_custom_signatures - Custom Application Signature Resource
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.0.0

.. contents::
   :local:
   :depth: 1

Synopsis
--------
Custom Application Signature Resource.

Use API "/resource-api/v2/security/app-custom-signatures".

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
 <li><span class="li-head">signature</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">comment</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">id</span> <span class="li-normal">type: int</span></li>
 <li><span class="li-head">tag</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">name</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">category</span> <span class="li-normal">type: int</span></li>
 <li><span class="li-head">protocol</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">technology</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">behavior</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">vendor</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">icon_class</span> <span class="li-normal">type: str</span></li>
 </ul></li>
 </ul>



Examples
-------------

.. code-block:: yaml

  - name: Security Application Custom Signatures
    hosts: fortisase
    gather_facts: false
    vars:
      primary_key: "asbsignatures"
    tasks:
      - name: Create/Update Security Application Custom Signatures
        fortinet.fortisase.security_app_custom_signatures:
          state: present
          params:
            primary_key: "{{ primary_key }}"
            signature: "{{ lookup('file', 'signature.txt') }}"
            tag: "customsignature_example"
      - name: Delete Security Application Custom Signatures
        fortinet.fortisase.security_app_custom_signatures:
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

