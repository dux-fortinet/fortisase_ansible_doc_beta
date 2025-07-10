endpoint_ztna_rules - ZTNA Rule Resource
++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.0.0

.. contents::
   :local:
   :depth: 1

Synopsis
--------
ZTNA Rule Resource.

Use API "/resource-api/v2/endpoint/ztna-rules".

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
 <ul class="ul-self"> <li><span class="li-head">primaryKey</span> <span class="li-required">[Required]</span><span class="li-normal">type: str</span></li>
 <li><span class="li-head">status</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">tag</span> <span class="li-normal">type: dict</span></li>
 <li><span class="li-head">comments</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">rules</span> <span class="li-normal">type: list</span></li>
 </ul> </ul>



Examples
-------------

.. code-block:: yaml

  - name: Update ztna rule
    hosts: fortisase
    gather_facts: false
    tasks:
      - name: Create a new endpoint profile, do nothing if the endpoint profile already exists
        fortinet.fortisase.endpoint_policies:
          state: present
          params:
            primaryKey: "policy1"
            enabled: true
      - name: Create/Update ztna tag, do nothing if the ztna tag already exists
        fortinet.fortisase.endpoint_ztna_tags:
          state: present
          params:
            primaryKey: "tag1"
            name: "tag1"
      - name: Update ztna rule
        fortinet.fortisase.endpoint_ztna_rules:
          params:
            primaryKey: "policy1"
            status: "enable" # "enable" or "disable"
            tag:
              primaryKey: "tag1"
              datasource: "endpoint/ztna-tags"
            comments: "example comment"
            rules:
              - os: "windows" # "windows", "macos", "linux", "ios", "android"
                type: "anti-virus"
                content: "AV Software is installed and running"
  


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

