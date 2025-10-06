endpoint_sandbox_profiles - Sandbox Profile Resource
++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.0.0

.. contents::
   :local:
   :depth: 1

Synopsis
--------
Sandbox Profile Resource.

Use API "/resource-api/v2/endpoint/sandbox-profiles/{primaryKey}".

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
 <li><span class="li-head">sandbox_mode</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['Disabled', 'FortiSASE', 'StandaloneFortiSandbox']</span></li>
 <li><span class="li-head">notification_type</span> Integer representing how notifications should be handled on FortiSandbox file submission. 0 - display notification balloon when malware is detected in a submission. 1 - display a popup for all file submissions.<span class="li-normal">type: raw</span><span class="li-normal">choices: ['0', '1']</span></li>
 <li><span class="li-head">timeout_awaiting_sandbox_results</span> <span class="li-normal">type: int</span></li>
 <li><span class="li-head">file_submission_options</span> <span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">all_email_downloads</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">all_files_mapped_network_drives</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">all_files_removable_media</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">all_web_downloads</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 </ul></li>
 <li><span class="li-head">detection_verdict_level</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['Clean', 'High', 'Low', 'Malicious', 'Medium']</span></li>
 <li><span class="li-head">exceptions</span> <span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">exclude_files_from_trusted_sources</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">files</span> <span class="li-normal">type: list</span><span class="li-normal">elements: str</span></li>
 <li><span class="li-head">folders</span> <span class="li-normal">type: list</span><span class="li-normal">elements: str</span></li>
 </ul></li>
 <li><span class="li-head">remediation_actions</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['alert', 'quarantine']</span></li>
 <li><span class="li-head">host_name</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">authentication</span> <span class="li-normal">type: bool</span></li>
 <li><span class="li-head">username</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">password</span> <span class="li-normal">type: str</span></li>
 </ul></li>
 </ul>



Examples
-------------

.. code-block:: yaml

  - name: Update sandbox profile
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
      - name: Update sandbox profile
        fortinet.fortisase.endpoint_sandbox_profiles:
          params:
            primary_key: "{{ primaryKey }}"
            sandbox_mode: "FortiSASE"  # Disabled, FortiSASE, StandaloneFortiSandbox
            detection_verdict_level: "Medium"
            exceptions:
              exclude_files_from_trusted_sources: "disable"
              files: []
              folders: []
            file_submission_options:
              all_email_downloads: "enable"
              all_files_mapped_network_drives: "enable"
              all_files_removable_media: "enable"
              all_web_downloads: "enable"
            remediation_actions: "quarantine"
            timeout_awaiting_sandbox_results: 0
  


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

