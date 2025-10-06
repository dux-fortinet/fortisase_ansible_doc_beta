security_dlp_dictionaries - DLP Dictionary Resource
+++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.0.0

.. contents::
   :local:
   :depth: 1

Synopsis
--------
DLP Dictionary Resource.

Use API "/resource-api/v2/security/dlp-dictionaries".

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
 <li><span class="li-head">dictionary_type</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['mip-label', 'sensor']</span></li>
 <li><span class="li-head">sensitivity_label_guid</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">entries_to_evaluate</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['all', 'any']</span></li>
 <li><span class="li-head">entries</span> <span class="li-normal">type: list</span><span class="li-normal">elements: dict</span> <ul class="ul-self"> <li><span class="li-head">dlp_data_type</span> <span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">primary_key</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">datasource</span> <span class="li-normal">type: str</span></li>
 </ul></li>
 <li><span class="li-head">status</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">repeat</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">pattern</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">case_sensitive</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 </ul></li>
 </ul></li>
 </ul>



Examples
-------------

.. code-block:: yaml

  - name: Security DLP Dictionaries
    hosts: fortisase
    gather_facts: false
    vars:
      primaryKey: "asbdictionaries"
    tasks:
      - name: Create/Update Security DLP Dictionaries
        fortinet.fortisase.security_dlp_dictionaries:
          state: present
          params:
            primaryKey: "{{ primaryKey }}"
            dictionaryType: "sensor"
            entriesToEvaluate: "all"
            entries:
              - dlpDataType:
                  primaryKey: "regex"
                  datasource: "security/dlp-data-types"
                pattern: "string"
                status: "enable"
                repeat: "enable"
      - name: Delete Security DLP Dictionaries
        fortinet.fortisase.security_dlp_dictionaries:
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

