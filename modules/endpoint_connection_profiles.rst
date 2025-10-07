endpoint_connection_profiles - Connection Profile Resource
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.0.0

.. contents::
   :local:
   :depth: 1

Synopsis
--------
Connection Profile Resource.

Use API "/resource-api/v2/endpoint/connection-profiles/{primaryKey}".

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
 <li><span class="li-head">connect_to_fortisase</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['automatically', 'manually']</span></li>
 <li><span class="li-head">lockdown</span> <span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">status</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">grace_period</span> <span class="li-normal">type: int</span></li>
 <li><span class="li-head">max_attempts</span> <span class="li-normal">type: int</span></li>
 <li><span class="li-head">ips</span> <span class="li-normal">type: list</span><span class="li-normal">elements: dict</span> <ul class="ul-self"> <li><span class="li-head">ip</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">port</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">protocol</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['', 'icmp', 'tcp', 'udp']</span></li>
 </ul></li>
 <li><span class="li-head">domains</span> <span class="li-normal">type: list</span><span class="li-normal">elements: dict</span> <ul class="ul-self"> <li><span class="li-head">address</span> <span class="li-normal">type: str</span></li>
 </ul></li>
 <li><span class="li-head">detect_captive_portal</span> <span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">status</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 </ul></li>
 </ul></li>
 <li><span class="li-head">on_fabric_rule_set</span> <span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">primary_key</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">datasource</span> <span class="li-normal">type: str</span></li>
 </ul></li>
 <li><span class="li-head">off_net_split_tunnel</span> <span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">local_apps</span> <span class="li-normal">type: list</span><span class="li-normal">elements: str</span></li>
 <li><span class="li-head">isdbs</span> <span class="li-normal">type: list</span><span class="li-normal">elements: dict</span> <ul class="ul-self"> <li><span class="li-head">primary_key</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">datasource</span> <span class="li-normal">type: str</span></li>
 </ul></li>
 <li><span class="li-head">fqdns</span> <span class="li-normal">type: list</span><span class="li-normal">elements: str</span></li>
 <li><span class="li-head">subnets</span> <span class="li-normal">type: list</span><span class="li-normal">elements: dict</span> <ul class="ul-self"> <li><span class="li-head">primary_key</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">datasource</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['network/host-groups', 'network/hosts']</span></li>
 </ul></li>
 <li><span class="li-head">subnets_ipsec</span> <span class="li-normal">type: list</span><span class="li-normal">elements: str</span></li>
 </ul></li>
 <li><span class="li-head">split_tunnel</span> <span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">local_apps</span> <span class="li-normal">type: list</span><span class="li-normal">elements: str</span></li>
 <li><span class="li-head">isdbs</span> <span class="li-normal">type: list</span><span class="li-normal">elements: dict</span> <ul class="ul-self"> <li><span class="li-head">primary_key</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">datasource</span> <span class="li-normal">type: str</span></li>
 </ul></li>
 <li><span class="li-head">fqdns</span> <span class="li-normal">type: list</span><span class="li-normal">elements: str</span></li>
 <li><span class="li-head">subnets</span> <span class="li-normal">type: list</span><span class="li-normal">elements: dict</span> <ul class="ul-self"> <li><span class="li-head">primary_key</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">datasource</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['network/host-groups', 'network/hosts']</span></li>
 </ul></li>
 <li><span class="li-head">subnets_ipsec</span> <span class="li-normal">type: list</span><span class="li-normal">elements: str</span></li>
 </ul></li>
 <li><span class="li-head">allow_invalid_server_certificate</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">endpoint_on_net_bypass</span> <span class="li-normal">type: bool</span></li>
 <li><span class="li-head">auth_before_user_logon</span> <span class="li-normal">type: bool</span></li>
 <li><span class="li-head">secure_internet_access</span> <span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">authenticate_with_sso</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">enable_local_lan</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">failover_sequence</span> <span class="li-normal">type: list</span><span class="li-normal">elements: str</span></li>
 <li><span class="li-head">posture_check</span> <span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">tag</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">action</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['allow', 'prohibit']</span></li>
 <li><span class="li-head">check_failed_message</span> <span class="li-normal">type: str</span></li>
 </ul></li>
 <li><span class="li-head">external_browser_saml_login</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 </ul></li>
 <li><span class="li-head">preferred_dtls_tunnel</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">use_gui_saml_auth</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">allow_personal_vpns</span> <span class="li-normal">type: bool</span></li>
 <li><span class="li-head">mtu_size</span> <span class="li-normal">type: int</span></li>
 <li><span class="li-head">available_vpns</span> <span class="li-normal">type: list</span><span class="li-normal">elements: dict</span> <ul class="ul-self"> <li><span class="li-head">type</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['ipSecVPN', 'sslVPN']</span></li>
 <li><span class="li-head">name</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">remote_gateway</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">username_prompt</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">save_username</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">show_always_up</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">show_auto_connect</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">show_remember_password</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">authenticate_with_sso</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">enable_local_lan</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">external_browser_saml_login</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">port</span> <span class="li-normal">type: int</span></li>
 <li><span class="li-head">require_certificate</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">auth_method</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['preSharedKey', 'smartCardCert', 'systemStoreCert']</span></li>
 <li><span class="li-head">show_passcode</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">posture_check</span> <span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">tag</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">action</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['allow', 'prohibit']</span></li>
 <li><span class="li-head">check_failed_message</span> <span class="li-normal">type: str</span></li>
 </ul></li>
 <li><span class="li-head">pre_shared_key</span> <span class="li-normal">type: str</span></li>
 </ul></li>
 <li><span class="li-head">show_disconnect_btn</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">enable_invalid_server_cert_warning</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">pre_logon</span> <span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">vpn_type</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['ipSecVPN', 'sslVPN']</span></li>
 <li><span class="li-head">remote_gateway</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">common_name</span> <span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">match_type</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['regex', 'wildcard']</span></li>
 <li><span class="li-head">pattern</span> <span class="li-normal">type: str</span></li>
 </ul></li>
 <li><span class="li-head">issuer</span> <span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">match_type</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['regex', 'wildcard']</span></li>
 <li><span class="li-head">pattern</span> <span class="li-normal">type: str</span></li>
 </ul></li>
 <li><span class="li-head">port</span> <span class="li-normal">type: int</span></li>
 </ul></li>
 </ul></li>
 </ul>



Examples
-------------

.. code-block:: yaml

  - name: Connection profile
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
      - name: Update connection profile
        fortinet.fortisase.endpoint_connection_profiles:
          params:
            primary_key: "{{ primary_key }}"
            allow_invalid_server_certificate: "enable"
            allow_personal_vpns: false
            auth_before_user_logon: false
            available_vpns: []
            connect_to_fortisase: "manually"
            enable_invalid_server_cert_warning: "disable"
            endpoint_on_net_bypass: false
            preferred_dtls_tunnel: "enable"
            secure_internet_access:
              authenticate_with_sso: "disable"
              external_browser_saml_login: "disable"
            use_gui_saml_auth: "disable"
  


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

