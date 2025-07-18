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
 <li><span class="li-head">params</span> The parameters of the module.<span class="li-required">[Required]</span><span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">primaryKey</span> <span class="li-required">[Required]</span><span class="li-normal">type: str</span></li>
 <li><span class="li-head">enabled</span> <span class="li-normal">type: bool</span></li>
 <li><span class="li-head">idpEntityId</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">idpSignOnUrl</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">idpLogOutUrl</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">username</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">groupName</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">groupId</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">spCert</span> <span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">primaryKey</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">datasource</span> <span class="li-normal">type: str</span></li>
 </ul></li>
 <li><span class="li-head">idpCertificate</span> <span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">primaryKey</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">datasource</span> <span class="li-normal">type: str</span></li>
 </ul></li>
 <li><span class="li-head">digestMethod</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['sha1', 'sha256']</span></li>
 <li><span class="li-head">entraIdEnabled</span> <span class="li-normal">type: bool</span></li>
 <li><span class="li-head">scimEnabled</span> <span class="li-normal">type: bool</span></li>
 <li><span class="li-head">domainName</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">applicationId</span> <span class="li-normal">type: str</span></li>
 </ul></li>
 </ul>



Examples
-------------

.. code-block:: yaml

  
  


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

