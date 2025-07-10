security_ips_custom_signatures - IPS Custom Signature Resource
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.0.0

.. contents::
   :local:
   :depth: 1

Synopsis
--------
IPS Custom Signature Resource.

Use API "/resource-api/v2/security/ips-custom-signatures".

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
 <li><span class="li-head">tag</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">signature</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">ruleId</span> <span class="li-normal">type: int</span></li>
 <li><span class="li-head">status</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">log</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">logPacket</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">action</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">severity</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">location</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">os</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">application</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">protocol</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">comment</span> <span class="li-normal">type: str</span></li>
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

