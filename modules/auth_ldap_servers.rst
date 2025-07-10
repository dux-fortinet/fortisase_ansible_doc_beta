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
 <li><span class="li-head">force_method</span> Specify this option to force the method to use to interact with the resource.<span class="li-normal">type: str</span><span class="li-normal">choices: ['none', 'get', 'post', 'put', 'delete']</span><span class="li-normal">default: none</span></li>
 <li><span class="li-head">bypass_validation</span> Bypass validation of the module.<span class="li-normal">type: bool</span><span class="li-normal">default: False</span></li>
 <li><span class="li-head">params</span> The parameters of the module.<span class="li-required">[Required]</span><span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">primaryKey</span> <span class="li-required">[Required]</span><span class="li-normal">type: str</span></li>
 <li><span class="li-head">server</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">port</span> <span class="li-normal">type: int</span></li>
 <li><span class="li-head">cnid</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">dn</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">bindType</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['anonymous', 'regular', 'simple']</span></li>
 <li><span class="li-head">secureConnection</span> <span class="li-normal">type: bool</span></li>
 <li><span class="li-head">advancedGroupMatchingEnabled</span> <span class="li-normal">type: bool</span></li>
 <li><span class="li-head">groupMemberCheck</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['group-object', 'posix-group-object', 'user-attr']</span></li>
 <li><span class="li-head">memberAttribute</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">groupFilter</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">groupSearchBase</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">groupObjectFilter</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">serverIdentityCheckEnabled</span> <span class="li-normal">type: bool</span></li>
 <li><span class="li-head">passwordRenewalEnabled</span> <span class="li-normal">type: bool</span></li>
 <li><span class="li-head">certificate</span> <span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">primaryKey</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">datasource</span> <span class="li-normal">type: str</span></li>
 </ul></li>
 <li><span class="li-head">clientCertAuthEnabled</span> <span class="li-normal">type: bool</span></li>
 <li><span class="li-head">clientCert</span> <span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">primaryKey</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">datasource</span> <span class="li-normal">type: str</span></li>
 </ul></li>
 <li><span class="li-head">username</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">password</span> <span class="li-normal">type: str</span></li>
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

