fortisase_generic - Send generic FortiSASE API request.
+++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.0.0

.. contents::
   :local:
   :depth: 1

Synopsis
--------
This module is for generic fortisase requests. It receives raw json-rpc data, and sends it to fortisase, finally returns the response to users.

Two parameters schemes are supported, either in raw json format "json" or in ansible recognnizable format "params".

If all two parameters are provided, the "json" is preferred.

Requirements
------------

The below requirements are needed on the host that executes this module.

- ansible>=2.17.0


Parameters
----------
.. raw:: html

 <ul>
 <li><span class="li-head">method</span> The method of the HTTP request.<span class="li-required">[Required]</span><span class="li-normal">type: str</span><span class="li-normal">choices: ['get', 'post', 'put', 'delete']</span></li>
 <li><span class="li-head">url</span> The URL of the API.<span class="li-required">[Required]</span><span class="li-normal">type: str</span></li>
 <li><span class="li-head">json</span> Raw json-rpc data.<span class="li-required">[Required]</span><span class="li-normal">type: str</span></li>
 <li><span class="li-head">params</span> Ansible recognnizable parameters.<span class="li-required">[Required]</span><span class="li-normal">type: dict</span></li>
 </ul>



Examples
-------------

.. code-block:: yaml

  - name: FortiSASE Generic Request
    hosts: fortisase
    gather_facts: false
    tasks:
      - name: FortiSASE Generic POST (Create) Request
        fortinet.fortisase.fortisase_generic:
          method: post
          url: "/resource-api/v2/network/dns-rules"
          params:
            primaryKey: "3"
            primaryDns: "3.3.3.3"
            secondaryDns: "3.3.3.2"
            domains:
              - www.33333.com
            popDnsOverride: {}
      - name: FortiSASE Generic GET (Read) Request
        fortinet.fortisase.fortisase_generic:
          method: get
          url: "/resource-api/v2/network/dns-rules/3"
      - name: FortiSASE Generic PUT (Update) Request
        fortinet.fortisase.fortisase_generic:
          method: put
          url: "/resource-api/v2/network/dns-rules/3"
          params:
            primaryKey: "3"
            primaryDns: "4.4.4.4"
            secondaryDns: "4.4.4.2"
            domains:
              - www.44444.com
            popDnsOverride: {}
      - name: FortiSASE Generic Delete (Delete) Request
        fortinet.fortisase.fortisase_generic:
          method: delete
          url: "/resource-api/v2/network/dns-rules/3"
  
  # Using json string
  - name: FortiSASE Generic Request (Using JSON String)
    hosts: fortisase
    gather_facts: false
    tasks:
      - name: FortiSASE Generic POST (Create) Request (JSON String)
        fortinet.fortisase.fortisase_generic:
          method: post
          url: "/resource-api/v2/network/dns-rules"
          json: |
            {
              "primaryKey": "3",
              "primaryDns": "3.3.3.3",
              "secondaryDns": "3.3.3.2",
              "domains": ["www.33333.com"],
              "popDnsOverride": {}
            }
      - name: FortiSASE Generic Delete (Delete) Request (JSON String)
        fortinet.fortisase.fortisase_generic:
          method: delete
          url: "/resource-api/v2/network/dns-rules/3"
          json: "{}"
  


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

