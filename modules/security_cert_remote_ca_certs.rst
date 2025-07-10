security_cert_remote_ca_certs - Certificate Resource
++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.0.0

.. contents::
   :local:
   :depth: 1

Synopsis
--------
Certificate Resource.

Use API "/resource-api/v1/security/cert/remote-ca-certs".

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
 <li><span class="li-head">params</span> The parameters of the module.<span class="li-required">[Required]</span><span class="li-normal">type: dict</span></li>
 <ul class="ul-self"> <li><span class="li-head">id</span> <span class="li-normal">type: int</span></li>
 <li><span class="li-head">name</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">primaryKey</span> <span class="li-required">[Required]</span><span class="li-normal">type: str</span></li>
 <li><span class="li-head">type</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['emote-ca', 'local-cer']</span></li>
 <li><span class="li-head">source</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">issuer</span> <span class="li-normal">type: dict</span></li>
 <li><span class="li-head">validFrom</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">validTo</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">serialNumber</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">usages</span> <span class="li-normal">type: list</span></li>
 <li><span class="li-head">certName</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">fileContent</span> <span class="li-normal">type: str</span></li>
 </ul> </ul>



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

