security_ip_threat_feeds - IP Threat Feed Resource
++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.0.0

.. contents::
   :local:
   :depth: 1

Synopsis
--------
IP Threat Feed Resource.

Use API "/resource-api/v2/security/ip-threat-feeds".

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
 <li><span class="li-head">comments</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">status</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">refresh_rate</span> <span class="li-normal">type: int</span></li>
 <li><span class="li-head">uri</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">basic_authentication</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">username</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">password</span> <span class="li-normal">type: str</span></li>
 </ul></li>
 </ul>



Examples
-------------

.. code-block:: yaml

  - name: Security IP Threat Feeds
    hosts: fortisase
    gather_facts: false
    vars:
      primary_key: "asbfeeds"
    tasks:
      - name: Create/Update Security IP Threat Feeds
        fortinet.fortisase.security_ip_threat_feeds:
          state: present
          params:
            primary_key: "{{ primary_key }}"
            refresh_rate: 10
            status: "enable"
            uri: "https://www.virustotal.com/api/v3/domains/example.com/threat-feed"
            username: "fortinet"
            password: "fortinet"
            basic_authentication: "enable"
      - name: Delete Security IP Threat Feeds
        fortinet.fortisase.security_ip_threat_feeds:
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

