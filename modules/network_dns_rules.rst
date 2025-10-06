network_dns_rules - DNS Rule Resource
+++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.0.0

.. contents::
   :local:
   :depth: 1

Synopsis
--------
DNS Rule Resource.

Use API "/resource-api/v2/network/dns-rules".

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
 <li><span class="li-head">params</span> The parameters of the module.<span class="li-required">[Required]</span><span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">primary_key</span> <span class="li-required">[Required]</span><span class="li-normal">type: int</span></li>
 <li><span class="li-head">primary_dns</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">secondary_dns</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">domains</span> <span class="li-normal">type: list</span><span class="li-normal">elements: str</span></li>
 <li><span class="li-head">pop_dns_override</span> <span class="li-normal">type: dict</span></li>
 <li><span class="li-head">for_private</span> <span class="li-normal">type: bool</span></li>
 </ul></li>
 </ul>



Examples
-------------

.. code-block:: yaml

  - name: Network DNS Rule
    hosts: fortisase
    gather_facts: false
    vars:
      primaryKey: "1"
    tasks:
      - name: Create/Update Network DNS Rule
        fortinet.fortisase.network_dns_rules:
          state: present
          params:
            primaryKey: "{{ primaryKey }}"
            primaryDns: "1.1.1.1"
            secondaryDns: "1.1.1.2"
            domains:
              - www.facebook.com
              - www.google.com
            popDnsOverride: {}
      - name: Delete Network DNS Rule
        fortinet.fortisase.network_dns_rules:
          state: absent
          params:
            primaryKey: "{{ primaryKey }}"
  


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

