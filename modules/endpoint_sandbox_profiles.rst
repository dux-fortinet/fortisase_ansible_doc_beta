endpoint_sandbox_profiles - Sandbox Profile Resource API V2 for FortiSASE
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.0.0

.. contents::
   :local:
   :depth: 1

Synopsis
--------
Sandbox Profile Resource API V2 for FortiSASE

Requirements
------------

The below requirements are needed on the host that executes this module.

- ansible>=2.17.0


Parameters
----------
.. raw:: html

 <ul>
 <li><span class="li-head">state</span> The state of the module.<span class="li-normal">type: str</span><span class="li-normal">choices: ['present', 'absent']</span><span class="li-normal">default: present</span></li>
 <li><span class="li-head">force_method</span> Specify this option to force the method to use to interact with the resource.<span class="li-normal">type: str</span><span class="li-normal">choices: ['none', 'read', 'create', 'update', 'delete']</span><span class="li-normal">default: none</span></li>
 <li><span class="li-head">bypass_validation</span> Bypass validation of the module.<span class="li-normal">type: bool</span><span class="li-normal">default: False</span></li>
 <li><span class="li-head">params</span> The parameters of the module.<span class="li-normal">type: dict</span><span class="li-normal">required: True</span></li>
 <ul class="ul-self"> <li><span class="li-head">primaryKey</span> <span class="li-normal">type: str</span><span class="li-normal">required: True</span></li>
 <li><span class="li-head">sandboxMode</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['Disabled', 'FortiSASE', 'StandaloneFortiSandbox']</span></li>
 <li><span class="li-head">timeoutAwaitingSandboxResults</span> <span class="li-normal">type: int</span></li>
 <li><span class="li-head">fileSubmissionOptions</span> <span class="li-normal">type: dict</span></li>
 <li><span class="li-head">detectionVerdictLevel</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['Clean', 'High', 'Low', 'Malicious', 'Medium']</span></li>
 <li><span class="li-head">exceptions</span> <span class="li-normal">type: dict</span></li>
 <li><span class="li-head">remediationActions</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['alert', 'quarantine']</span></li>
 <li><span class="li-head">hostName</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">authentication</span> <span class="li-normal">type: bool</span></li>
 <li><span class="li-head">username</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">password</span> <span class="li-normal">type: str</span></li>
 </ul> </ul>



Examples
-------------

.. code-block:: yaml

  - name: Update sandbox profiles
    hosts: fortisase
    gather_facts: false
    tasks:
      - name: Create policies, do nothing if already exists
        fortinet.fortisase.endpoint_policies:
          state: present
          params:
            primaryKey: "policy1"
            enabled: true
      - name: Update sandbox profiles
        fortinet.fortisase.endpoint_sandbox_profiles:
          params:
            primaryKey: "policy1"
            sandboxMode: "FortiSASE"  # Disabled, FortiSASE, StandaloneFortiSandbox
            detectionVerdictLevel: "Medium"
            exceptions:
              excludeFilesFromTrustedSources: "disable"
              files: []
              folders: []
            fileSubmissionOptions:
              allEmailDownloads: "enable"
              allFilesMappedNetworkDrives: "enable"
              allFilesRemovableMedia: "enable"
              allWebDownloads: "enable"
            remediationActions: "quarantine"
            timeoutAwaitingSandboxResults: 0
  


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

