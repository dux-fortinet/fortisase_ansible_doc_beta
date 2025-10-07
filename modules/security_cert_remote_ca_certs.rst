security_cert_remote_ca_certs - Certificate Resource
++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.0.0

.. contents::
   :local:
   :depth: 1

Synopsis
--------
Certificate Resource.

Use API "/resource-api/v1/security/cert/remote-ca-certs".

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
 <li><span class="li-head">cert_name</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">file_content</span> <span class="li-normal">type: str</span></li>
 </ul></li>
 </ul>



Examples
-------------

.. code-block:: yaml

  - name: Security Certificate Remote CA Certificates
    hosts: fortisase
    gather_facts: false
    vars:
      primary_key: "example_remote_ca_certs"
    tasks:
      - name: Create/Update Security Certificate Remote CA Certificates
        fortinet.fortisase.security_cert_remote_ca_certs:
          state: present
          params:
            primary_key: "{{ primary_key }}"
            cert_name: "{{ primary_key }}"
            file_content: "{{ lookup('file', 'cert2.crt') | b64encode }}"
      - name: Delete Security Certificate Remote CA Certificates
        fortinet.fortisase.security_cert_remote_ca_certs:
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

