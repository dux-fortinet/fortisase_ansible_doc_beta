endpoint_ztna_rules - ZTNA Rule Resource
++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.0.0

.. contents::
   :local:
   :depth: 1

Synopsis
--------
ZTNA Rule Resource.

Use API "/resource-api/v2/endpoint/ztna-rules".

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
 <li><span class="li-head">status</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">tag</span> <span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">primary_key</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">datasource</span> <span class="li-normal">type: str</span></li>
 </ul></li>
 <li><span class="li-head">comments</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">rules</span> <span class="li-normal">type: list</span><span class="li-normal">elements: dict</span> <ul class="ul-self"> <li><span class="li-head">id</span> <span class="li-normal">type: int</span></li>
 <li><span class="li-head">os</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['android', 'ios', 'linux', 'macos', 'windows']</span></li>
 <li><span class="li-head">type</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['ad-groups', 'anti-virus', 'certificate', 'crowdstrike-zta-score', 'cve', 'ems-management', 'fct-version', 'file', 'ip-range', 'logged-in-domain', 'on-fabric-status', 'os-version', 'registry-key', 'running-process', 'sandbox-detection', 'security', 'security-status', 'user-identity', 'vulnerable-devices', 'windows-security']</span></li>
 <li><span class="li-head">service</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['Custom', 'Google', 'LinkedIn', 'Salesforce']</span></li>
 <li><span class="li-head">account</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">match_type</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['regex', 'simple', 'wildcard']</span></li>
 <li><span class="li-head">subject</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">issuer</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">content</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['AV Signature is up-to-date', 'AV Software is installed and running', 'Application Guard is enabled', 'Automatic Updates are enabled', 'Biometrics Protected', 'Bitlocker Disk Encryption is enabled on OS disk', 'Bitlocker Disk Encryption is enabled on all disks', 'Critical', 'Exploit Guard is enabled', 'High or higher', 'Jail-broken', 'Low or higher', 'Medium or higher', 'Passcode Enabled', 'Windows Defender is enabled', 'Windows Firewall is enabled']</span></li>
 <li><span class="li-head">path</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">negated</span> <span class="li-normal">type: bool</span></li>
 <li><span class="li-head">enable_latest_update_check</span> <span class="li-normal">type: bool</span></li>
 <li><span class="li-head">check_updates_within_days</span> <span class="li-normal">type: int</span></li>
 <li><span class="li-head">comparator</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['<', '<=', '=', '>', '>=']</span></li>
 <li><span class="li-head">condition</span> <span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">key</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">is_dword</span> <span class="li-normal">type: bool</span></li>
 <li><span class="li-head">comparator</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['!=', '<', '<=', '=', '>', '>=']</span></li>
 <li><span class="li-head">value</span> <span class="li-normal">type: str</span></li>
 </ul></li>
 </ul></li>
 <li><span class="li-head">logic</span> <span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">windows</span> <span class="li-normal">type: raw</span></li>
 <li><span class="li-head">macos</span> <span class="li-normal">type: raw</span></li>
 <li><span class="li-head">linux</span> <span class="li-normal">type: raw</span></li>
 <li><span class="li-head">ios</span> <span class="li-normal">type: raw</span></li>
 <li><span class="li-head">android</span> <span class="li-normal">type: raw</span></li>
 </ul></li>
 </ul></li>
 </ul>



Examples
-------------

.. code-block:: yaml

  - name: Ztna rule
    hosts: fortisase
    gather_facts: false
    vars:
      policy: "policy1"
      tag: "tag_example"
      rule_name: "rule_example"
    tasks:
      - name: Create a new endpoint profile, do nothing if the endpoint profile already exists
        fortinet.fortisase.endpoint_policies:
          state: present
          params:
            primaryKey: "{{ policy }}"
            enabled: true
      - name: Create/Update ztna tag, do nothing if the ztna tag already exists
        fortinet.fortisase.endpoint_ztna_tags:
          state: present
          params:
            primaryKey: "{{ tag }}"
            name: "{{ tag }}"
      - name: Create/Update ztna rule
        fortinet.fortisase.endpoint_ztna_rules:
          state: present
          params:
            primaryKey: "{{ rule_name }}"
            status: "enable" # "enable" or "disable"
            tag:
              primaryKey: "{{ tag }}"
              datasource: "endpoint/ztna-tags"
            comments: "example comment"
            rules:
              - os: "windows" # "windows", "macos", "linux", "ios", "android"
                type: "anti-virus"
                content: "AV Software is installed and running"
      - name: Delete ztna rule
        fortinet.fortisase.endpoint_ztna_rules:
          state: absent
          params:
            primaryKey: "{{ rule_name }}"
  


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

