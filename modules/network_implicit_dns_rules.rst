network_implicit_dns_rules - Implicit DNS Rule Resource
+++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.0.0

.. contents::
   :local:
   :depth: 1

Synopsis
--------
Implicit DNS Rule Resource.

Use API "/resource-api/v2/network/implicit-dns-rules/{primaryKey}".

Requirements
------------

The below requirements are needed on the host that executes this module.

- ansible>=2.17.0


Parameters
----------
.. raw:: html

 <ul>
 <li><span class="li-head">state</span> The state of the module. "present" means update the resource. This resource can't be deleted, and does not support "absent" state.<span class="li-normal">type: str</span><span class="li-normal">choices: ['present', 'absent']</span><span class="li-normal">default: present</span></li>
 <li><span class="li-head">force_behavior</span> Specify this option to force the method to use to interact with the resource.<span class="li-normal">type: str</span><span class="li-normal">choices: ['none', 'read', 'create', 'update', 'delete']</span><span class="li-normal">default: none</span></li>
 <li><span class="li-head">bypass_validation</span> Bypass validation of the module.<span class="li-normal">type: bool</span><span class="li-normal">default: False</span></li>
 <li><span class="li-head">params</span> The parameters of the module.<span class="li-required">[Required]</span><span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">primaryKey</span> <span class="li-required">[Required]</span><span class="li-normal">type: str</span><span class="li-normal">choices: ['implicit_all', 'other', 'vpn']</span></li>
 <li><span class="li-head">dnsServer</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['cloudflare', 'custom', 'endpoint', 'fortiguard', 'google', 'quad9']</span></li>
 <li><span class="li-head">dnsServer1</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">dnsServer2</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">protocols</span> <span class="li-normal">type: list</span><span class="li-normal">elements: raw</span></li>
 <li><span class="li-head">forPrivate</span> <span class="li-normal">type: bool</span></li>
 </ul></li>
 </ul>



Examples
-------------

.. code-block:: yaml

  - name: Network Implicit DNS Rule
    hosts: fortisase
    gather_facts: false
    tasks:
      - name: Update Network Implicit DNS Rule
        fortinet.fortisase.network_implicit_dns_rules:
          params:
            primaryKey: "implicit_all"
            dnsServer: "fortiguard"
  


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

