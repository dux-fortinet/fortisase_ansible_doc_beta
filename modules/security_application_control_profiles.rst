security_application_control_profiles - Application Control Profile Resource
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.0.0

.. contents::
   :local:
   :depth: 1

Synopsis
--------
Application Control Profile Resource.

Use API "/resource-api/v2/security/application-control-profiles/{primaryKey}".

Requirements
------------

The below requirements are needed on the host that executes this module.

- ansible>=2.17.0


Parameters
----------
.. raw:: html

 <ul>
 <li><span class="li-head">state</span> The state of the module. "present" means update the resource. This resource can't be deleted, and does not support "absent" state.<span class="li-normal">type: str</span><span class="li-normal">choices: ['present', 'absent']</span><span class="li-normal">default: present</span></li>
 <li><span class="li-head">force_method</span> Specify this option to force the method to use to interact with the resource.<span class="li-normal">type: str</span><span class="li-normal">choices: ['none', 'get', 'post', 'put', 'delete']</span><span class="li-normal">default: none</span></li>
 <li><span class="li-head">bypass_validation</span> Bypass validation of the module.<span class="li-normal">type: bool</span><span class="li-normal">default: False</span></li>
 <li><span class="li-head">params</span> The parameters of the module.<span class="li-required">[Required]</span><span class="li-normal">type: dict</span></li>
 <ul class="ul-self"> <li><span class="li-head">primaryKey</span> <span class="li-required">[Required]</span><span class="li-normal">type: str</span></li>
 <li><span class="li-head">applicationCategoryControls</span> <span class="li-normal">type: list</span></li>
 <li><span class="li-head">applicationControls</span> <span class="li-normal">type: list</span></li>
 <li><span class="li-head">unknownApplicationAction</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['allow', 'block', 'monitor']</span></li>
 <li><span class="li-head">networkProtocolEnforcement</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">networkProtocols</span> <span class="li-normal">type: list</span></li>
 <li><span class="li-head">blockNonDefaultPortApplications</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 </ul> </ul>



Examples
-------------

.. code-block:: yaml

  - name: Update security application control profiles
    hosts: fortisase
    gather_facts: false
    tasks:
      - name: Update security application control profiles
        fortinet.fortisase.security_application_control_profiles:
          params:
            primaryKey: "internal" # internal or outbound
            applicationControls: []
            blockNonDefaultPortApplications: "disable"
            networkProtocolEnforcement: "disable"
            networkProtocols: []
            unknownApplicationAction: "monitor"
            applicationCategoryControls:
              - action: allow
                category:
                  datasource: security/application-categories
                  primaryKey: P2P
              - action: allow
                category:
                  datasource: security/application-categories
                  primaryKey: VoIP
              - action: allow
                category:
                  datasource: security/application-categories
                  primaryKey: Video/Audio
              - action: allow
                category:
                  datasource: security/application-categories
                  primaryKey: Proxy
              - action: allow
                category:
                  datasource: security/application-categories
                  primaryKey: Remote.Access
              - action: allow
                category:
                  datasource: security/application-categories
                  primaryKey: Game
              - action: allow
                category:
                  datasource: security/application-categories
                  primaryKey: General.Interest
              - action: allow
                category:
                  datasource: security/application-categories
                  primaryKey: Network.Service
              - action: allow
                category:
                  datasource: security/application-categories
                  primaryKey: Update
              - action: allow
                category:
                  datasource: security/application-categories
                  primaryKey: Email
              - action: allow
                category:
                  datasource: security/application-categories
                  primaryKey: Storage.Backup
              - action: allow
                category:
                  datasource: security/application-categories
                  primaryKey: Social.Media
              - action: allow
                category:
                  datasource: security/application-categories
                  primaryKey: Web.Client
              - action: allow
                category:
                  datasource: security/application-categories
                  primaryKey: Industrial
              - action: allow
                category:
                  datasource: security/application-categories
                  primaryKey: Collaboration
              - action: allow
                category:
                  datasource: security/application-categories
                  primaryKey: Business
              - action: allow
                category:
                  datasource: security/application-categories
                  primaryKey: Cloud.IT
              - action: allow
                category:
                  datasource: security/application-categories
                  primaryKey: Mobile
              - action: allow
                category:
                  datasource: security/application-categories
                  primaryKey: Unknown Applications
              - action: allow
                category:
                  datasource: security/application-categories
                  primaryKey: GenAI
  


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

