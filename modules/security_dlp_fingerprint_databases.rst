security_dlp_fingerprint_databases - DLP Fingerprint Database Resource
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.0.0

.. contents::
   :local:
   :depth: 1

Synopsis
--------
DLP Fingerprint Database Resource.

Use API "/resource-api/v2/security/dlp-fingerprint-databases".

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
 <li><span class="li-head">server</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">sensitivity</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['Critical', 'Private', 'Warning']</span></li>
 <li><span class="li-head">include_subdirectories</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">server_directory</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">file_pattern</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">schedule</span> <span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">period</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['daily', 'monthly', 'weekly']</span></li>
 <li><span class="li-head">sync_hour</span> <span class="li-normal">type: int</span></li>
 <li><span class="li-head">sync_minute</span> <span class="li-normal">type: int</span></li>
 <li><span class="li-head">weekday</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['friday', 'monday', 'saturday', 'sunday', 'thursday', 'tuesday', 'wednesday']</span></li>
 <li><span class="li-head">sync_day_of_the_month</span> <span class="li-normal">type: int</span></li>
 </ul></li>
 <li><span class="li-head">remove_deleted_file_fingerprints</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">keep_modified</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">scan_on_creation</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">authentication</span> <span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">username</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">password</span> <span class="li-normal">type: str</span></li>
 </ul></li>
 </ul></li>
 </ul>



Examples
-------------

.. code-block:: yaml

  - name: Security DLP Fingerprint Databases
    hosts: fortisase
    gather_facts: false
    vars:
      primary_key: "asbdatabases"
    tasks:
      - name: Create/Update Security DLP Fingerprint Databases
        fortinet.fortisase.security_dlp_fingerprint_databases:
          state: present
          params:
            primary_key: "{{ primaryKey }}"
            server: "example-server.com"
            sensitivity: "Warning"
            include_subdirectories: "enable"
            server_directory: "/path/to/directory/"
            file_pattern: "*.txt"
            schedule:
              period: "daily"
              sync_hour: 2
              sync_minute: 0
            remove_deleted_file_fingerprints: "enable"
            keep_modified: "enable"
            scan_on_creation: "enable"
            authentication:
              username: "admin"
              password: "password123"
      - name: Delete Security DLP Fingerprint Databases
        fortinet.fortisase.security_dlp_fingerprint_databases:
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

