security_video_filter_profile - Video Filter Profile Resource
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.0.0

.. contents::
   :local:
   :depth: 1

Synopsis
--------
Video Filter Profile Resource.

Use API "/resource-api/v2/security/video-filter-profile/{direction}/{primaryKey}".

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
 <li><span class="li-head">params</span> The parameters of the module.<span class="li-required">[Required]</span><span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">direction</span> <span class="li-required">[Required]</span><span class="li-normal">type: str</span></li>
 <li><span class="li-head">primaryKey</span> <span class="li-required">[Required]</span><span class="li-normal">type: str</span></li>
 <li><span class="li-head">fortiguardFilters</span> <span class="li-normal">type: list</span><span class="li-normal">elements: dict</span> <ul class="ul-self"> <li><span class="li-head">action</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['allow', 'block', 'default', 'monitor', 'warning']</span></li>
 <li><span class="li-head">category</span> <span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">primaryKey</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">datasource</span> <span class="li-normal">type: str</span></li>
 </ul></li>
 </ul></li>
 <li><span class="li-head">defaultAction</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">channels</span> <span class="li-normal">type: list</span><span class="li-normal">elements: dict</span> <ul class="ul-self"> <li><span class="li-head">action</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['allow', 'block', 'monitor']</span></li>
 <li><span class="li-head">name</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">channelId</span> <span class="li-normal">type: str</span></li>
 </ul></li>
 </ul></li>
 </ul>



Examples
-------------

.. code-block:: yaml

  - name: Update security video filter profile
    hosts: fortisase
    gather_facts: false
    vars:
      direction: "outbound-profiles" # outbound-profiles or internal-profiles
      profile_group: "profile_ansible"
    tasks:
      - name: Ensure security group exists, otherwise create it
        fortinet.fortisase.security_profile_group:
          params:
            direction: "{{ direction }}"
            primaryKey: "{{ profile_group }}"
      - name: Update security video filter profile
        fortinet.fortisase.security_video_filter_profile:
          params:
            direction: "{{ direction }}"
            primaryKey: "{{ profile_group }}"
            defaultAction: "monitor"
            channels: []
            fortiguardFilters:
              - action: "default"
                category:
                  datasource: "security/video-filter-fortiguard-categories"
                  primaryKey: "Not Rated"
              - action: "default"
                category:
                  datasource: "security/video-filter-fortiguard-categories"
                  primaryKey: "Business"
              - action: "default"
                category:
                  datasource: "security/video-filter-fortiguard-categories"
                  primaryKey: "Entertainment"
              - action: "default"
                category:
                  datasource: "security/video-filter-fortiguard-categories"
                  primaryKey: "Games"
              - action: "default"
                category:
                  datasource: "security/video-filter-fortiguard-categories"
                  primaryKey: "Knowledge"
              - action: "default"
                category:
                  datasource: "security/video-filter-fortiguard-categories"
                  primaryKey: "Lifestyle"
              - action: "default"
                category:
                  datasource: "security/video-filter-fortiguard-categories"
                  primaryKey: "Music"
              - action: "default"
                category:
                  datasource: "security/video-filter-fortiguard-categories"
                  primaryKey: "News"
              - action: "default"
                category:
                  datasource: "security/video-filter-fortiguard-categories"
                  primaryKey: "People"
              - action: "default"
                category:
                  datasource: "security/video-filter-fortiguard-categories"
                  primaryKey: "Society"
              - action: "default"
                category:
                  datasource: "security/video-filter-fortiguard-categories"
                  primaryKey: "Sports"
  


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

