private_access_network_configuration - Secure Private Access Resource
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.0.0

.. contents::
   :local:
   :depth: 1

Synopsis
--------
Secure Private Access Resource.

Use API "/resource-api/v1/private-access/network-configuration".

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
 <li><span class="li-head">params</span> The parameters of the module.<span class="li-required">[Required]</span><span class="li-normal">type: dict</span></li>
 <ul class="ul-self"> <li><span class="li-head">bgp_router_ids_subnet</span> Available/unused subnet that can be used to assign loopback interface IP addresses used for BGP router IDs parameter on the FortiSASE security PoPs. /28 is the minimum subnet size.<span class="li-normal">type: str</span></li>
 <li><span class="li-head">as_number</span> Autonomous System Number (ASN).<span class="li-normal">type: str</span></li>
 <li><span class="li-head">recursive_next_hop</span> BGP Recursive Routing. Enabling this setting allows for interhub connectivity. When use BGP design on-loopback this has to be enabled.<span class="li-normal">type: bool</span><span class="li-normal">choices: ['false', 'true']</span></li>
 <li><span class="li-head">sdwan_rule_enable</span> Hub Selection Method. Enabling this setting the highest priority service connection that meets minimum SLA requirements is selected. Otherwise BGP MED (Multi-Exit Discriminator) will be used.<span class="li-normal">type: bool</span><span class="li-normal">choices: ['false', 'true']</span></li>
 <li><span class="li-head">sdwan_health_check_vm</span> Health Check IP. Must be provided when enable sdwan rule which used to obtain Jitter, latency and packet loss measurements.<span class="li-normal">type: str</span></li>
 <li><span class="li-head">config_state</span> Configuration state of network configuration.<span class="li-normal">type: str</span><span class="li-normal">choices: ['creating', 'deleting', 'failed', 'success', 'updating']</span></li>
 <li><span class="li-head">bgp_design</span> BGP Routing Design.<span class="li-normal">type: str</span><span class="li-normal">choices: ['loopback', 'overlay']</span></li>
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

