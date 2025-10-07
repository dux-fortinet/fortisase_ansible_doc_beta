dem_spa_applications - DEM SPA Application Resource
+++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.0.0

.. contents::
   :local:
   :depth: 1

Synopsis
--------
DEM SPA Application Resource.

Use API "/resource-api/v2/dem/spa-applications".

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
 <li><span class="li-head">server</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">latency_threshold</span> <span class="li-normal">type: int</span></li>
 <li><span class="li-head">jitter_threshold</span> <span class="li-normal">type: int</span></li>
 <li><span class="li-head">packetloss_threshold</span> <span class="li-normal">type: int</span></li>
 <li><span class="li-head">interval</span> <span class="li-normal">type: int</span></li>
 <li><span class="li-head">fail_time</span> <span class="li-normal">type: int</span></li>
 <li><span class="li-head">recovery_time</span> <span class="li-normal">type: int</span></li>
 </ul></li>
 </ul>



Examples
-------------

.. code-block:: yaml

  - name: Dem SPA Applications
    hosts: fortisase
    gather_facts: false
    vars:
      primary_key: "example_name"
    tasks:
      - name: Create/Update Dem SPA Applications
        fortinet.fortisase.dem_spa_applications:
          state: present
          params:
            primary_key: "{{ primary_key }}"
            server: "string"
            latency_threshold: 10000000
            jitter_threshold: 10000000
            packetloss_threshold: 100
            interval: 20
            fail_time: 1
            recovery_time: 1
      - name: Delete Dem SPA Applications
        fortinet.fortisase.dem_spa_applications:
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

