security_services - Service Resource
++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.0.0

.. contents::
   :local:
   :depth: 1

Synopsis
--------
Service Resource.

Use API "/resource-api/v2/security/services".

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
 <li><span class="li-head">proxy</span> <span class="li-normal">type: bool</span></li>
 <li><span class="li-head">category</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['Authentication', 'Email', 'File Access', 'General', 'Network Services', 'Remote Access', 'Tunneling', 'Uncategorized', 'VoIP, Messaging & Other Applications', 'Web Access', 'Web Proxy']</span></li>
 <li><span class="li-head">protocol</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">protocol_number</span> <span class="li-normal">type: int</span></li>
 <li><span class="li-head">icmp_type</span> <span class="li-normal">type: int</span></li>
 <li><span class="li-head">udp_portrange</span> <span class="li-normal">type: list</span><span class="li-normal">elements: dict</span> <ul class="ul-self"> <li><span class="li-head">destination</span> <span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">low</span> <span class="li-normal">type: int</span></li>
 <li><span class="li-head">high</span> <span class="li-normal">type: int</span></li>
 </ul></li>
 <li><span class="li-head">source</span> <span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">low</span> <span class="li-normal">type: int</span></li>
 <li><span class="li-head">high</span> <span class="li-normal">type: int</span></li>
 </ul></li>
 </ul></li>
 <li><span class="li-head">sctp_portrange</span> <span class="li-normal">type: list</span><span class="li-normal">elements: dict</span> <ul class="ul-self"> <li><span class="li-head">destination</span> <span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">low</span> <span class="li-normal">type: int</span></li>
 <li><span class="li-head">high</span> <span class="li-normal">type: int</span></li>
 </ul></li>
 <li><span class="li-head">source</span> <span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">low</span> <span class="li-normal">type: int</span></li>
 <li><span class="li-head">high</span> <span class="li-normal">type: int</span></li>
 </ul></li>
 </ul></li>
 <li><span class="li-head">tcp_portrange</span> <span class="li-normal">type: list</span><span class="li-normal">elements: dict</span> <ul class="ul-self"> <li><span class="li-head">destination</span> <span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">low</span> <span class="li-normal">type: int</span></li>
 <li><span class="li-head">high</span> <span class="li-normal">type: int</span></li>
 </ul></li>
 <li><span class="li-head">source</span> <span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">low</span> <span class="li-normal">type: int</span></li>
 <li><span class="li-head">high</span> <span class="li-normal">type: int</span></li>
 </ul></li>
 </ul></li>
 </ul></li>
 </ul>



Examples
-------------

.. code-block:: yaml

  - name: Security service
    hosts: fortisase
    gather_facts: false
    vars:
      primary_key: "service_example"
    tasks:
      - name: Create/Update security service
        fortinet.fortisase.security_services:
          state: present
          params:
            primary_key: "{{ primary_key }}"
            proxy: false
            category: "Email"
            protocol: "TCP/UDP/SCTP"
            tcp_portrange:
              - destination:
                  low: 25
      - name: Delete security service
        fortinet.fortisase.security_services:
          state: absent
          params:
            primary_key: "{{ primary_key }}"
  


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

