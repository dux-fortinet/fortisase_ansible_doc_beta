security_ips_profile - IPS Profile Resource
+++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.0.0

.. contents::
   :local:
   :depth: 1

Synopsis
--------
IPS Profile Resource.

Use API "/resource-api/v2/security/ips-profile/{direction}/{primaryKey}".

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
 <li><span class="li-head">params</span> The parameters of the module.<span class="li-required">[Required]</span><span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">direction</span> <span class="li-required">[Required]</span><span class="li-normal">type: str</span></li>
 <li><span class="li-head">primary_key</span> <span class="li-required">[Required]</span><span class="li-normal">type: str</span></li>
 <li><span class="li-head">profile_type</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['critical', 'custom', 'monitor', 'recommended']</span></li>
 <li><span class="li-head">custom_rule_groups</span> <span class="li-normal">type: list</span><span class="li-normal">elements: dict</span> <ul class="ul-self"> <li><span class="li-head">action</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['allow', 'block', 'monitor']</span></li>
 <li><span class="li-head">signatures</span> <span class="li-normal">type: list</span><span class="li-normal">elements: dict</span> <ul class="ul-self"> <li><span class="li-head">primary_key</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">datasource</span> <span class="li-normal">type: str</span></li>
 </ul></li>
 </ul></li>
 <li><span class="li-head">is_blocking_malicious_url</span> <span class="li-normal">type: bool</span></li>
 <li><span class="li-head">botnet_scanning</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['block', 'disable', 'monitor']</span></li>
 <li><span class="li-head">is_extended_log_enabled</span> <span class="li-normal">type: bool</span></li>
 <li><span class="li-head">comment</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">entries</span> <span class="li-normal">type: list</span><span class="li-normal">elements: dict</span> <ul class="ul-self"> <li><span class="li-head">rule</span> <span class="li-normal">type: list</span><span class="li-normal">elements: dict</span> <ul class="ul-self"> <li><span class="li-head">primary_key</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">datasource</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['security/ips-custom-signatures', 'security/ips-rule']</span></li>
 </ul></li>
 <li><span class="li-head">location</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">severity</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">protocol</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">os</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">application</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">cve</span> <span class="li-normal">type: list</span><span class="li-normal">elements: str</span></li>
 <li><span class="li-head">status</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['default', 'disable', 'enable']</span></li>
 <li><span class="li-head">log</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">log_packet</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">log_attack_context</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">action</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['block', 'default', 'pass']</span></li>
 <li><span class="li-head">vuln_type</span> <span class="li-normal">type: list</span><span class="li-normal">elements: dict</span> <ul class="ul-self"> <li><span class="li-head">id</span> <span class="li-normal">type: int</span></li>
 </ul></li>
 <li><span class="li-head">quarantine</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">exempt_ip</span> <span class="li-normal">type: list</span><span class="li-normal">elements: dict</span> <ul class="ul-self"> <li><span class="li-head">id</span> <span class="li-normal">type: int</span></li>
 <li><span class="li-head">src_ip</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">dst_ip</span> <span class="li-normal">type: str</span></li>
 </ul></li>
 <li><span class="li-head">default_action</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['all', 'block', 'pass']</span></li>
 <li><span class="li-head">default_status</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['all', 'disable', 'enable']</span></li>
 </ul></li>
 </ul></li>
 </ul>



Examples
-------------

.. code-block:: yaml

  - name: Update security ips profile
    hosts: fortisase
    gather_facts: false
    vars:
      direction: "outbound-profiles" # outbound-profiles or internal-profiles
      profile_group: "profile_ansible"
    tasks:
      - name: Ensure security group exists, otherwise create it
        fortinet.fortisase.security_profile_group:
          params:
            direction: "{{ direction }}"
            primaryKey: "{{ profile_group }}"
      - name: Update security ips profile
        fortinet.fortisase.security_ips_profile:
          params:
            direction: "{{ direction }}"
            primaryKey: "{{ profile_group }}"
            botnetScanning: "block"
            comment: "Recommended"
            customRuleGroups: []
            entries:
              - action: "default"
                application: "all"
                cve: []
                defaultAction: "all"
                defaultStatus: "all"
                exempt_ip: []
                location: "all"
                log: "enable"
                logAttackContext: "disable"
                logPacket: "disable"
                os: "all"
                protocol: "all"
                quarantine: "none"
                rule: []
                severity: "all"
                status: "default"
                vulnType: []
            isBlockingMaliciousUrl: false
            isExtendedLogEnabled: false
            profileType: "recommended"
  


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

