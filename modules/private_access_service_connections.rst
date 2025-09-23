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
 <li><span class="li-head">params</span> The parameters of the module.<span class="li-required">[Required]</span><span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">service_connection_id</span> <span class="li-required">[Required]</span><span class="li-normal">type: str</span></li>
 <li><span class="li-head">alias</span> alias for serivce connection<span class="li-normal">type: str</span></li>
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
 <li><span class="li-head">type</span> BGP Routing Design. Must be same as network configuration.<span class="li-normal">type: str</span><span class="li-normal">choices: ['loopback', 'overlay']</span></li>
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

  - name: Private Access Service Connections
    hosts: fortisase
    gather_facts: false
    tasks:
      # !!!! private_access_network_configuration has to be created first
      # - name: Create/Update Private Access Network Configuration
      #   fortinet.fortisase.private_access_network_configuration:
      #     state: present
      #     params:
      #       bgp_design: "loopback"
      #       bgp_router_ids_subnet: "172.1.0.0/24"
      #       as_number: "65400"
      #       sdwan_rule_enable: true
      #       sdwan_health_check_vm: "10.255.255.100"
      #       recursive_next_hop: true
      # - name: Wait until the resource config_state is success
      #   fortinet.fortisase.fortisase_facts:
      #     selector: "private_access_network_configuration"
      #   register: result
      #   until: result.response.config_state == "success"
      #   retries: 15
      #   delay: 10
  
      - name: Create Private Access Service Connections
        fortinet.fortisase.private_access_service_connections:
          state: present
          params:
            service_connection_id: "placeholder, not in use in create"
            type: "loopback"
            alias: "AWS-Ireland-Primary"
            ipsec_remote_gw: "1.1.1.1"
            ipsec_ike_version: "2"
            auth: "psk"
            ipsec_pre_shared_key: "example_shared_key"
            route_map_tag: "100"
            bgp_peer_ip: "10.255.255.100"
            overlay_network_id: "100"
        register: create_result
      - name: Wait until the resource config_state in create_result is success
        fortinet.fortisase.fortisase_facts:
          selector: "private_access_service_connections"
          params:
            service_connection_id: "{{ create_result.response.id }}"
        register: result
        until: result.response.config_state == "success" or result.response.config_state == "failed"
        retries: 15
        delay: 10
        failed_when: result.response.config_state != "success"
  
      - name: Update Private Access Service Connections
        fortinet.fortisase.private_access_service_connections:
          state: present
          params:
            service_connection_id: "{{ create_result.response.id }}"
            ipsec_remote_gw: "1.1.1.2"
        register: update_result
      - name: Wait until the resource config_state in update_result is success
        fortinet.fortisase.fortisase_facts:
          selector: "private_access_service_connections"
          params:
            service_connection_id: "{{ update_result.response.id }}"
        register: result
        until: result.response.config_state == "success" or result.response.config_state == "failed"
        retries: 15
        delay: 10
        failed_when: result.response.config_state != "success"
  
      - name: Delete Private Access Service Connections
        fortinet.fortisase.private_access_service_connections:
          state: absent
          params:
            service_connection_id: "{{ create_result.response.id }}"
      - name: Wait until return error 403 (deleted successfully)
        fortinet.fortisase.fortisase_facts:
          selector: "private_access_service_connections"
          params:
            service_connection_id: "{{ create_result.response.id }}"
        register: result
        until: result.http_code == 403
        retries: 15
        delay: 10
        failed_when: false  # Never fail, regardless of HTTP 403 error
  


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

