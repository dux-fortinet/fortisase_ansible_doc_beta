auth_swg_saml_server - SWG User SSO Resource
++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.0.0

.. contents::
   :local:
   :depth: 1

Synopsis
--------
SWG User SSO Resource.

Use API "/resource-api/v2/auth/swg-saml-server".

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
 <li><span class="li-head">group_match</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">sp_cert</span> <span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">primary_key</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">datasource</span> <span class="li-normal">type: str</span></li>
 </ul></li>
 <li><span class="li-head">idp_certificate</span> <span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">primary_key</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">datasource</span> <span class="li-normal">type: str</span></li>
 </ul></li>
 <li><span class="li-head">digest_method</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['sha1', 'sha256']</span></li>
 <li><span class="li-head">scim_enabled</span> <span class="li-normal">type: bool</span></li>
 <li><span class="li-head">scim</span> <span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">scim_url</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">auth_method</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['token']</span></li>
 <li><span class="li-head">token</span> <span class="li-normal">type: str</span></li>
 </ul></li>
 </ul></li>
 </ul>



Examples
-------------

.. code-block:: yaml

  - name: Auth SWG SAML Server
    hosts: fortisase
    gather_facts: false
    vars:
      primary_key: "$sase-global"
    tasks:
      # To configure this resource, please enable proxy configuration.
      - name: Create/Update Auth SWG SAML Server
        fortinet.fortisase.auth_swg_saml_server:
          params:
            primary_key: "{{ primaryKey }}"
            enabled: true
            digest_method: "sha256"
            idp_entity_id: "https://sts.windows.net/example/"
            idp_sign_on_url: "https://login.microsoftonline.com/example/saml2"
            idp_log_out_url: "https://login.microsoftonline.com/example/saml2"
            idp_certificate:
              primary_key: "certificate"
              datasource: "system/certificate/remote-certificates"
            username: "username"
            group_name: "group"
            group_match: ""
            sp_cert:
              primary_key: "FortiSASE Default Certificate"
              datasource: "system/certificate/local-certificates"
            scim_enabled: false
  
      - name: Delete Auth SWG SAML Server
        fortinet.fortisase.auth_swg_saml_server:
          params:
            primary_key: "{{ primaryKey }}"
            enabled: false
  


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

