network_hosts - Host Resource
+++++++++++++++++++++++++++++

.. versionadded:: 1.0.0

.. contents::
   :local:
   :depth: 1

Synopsis
--------
Host Resource.

Use API "/resource-api/v2/network/hosts".

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
 <li><span class="li-head">type</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['fqdn', 'geography', 'ipmask', 'iprange']</span></li>
 <li><span class="li-head">location</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['external', 'internal', 'private-access', 'unspecified']</span></li>
 <li><span class="li-head">subnet</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">start_ip</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">end_ip</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">fqdn</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">country_id</span> <span class="li-normal">type: str</span></li>
 </ul></li>
 </ul>



Examples
-------------

.. code-block:: yaml

  - name: Network Host
    hosts: fortisase
    gather_facts: false
    vars:
      host: "network_host_example"
    tasks:
      - name: Create/Update Network Host
        fortinet.fortisase.network_hosts:
          state: present
          params:
            primary_key: "{{ host }}"
            type: "ipmask"
            location: "internal"
            subnet: "192.168.4.0/24"
      - name: Delete Network Host
        fortinet.fortisase.network_hosts:
          state: absent
          params:
            primary_key: "{{ host }}"
  


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

