security_dlp_profiles - DLP Profile Resource
++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.0.0

.. contents::
   :local:
   :depth: 1

Synopsis
--------
DLP Profile Resource.

Use API "/resource-api/v2/security/dlp-profiles/{primaryKey}".

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
 <li><span class="li-head">params</span> The parameters of the module.<span class="li-required">[Required]</span><span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">primaryKey</span> <span class="li-required">[Required]</span><span class="li-normal">type: str</span></li>
 <li><span class="li-head">dlpRules</span> <span class="li-normal">type: list</span><span class="li-normal">elements: dict</span> <ul class="ul-self"> <li><span class="li-head">primaryKey</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">datasourceType</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['fingerprint', 'mpip-label', 'none', 'sensors']</span></li>
 <li><span class="li-head">severity</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['critical', 'high', 'informational', 'low', 'medium']</span></li>
 <li><span class="li-head">action</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['allow', 'block', 'monitor']</span></li>
 <li><span class="li-head">dlpRuleType</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['file', 'message']</span></li>
 <li><span class="li-head">fileType</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['all', 'specify']</span></li>
 <li><span class="li-head">protocols</span> <span class="li-normal">type: list</span><span class="li-normal">elements: str</span></li>
 <li><span class="li-head">dlpSensors</span> <span class="li-normal">type: list</span><span class="li-normal">elements: dict</span> <ul class="ul-self"> <li><span class="li-head">primaryKey</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">datasource</span> <span class="li-normal">type: str</span></li>
 </ul></li>
 <li><span class="li-head">sensitivityLabel</span> <span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">primaryKey</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">datasource</span> <span class="li-normal">type: str</span></li>
 </ul></li>
 <li><span class="li-head">sensitivities</span> <span class="li-normal">type: list</span><span class="li-normal">elements: str</span></li>
 <li><span class="li-head">dlpFilePattern</span> <span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">primaryKey</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">datasource</span> <span class="li-normal">type: str</span></li>
 </ul></li>
 </ul></li>
 </ul></li>
 </ul>



Examples
-------------

.. code-block:: yaml

  - name: Update security dlp profiles
    hosts: fortisase
    gather_facts: false
    tasks:
      - name: Update security dlp profiles
        fortinet.fortisase.security_dlp_profiles:
          params:
            primaryKey: "outbound" # internal or outbound
            dlpRules: []
  


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

