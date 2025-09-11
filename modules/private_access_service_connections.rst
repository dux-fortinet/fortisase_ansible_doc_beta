private_access_service_connections - Secure Private Access Resource
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.0.0

.. contents::
   :local:
   :depth: 1

Synopsis
--------
Secure Private Access Resource.

Use API "/resource-api/v1/private-access/service-connections".

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
 <li><span class="li-head">params</span> The parameters of the module.<span class="li-required">[Required]</span><span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">alias</span> alias for serivce connection<span class="li-normal">type: str</span></li>
 <li><span class="li-head">bgp_peer_ip</span> BGP Routing Peer IP.<span class="li-normal">type: str</span></li>
 <li><span class="li-head">ipsec_remote_gw</span> IPSEC Remote Gateway IP<span class="li-normal">type: str</span></li>
 <li><span class="li-head">overlay_network_id</span> integer id for overlay<span class="li-normal">type: str</span></li>
 <li><span class="li-head">route_map_tag</span> route map tag<span class="li-normal">type: str</span></li>
 <li><span class="li-head">auth</span> IPSEC authentication method<span class="li-normal">type: str</span><span class="li-normal">choices: ['pki', 'psk']</span></li>
 <li><span class="li-head">ipsec_pre_shared_key</span> IPSEC auth by pre shared key.<span class="li-normal">type: str</span></li>
 <li><span class="li-head">ipsec_cert_name</span> the name of IPSEC authentication certificate that uploaded to SASE<span class="li-normal">type: str</span></li>
 <li><span class="li-head">ipsec_ike_version</span> IKE version for IPSEC<span class="li-normal">type: str</span><span class="li-normal">choices: ['2']</span></li>
 <li><span class="li-head">ipsec_peer_name</span> Peer PKI user name that created on SASE for IPSEC authentication<span class="li-normal">type: str</span></li>
 <li><span class="li-head">backup_links</span> <span class="li-normal">type: list</span><span class="li-normal">elements: dict</span> <ul class="ul-self"> <li><span class="li-head">alias</span> alias for serivce connection additional overlay<span class="li-normal">type: str</span></li>
 <li><span class="li-head">auth</span> IPSEC authentication method<span class="li-normal">type: str</span><span class="li-normal">choices: ['pki', 'psk']</span></li>
 <li><span class="li-head">ipsec_cert_name</span> the name of IPSEC authentication certificate that uploaded to SASE<span class="li-normal">type: str</span></li>
 <li><span class="li-head">ipsec_ike_version</span> IKE version for IPSEC<span class="li-normal">type: str</span><span class="li-normal">choices: ['2']</span></li>
 <li><span class="li-head">ipsec_peer_name</span> Peer PKI user name that created on SASE for IPSEC authentication<span class="li-normal">type: str</span></li>
 <li><span class="li-head">ipsec_remote_gw</span> IPSEC Remote Gateway IP<span class="li-normal">type: str</span></li>
 <li><span class="li-head">overlay_network_id</span> integer id for overlay<span class="li-normal">type: str</span></li>
 <li><span class="li-head">ipsec_pre_shared_key</span> IPSEC auth by pre shared key.<span class="li-normal">type: str</span></li>
 </ul></li>
 <li><span class="li-head">id</span> unique id for service connection<span class="li-normal">type: str</span></li>
 <li><span class="li-head">type</span> BGP Routing Design. Must be same as network configuration.<span class="li-normal">type: str</span><span class="li-normal">choices: ['loopback', 'overlay']</span></li>
 <li><span class="li-head">config_state</span> Configuration state of service connection.<span class="li-normal">type: str</span><span class="li-normal">choices: ['creating', 'deleting', 'failed', 'success', 'updating']</span></li>
 <li><span class="li-head">seq_num</span> sequential unique number for service connection<span class="li-normal">type: int</span></li>
 <li><span class="li-head">failed_message</span> failure message while config service connection<span class="li-normal">type: str</span></li>
 <li><span class="li-head">config</span> <span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">alias</span> alias for serivce connection<span class="li-normal">type: str</span></li>
 <li><span class="li-head">auth</span> IPSEC authentication method<span class="li-normal">type: str</span><span class="li-normal">choices: ['pki', 'psk']</span></li>
 <li><span class="li-head">bgp_peer_ip</span> BGP Routing Peer IP.<span class="li-normal">type: str</span></li>
 <li><span class="li-head">ipsec_cert_name</span> the name of IPSEC authentication certificate that uploaded to SASE<span class="li-normal">type: str</span></li>
 <li><span class="li-head">ipsec_ike_version</span> IKE version for IPSEC<span class="li-normal">type: str</span><span class="li-normal">choices: ['2']</span></li>
 <li><span class="li-head">ipsec_peer_name</span> Peer PKI user name that created on SASE for IPSEC authentication<span class="li-normal">type: str</span></li>
 <li><span class="li-head">ipsec_remote_gw</span> IPSEC Remote Gateway IP<span class="li-normal">type: str</span></li>
 <li><span class="li-head">overlay_network_id</span> integer id for overlay<span class="li-normal">type: str</span></li>
 <li><span class="li-head">route_map_tag</span> route map tag<span class="li-normal">type: str</span></li>
 <li><span class="li-head">region_cost</span> cost value to determine the priority of SASE spokes<span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">sjc_f1</span> <span class="li-normal">type: int</span></li>
 <li><span class="li-head">lon_f1</span> <span class="li-normal">type: int</span></li>
 <li><span class="li-head">fra_f1</span> <span class="li-normal">type: int</span></li>
 <li><span class="li-head">iad_f1</span> <span class="li-normal">type: int</span></li>
 </ul></li>
 <li><span class="li-head">backup_links</span> <span class="li-normal">type: list</span><span class="li-normal">elements: dict</span> <ul class="ul-self"> <li><span class="li-head">id</span> unique id for additional IPsec overlays.<span class="li-normal">type: str</span></li>
 <li><span class="li-head">alias</span> alias for serivce connection additional overlay<span class="li-normal">type: str</span></li>
 <li><span class="li-head">auth</span> IPSEC authentication method<span class="li-normal">type: str</span><span class="li-normal">choices: ['pki', 'psk']</span></li>
 <li><span class="li-head">ipsec_cert_name</span> the name of IPSEC authentication certificate that uploaded to SASE<span class="li-normal">type: str</span></li>
 <li><span class="li-head">ipsec_ike_version</span> IKE version for IPSEC<span class="li-normal">type: str</span><span class="li-normal">choices: ['2']</span></li>
 <li><span class="li-head">ipsec_peer_name</span> Peer PKI user name that created on SASE for IPSEC authentication<span class="li-normal">type: str</span></li>
 <li><span class="li-head">ipsec_remote_gw</span> IPSEC Remote Gateway IP<span class="li-normal">type: str</span></li>
 <li><span class="li-head">overlay_network_id</span> integer id for overlay<span class="li-normal">type: str</span></li>
 </ul></li>
 </ul></li>
 <li><span class="li-head">common_config</span> <span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">config_state</span> Configuration state of network configuration.<span class="li-normal">type: str</span><span class="li-normal">choices: ['creating', 'deleting', 'failed', 'success', 'updating']</span></li>
 <li><span class="li-head">bgp_design</span> BGP Routing Design.<span class="li-normal">type: str</span><span class="li-normal">choices: ['loopback', 'overlay']</span></li>
 <li><span class="li-head">bgp_router_ids_subnet</span> Available/unused subnet that can be used to assign loopback interface IP addresses used for BGP router IDs parameter on the FortiSASE security PoPs. /28 is the minimum subnet size.<span class="li-normal">type: str</span></li>
 <li><span class="li-head">as_number</span> Autonomous System Number (ASN).<span class="li-normal">type: str</span></li>
 <li><span class="li-head">recursive_next_hop</span> BGP Recursive Routing. Enabling this setting allows for interhub connectivity. When use BGP design on-loopback this has to be enabled.<span class="li-normal">type: bool</span><span class="li-normal">choices: ['false', 'true']</span></li>
 <li><span class="li-head">sdwan_rule_enable</span> Hub Selection Method. Enabling this setting the highest priority service connection that meets minimum SLA requirements is selected. Otherwise BGP MED (Multi-Exit Discriminator) will be used.<span class="li-normal">type: bool</span><span class="li-normal">choices: ['false', 'true']</span></li>
 <li><span class="li-head">sdwan_health_check_vm</span> Health Check IP. Must be provided when enable sdwan rule which used to obtain Jitter, latency and packet loss measurements.<span class="li-normal">type: str</span></li>
 </ul></li>
 <li><span class="li-head">ip_assigned</span> <span class="li-normal">type: list</span><span class="li-normal">elements: dict</span> <ul class="ul-self"> <li><span class="li-head">id</span> unique id for bgp router id assignment<span class="li-normal">type: str</span></li>
 <li><span class="li-head">sdwan_common_id</span> unique id related to network configuration<span class="li-normal">type: str</span></li>
 <li><span class="li-head">bgp_router_id</span> BGP Router ID generated from Router ID Subnets<span class="li-normal">type: str</span></li>
 <li><span class="li-head">site_id</span> id for SASE spoke<span class="li-normal">type: str</span></li>
 <li><span class="li-head">region</span> air port code for SASE spoke physical region<span class="li-normal">type: str</span></li>
 </ul></li>
 <li><span class="li-head">region_cost</span> Cost value to determine the priority of SASE spokes. Default cost is 5 if not provided through initial api request.<span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">sjc_f1</span> <span class="li-normal">type: int</span></li>
 <li><span class="li-head">lon_f1</span> <span class="li-normal">type: int</span></li>
 <li><span class="li-head">fra_f1</span> <span class="li-normal">type: int</span></li>
 <li><span class="li-head">iad_f1</span> <span class="li-normal">type: int</span></li>
 </ul></li>
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

