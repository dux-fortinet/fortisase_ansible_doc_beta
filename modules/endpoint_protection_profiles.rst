endpoint_protection_profiles - Protection Profile Resource
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.0.0

.. contents::
   :local:
   :depth: 1

Synopsis
--------
Protection Profile Resource.

Use API "/resource-api/v2/endpoint/protection-profiles/{primaryKey}".

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
 <li><span class="li-head">antivirus</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">antiransomware</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">event_based_scanning</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">vulnerability_scan</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">automatically_patch_vulnerabilities</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">automatic_vulnerability_patch_level</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['critical', 'high', 'low', 'medium']</span></li>
 <li><span class="li-head">notify_endpoint_of_blocks</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">default_action</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['allow', 'block', 'monitor']</span></li>
 <li><span class="li-head">rules</span> <span class="li-normal">type: list</span><span class="li-normal">elements: dict</span> <ul class="ul-self"> <li><span class="li-head">action</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['allow', 'block', 'monitor']</span></li>
 <li><span class="li-head">type</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['regex', 'simple']</span></li>
 <li><span class="li-head">description</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">class</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['Bluetooth', 'CDROM', 'Camera', 'HID', 'SmartCardReader', 'USBDevice', 'WPD']</span></li>
 <li><span class="li-head">manufacturer</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">vendor_id</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">product_id</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">revision</span> <span class="li-normal">type: str</span></li>
 </ul></li>
 <li><span class="li-head">exclusions</span> <span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">files</span> <span class="li-normal">type: list</span><span class="li-normal">elements: str</span></li>
 <li><span class="li-head">folders</span> <span class="li-normal">type: list</span><span class="li-normal">elements: str</span></li>
 </ul></li>
 <li><span class="li-head">protected_folders_path</span> <span class="li-normal">type: list</span><span class="li-normal">elements: str</span></li>
 <li><span class="li-head">scheduled_scan</span> <span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">time</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">repeat</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['daily', 'monthly', 'weekly']</span></li>
 <li><span class="li-head">day</span> <span class="li-normal">type: int</span></li>
 </ul></li>
 </ul></li>
 </ul>



Examples
-------------

.. code-block:: yaml

  - name: Update protection profile
    hosts: fortisase
    gather_facts: false
    vars:
      primary_key: "policy1"
    tasks:
      - name: Create a new endpoint profile, do nothing if the endpoint profile already exists
        fortinet.fortisase.endpoint_policies:
          state: present
          params:
            primary_key: "{{ primary_key }}"
            enabled: true
      - name: Update protection profile
        fortinet.fortisase.endpoint_protection_profiles:
          params:
            primary_key: "{{ primary_key }}"
            antiransomware: "disable"
            antivirus: "enable"
            automatically_patch_vulnerabilities: "disable"
            default_action: "allow"
            event_based_scanning: "enable"
            notify_endpoint_of_blocks: "enable"
            rules: []
            scheduled_scan:
              day: 1
              repeat: "weekly"
              time: "00:00"
            vulnerability_scan: "enable"
  


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

