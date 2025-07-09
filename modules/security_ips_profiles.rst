security_ips_profiles - IPS Profile Resource API V2 for FortiSASE
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.0.0

.. contents::
   :local:
   :depth: 1

Synopsis
--------
IPS Profile Resource API V2 for FortiSASE

Requirements
------------

The below requirements are needed on the host that executes this module.

- ansible>=2.15.0


Parameters
----------
.. raw:: html

 <ul>
 <li><span class="li-head">state</span> The state of the module.<span class="li-normal">type: str</span><span class="li-normal">choices: ['present', 'absent']</span><span class="li-normal">default: present</span></li>
 <li><span class="li-head">force_method</span> Specify this option to force the method to use to interact with the resource.<span class="li-normal">type: str</span><span class="li-normal">choices: ['none', 'read', 'create', 'update', 'delete']</span><span class="li-normal">default: none</span></li>
 <li><span class="li-head">bypass_validation</span> Bypass validation of the module.<span class="li-normal">type: bool</span><span class="li-normal">default: False</span></li>
 <li><span class="li-head">params</span> The parameters of the module.<span class="li-normal">type: dict</span><span class="li-normal">required: True</span></li>
 <ul class="ul-self"> <li><span class="li-head">primaryKey</span> <span class="li-normal">type: str</span><span class="li-normal">required: True</span></li>
 <li><span class="li-head">profileType</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['critical', 'custom', 'monitor', 'recommended']</span></li>
 <li><span class="li-head">customRuleGroups</span> <span class="li-normal">type: list</span></li>
 <li><span class="li-head">isBlockingMaliciousUrl</span> <span class="li-normal">type: bool</span></li>
 <li><span class="li-head">botnetScanning</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['block', 'disable', 'monitor']</span></li>
 <li><span class="li-head">isExtendedLogEnabled</span> <span class="li-normal">type: bool</span></li>
 <li><span class="li-head">comment</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">entries</span> <span class="li-normal">type: list</span></li>
 </ul> </ul>



Examples
-------------

.. code-block:: yaml

  - name: Update security ips profiles
    hosts: fortisase
    gather_facts: false
    tasks:
      - name: Update security ips profiles
        fortinet.fortisase.security_ips_profiles:
          params:
            primaryKey: "outbound" # internal or outbound
            botnetScanning: "block"
            comment: "Recommended"
            customRuleGroups: []
            entries:
              - action: "default"
                application: "all"
                cve: []
                defaultAction: "all"
                defaultStatus: "all"
                exempt-ip: []
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

