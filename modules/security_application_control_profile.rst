security_application_control_profile - Application Control Profile Resource
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.0.0

.. contents::
   :local:
   :depth: 1

Synopsis
--------
Application Control Profile Resource.

Use API "/resource-api/v2/security/application-control-profile/{direction}/{primaryKey}".

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
 <li><span class="li-head">application_category_controls</span> <span class="li-normal">type: list</span><span class="li-normal">elements: dict</span> <ul class="ul-self"> <li><span class="li-head">action</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['allow', 'block', 'monitor']</span></li>
 <li><span class="li-head">category</span> <span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">primary_key</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">datasource</span> <span class="li-normal">type: str</span></li>
 </ul></li>
 </ul></li>
 <li><span class="li-head">application_controls</span> <span class="li-normal">type: list</span><span class="li-normal">elements: dict</span> <ul class="ul-self"> <li><span class="li-head">action</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['allow', 'block', 'monitor']</span></li>
 <li><span class="li-head">applications</span> <span class="li-normal">type: list</span><span class="li-normal">elements: dict</span> <ul class="ul-self"> <li><span class="li-head">primary_key</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">datasource</span> <span class="li-normal">type: str</span></li>
 </ul></li>
 </ul></li>
 <li><span class="li-head">unknown_application_action</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['allow', 'block', 'monitor']</span></li>
 <li><span class="li-head">network_protocol_enforcement</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">network_protocols</span> <span class="li-normal">type: list</span><span class="li-normal">elements: dict</span> <ul class="ul-self"> <li><span class="li-head">port</span> <span class="li-normal">type: int</span></li>
 <li><span class="li-head">action</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['block', 'monitor', 'pass']</span></li>
 <li><span class="li-head">services</span> <span class="li-normal">type: list</span><span class="li-normal">elements: str</span></li>
 </ul></li>
 <li><span class="li-head">block_non_default_port_applications</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 </ul></li>
 </ul>



Examples
-------------

.. code-block:: yaml

  # To configure this resource, please disable SWG Configuration.
  - name: Update security application control profile
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
            primary_key: "{{ profile_group }}"
      - name: Update security application control profile
        fortinet.fortisase.security_application_control_profile:
          params:
            direction: "{{ direction }}"
            primary_key: "{{ profile_group }}"
            application_controls: []
            block_non_default_port_applications: "disable"
            network_protocol_enforcement: "disable"
            network_protocols: []
            unknown_application_action: "monitor"
            application_category_controls:
              - action: allow
                category:
                  datasource: security/application-categories
                  primary_key: P2P
              - action: allow
                category:
                  datasource: security/application-categories
                  primary_key: VoIP
              - action: allow
                category:
                  datasource: security/application-categories
                  primary_key: Video/Audio
              - action: allow
                category:
                  datasource: security/application-categories
                  primary_key: Proxy
              - action: allow
                category:
                  datasource: security/application-categories
                  primary_key: Remote.Access
              - action: allow
                category:
                  datasource: security/application-categories
                  primary_key: Game
              - action: allow
                category:
                  datasource: security/application-categories
                  primary_key: General.Interest
              - action: allow
                category:
                  datasource: security/application-categories
                  primary_key: Network.Service
              - action: allow
                category:
                  datasource: security/application-categories
                  primary_key: Update
              - action: allow
                category:
                  datasource: security/application-categories
                  primary_key: Email
              - action: allow
                category:
                  datasource: security/application-categories
                  primary_key: Storage.Backup
              - action: allow
                category:
                  datasource: security/application-categories
                  primary_key: Social.Media
              - action: allow
                category:
                  datasource: security/application-categories
                  primary_key: Web.Client
              - action: allow
                category:
                  datasource: security/application-categories
                  primary_key: Industrial
              - action: allow
                category:
                  datasource: security/application-categories
                  primary_key: Collaboration
              - action: allow
                category:
                  datasource: security/application-categories
                  primary_key: Business
              - action: allow
                category:
                  datasource: security/application-categories
                  primary_key: Cloud.IT
              - action: allow
                category:
                  datasource: security/application-categories
                  primary_key: Mobile
              - action: allow
                category:
                  datasource: security/application-categories
                  primary_key: Unknown Applications
              - action: allow
                category:
                  datasource: security/application-categories
                  primary_key: GenAI
  


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

