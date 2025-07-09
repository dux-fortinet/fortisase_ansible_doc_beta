endpoint_protection_profiles - Protection Profile Resource API V2 for FortiSASE
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.0.0

.. contents::
   :local:
   :depth: 1

Synopsis
--------
Protection Profile Resource API V2 for FortiSASE

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
 <li><span class="li-head">antivirus</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">antiransomware</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">eventBasedScanning</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">vulnerabilityScan</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">automaticallyPatchVulnerabilities</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">automaticVulnerabilityPatchLevel</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['critical', 'high', 'low', 'medium']</span></li>
 <li><span class="li-head">notifyEndpointOfBlocks</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">defaultAction</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['allow', 'block', 'monitor']</span></li>
 <li><span class="li-head">rules</span> <span class="li-normal">type: list</span></li>
 <li><span class="li-head">protectedFoldersPath</span> <span class="li-normal">type: list</span></li>
 <li><span class="li-head">scheduledScan</span> <span class="li-normal">type: dict</span></li>
 </ul> </ul>



Examples
-------------

.. code-block:: yaml

  - name: Update policy protection profiles
    hosts: fortisase
    gather_facts: false
    tasks:
      - name: Create policies, do nothing if already exists
        fortinet.fortisase.endpoint_policies:
          state: present
          params:
            primaryKey: "policy1"
            enabled: true
      - name: Update policy protection profiles
        fortinet.fortisase.endpoint_protection_profiles:
          params:
            primaryKey: "policy1"
            antiransomware: "disable"
            antivirus: "enable"
            automaticallyPatchVulnerabilities: "disable"
            defaultAction: "allow"
            eventBasedScanning: "enable"
            notifyEndpointOfBlocks: "enable"
            rules: []
            scheduledScan:
              day: 1
              repeat: "weekly"
              time: "00:00"
            vulnerabilityScan: "enable"
  


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

