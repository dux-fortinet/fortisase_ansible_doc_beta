auth_vpn_saml_server - VPN User SSO Resource
++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.0.0

.. contents::
   :local:
   :depth: 1

Synopsis
--------
VPN User SSO Resource.

Use API "/resource-api/v2/auth/vpn-saml-server".

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
 <li><span class="li-head">enabled</span> <span class="li-normal">type: bool</span></li>
 <li><span class="li-head">idp_entity_id</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">idp_sign_on_url</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">idp_log_out_url</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">username</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">group_name</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">group_id</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">sp_cert</span> <span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">primary_key</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">datasource</span> <span class="li-normal">type: str</span></li>
 </ul></li>
 <li><span class="li-head">idp_certificate</span> <span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">primary_key</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">datasource</span> <span class="li-normal">type: str</span></li>
 </ul></li>
 <li><span class="li-head">digest_method</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['sha1', 'sha256']</span></li>
 <li><span class="li-head">entra_id_enabled</span> <span class="li-normal">type: bool</span></li>
 <li><span class="li-head">scim_enabled</span> <span class="li-normal">type: bool</span></li>
 <li><span class="li-head">domain_name</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">application_id</span> <span class="li-normal">type: str</span></li>
 </ul></li>
 </ul>



Examples
-------------

.. code-block:: yaml

  - name: Auth VPN SAML Server
    hosts: fortisase
    gather_facts: false
    vars:
      primaryKey: "$sase-global"
    tasks:
      - name: Create/Update Auth VPN SAML Server with full configuration
        fortinet.fortisase.auth_vpn_saml_server:
          state: present
          params:
            primaryKey: "{{ primaryKey }}"
            enabled: true
            digestMethod: "sha256"
            idpEntityId: "https://sts.windows.net/example/"
            idpSignOnUrl: "https://login.microsoftonline.com/example/saml1"
            idpLogOutUrl: "https://login.microsoftonline.com/example/saml1"
            idpCertificate:
              primaryKey: "certificate"
              datasource: "system/certificate/remote-certificates"
            username: "example_username"
            groupName: "example_group_name"
            spCert:
              primaryKey: "FortiSASE Default Certificate"
              datasource: "system/certificate/local-certificates"
            scimEnabled: false
            groupId: ""
            entraIdEnabled: false
      - name: Wait until the resource $meta.state is done
        fortinet.fortisase.fortisase_facts:
          selector: "auth_vpn_saml_server"
          params:
            primaryKey: "{{ primaryKey }}"
        register: result
        until: result.response[0]['$meta'].state == "done"
        retries: 15
        delay: 10
        failed_when: result.response[0]['$meta'].state != "done"
  
      - name: Delete Auth VPN SAML Server
        fortinet.fortisase.auth_vpn_saml_server:
          params:
            primaryKey: "{{ primaryKey }}"
            enabled: false
      - name: Wait until the resource $meta doesn't have state
        fortinet.fortisase.fortisase_facts:
          selector: "auth_vpn_saml_server"
          params:
            primaryKey: "{{ primaryKey }}"
        register: result
        until: result.response[0]['$meta']['state'] is not defined
        retries: 15
        delay: 10
  


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

