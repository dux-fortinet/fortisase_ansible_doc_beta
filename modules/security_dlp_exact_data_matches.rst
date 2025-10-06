security_dlp_exact_data_matches - DLP Exact Data Match Resource
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.0.0

.. contents::
   :local:
   :depth: 1

Synopsis
--------
DLP Exact Data Match Resource.

Use API "/resource-api/v2/security/dlp-exact-data-matches".

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
 <li><span class="li-head">external_resource_data</span> <span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">resource</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">refresh_rate</span> <span class="li-normal">type: int</span></li>
 <li><span class="li-head">username</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">password</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">update_method</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['feed', 'push']</span></li>
 </ul></li>
 <li><span class="li-head">columns</span> <span class="li-normal">type: list</span><span class="li-normal">elements: dict</span> <ul class="ul-self"> <li><span class="li-head">index</span> <span class="li-normal">type: int</span></li>
 <li><span class="li-head">type</span> <span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">primary_key</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">datasource</span> <span class="li-normal">type: str</span></li>
 </ul></li>
 <li><span class="li-head">optional</span> <span class="li-normal">type: bool</span></li>
 </ul></li>
 <li><span class="li-head">optional_count</span> <span class="li-normal">type: int</span></li>
 </ul></li>
 </ul>



Examples
-------------

.. code-block:: yaml

  - name: Security DLP Exact Data Matches
    hosts: fortisase
    gather_facts: false
    vars:
      primary_key: "asbmatches"
    tasks:
      - name: Create/Update Security DLP Exact Data Matches
        fortinet.fortisase.security_dlp_exact_data_matches:
          state: present
          params:
            primary_key: "{{ primaryKey }}"
            external_resource_data:
              resource: "https://example-resource.com"
              username: "admin"
              password: "password123"
              refresh_rate: 3600
              update_method: "feed"
            optional_count: 0
            columns:
              - index: 1
                optional: false
                type:
                  datasource: "security/dlp-data-types"
                  primary_key: "credit-card"
      - name: Delete Security DLP Exact Data Matches
        fortinet.fortisase.security_dlp_exact_data_matches:
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

