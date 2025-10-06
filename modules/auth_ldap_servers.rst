auth_ldap_servers - LDAP Resource
+++++++++++++++++++++++++++++++++

.. versionadded:: 1.0.0

.. contents::
   :local:
   :depth: 1

Synopsis
--------
LDAP Resource.

Use API "/resource-api/v2/auth/ldap-servers".

Requirements
------------

The below requirements are needed on the host that executes this module.

- ansible>=2.17.0


Parameters
----------
.. raw:: html

 <ul>
 <li><span class="li-head">state</span> The state of the module. "present" means create or update the resource, "absent" means delete the resource.<span class="li-normal">type: str</span><span class="li-normal">choices: ['present', 'absent']</span><span class="li-normal">default: present</span></li>
 <li><span class="li-head">force_behavior</span> Specify this option to force the method to use to interact with the resource.<span class="li-normal">type: str</span><span class="li-normal">choices: ['none', 'read', 'create', 'update', 'delete']</span><span class="li-normal">default: none</span></li>
 <li><span class="li-head">bypass_validation</span> Bypass validation of the module.<span class="li-normal">type: bool</span><span class="li-normal">default: False</span></li>
 <li><span class="li-head">params</span> The parameters of the module.<span class="li-required">[Required]</span><span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">primary_key</span> <span class="li-required">[Required]</span><span class="li-normal">type: str</span></li>
 <li><span class="li-head">server</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">port</span> <span class="li-normal">type: int</span></li>
 <li><span class="li-head">cnid</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">dn</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">bind_type</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['anonymous', 'regular', 'simple']</span></li>
 <li><span class="li-head">secure_connection</span> <span class="li-normal">type: bool</span></li>
 <li><span class="li-head">advanced_group_matching_enabled</span> <span class="li-normal">type: bool</span></li>
 <li><span class="li-head">group_member_check</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['group-object', 'posix-group-object', 'user-attr']</span></li>
 <li><span class="li-head">member_attribute</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">group_filter</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">group_search_base</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">group_object_filter</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">server_identity_check_enabled</span> <span class="li-normal">type: bool</span></li>
 <li><span class="li-head">password_renewal_enabled</span> <span class="li-normal">type: bool</span></li>
 <li><span class="li-head">certificate</span> <span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">primary_key</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">datasource</span> <span class="li-normal">type: str</span></li>
 </ul></li>
 <li><span class="li-head">client_cert_auth_enabled</span> <span class="li-normal">type: bool</span></li>
 <li><span class="li-head">client_cert</span> <span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">primary_key</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">datasource</span> <span class="li-normal">type: str</span></li>
 </ul></li>
 <li><span class="li-head">username</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">password</span> <span class="li-normal">type: str</span></li>
 </ul></li>
 </ul>



Examples
-------------

.. code-block:: yaml

  - name: Auth LDAP Server
    hosts: fortisase
    gather_facts: false
    vars:
      primaryKey: "ldap_server_example"
    tasks:
      - name: Create/Update Auth LDAP Server
        fortinet.fortisase.auth_ldap_servers:
          state: present
          params:
            primaryKey: "{{ primaryKey }}"
            server: "1.1.1.1"
            port: 1111
            cnid: "test"
            dn: "cn=admin,dc=example,dc=com"
            clientCertAuthEnabled: false
            bindType: "simple"
            secureConnection: false
            serverIdentityCheckEnabled: true
            advancedGroupMatchingEnabled: true
            groupMemberCheck: "user-attr"
            groupFilter: "cn=group,dc=example,dc=com"
            groupSearchBase: "dc=example,dc=com"
            certificate:
              primaryKey: "certificate"
              datasource: "system/certificate/ca-certificates"
      - name: Delete Auth LDAP Server
        fortinet.fortisase.auth_ldap_servers:
          state: absent
          params:
            primaryKey: "{{ primaryKey }}"
  


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

