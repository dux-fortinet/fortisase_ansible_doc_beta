security_pki_users - PKI User Resource API for FortiSASE
++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.0.0

.. contents::
   :local:
   :depth: 1

Synopsis
--------
PKI User Resource API for FortiSASE

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
 <li><span class="li-head">params</span> The parameters of the module.<span class="li-normal">type: dict</span><span class="li-normal">required: True</span></li>
 <ul class="ul-self"> <li><span class="li-head">primaryKey</span> Primary Key of PKI User.<span class="li-normal">type: str</span><span class="li-normal">required: True</span></li>
 <li><span class="li-head">subject</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">ca</span> <span class="li-normal">type: dict</span></li>
 <li><span class="li-head">isStaticObject</span> <span class="li-normal">type: bool</span><span class="li-normal">choices: ['false', 'true']</span></li>
 <li><span class="li-head">references</span> <span class="li-normal">type: int</span></li>
 <li><span class="li-head">isGlobalEntry</span> <span class="li-normal">type: bool</span><span class="li-normal">choices: ['false', 'true']</span></li>
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

