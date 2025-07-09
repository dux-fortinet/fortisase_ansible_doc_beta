private_access_service_connections - Secure Private Access Resource
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.0.0

.. contents::
   :local:
   :depth: 1

Synopsis
--------
Secure Private Access Resource.

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
 <ul class="ul-self"> <li><span class="li-head">alias</span> alias for serivce connection<span class="li-normal">type: str</span></li>
 <li><span class="li-head">bgp_peer_ip</span> BGP Routing Peer IP.<span class="li-normal">type: str</span></li>
 <li><span class="li-head">ipsec_remote_gw</span> IPSEC Remote Gateway IP<span class="li-normal">type: str</span></li>
 <li><span class="li-head">overlay_network_id</span> integer id for overlay<span class="li-normal">type: str</span></li>
 <li><span class="li-head">route_map_tag</span> route map tag<span class="li-normal">type: str</span></li>
 <li><span class="li-head">auth</span> IPSEC authentication method<span class="li-normal">type: str</span><span class="li-normal">choices: ['pki', 'psk']</span></li>
 <li><span class="li-head">ipsec_pre_shared_key</span> IPSEC auth by pre shared key.<span class="li-normal">type: str</span></li>
 <li><span class="li-head">ipsec_cert_name</span> the name of IPSEC authentication certificate that uploaded to SASE<span class="li-normal">type: str</span></li>
 <li><span class="li-head">ipsec_ike_version</span> IKE version for IPSEC<span class="li-normal">type: str</span><span class="li-normal">choices: ['2']</span></li>
 <li><span class="li-head">ipsec_peer_name</span> Peer PKI user name that created on SASE for IPSEC authentication<span class="li-normal">type: str</span></li>
 <li><span class="li-head">backup_links</span> <span class="li-normal">type: list</span></li>
 <li><span class="li-head">id</span> unique id for service connection<span class="li-normal">type: str</span></li>
 <li><span class="li-head">type</span> BGP Routing Design. Must be same as network configuration. BGP Routing Design.<span class="li-normal">type: str</span><span class="li-normal">choices: ['loopback', 'overlay']</span></li>
 <li><span class="li-head">config_state</span> Configuration state of service connection.<span class="li-normal">type: str</span><span class="li-normal">choices: ['creating', 'deleting', 'failed', 'success', 'updating']</span></li>
 <li><span class="li-head">seq_num</span> sequential unique number for service connection<span class="li-normal">type: int</span></li>
 <li><span class="li-head">failed_message</span> failure message while config service connection<span class="li-normal">type: str</span></li>
 <li><span class="li-head">config</span> <span class="li-normal">type: dict</span></li>
 <li><span class="li-head">common_config</span> <span class="li-normal">type: dict</span></li>
 <li><span class="li-head">ip_assigned</span> <span class="li-normal">type: list</span></li>
 <li><span class="li-head">region_cost</span> Cost value to determine the priority of SASE spokes. Default cost is 5 if not provided through initial api request.<span class="li-normal">type: dict</span></li>
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

