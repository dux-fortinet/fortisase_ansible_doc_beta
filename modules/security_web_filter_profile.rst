security_web_filter_profile - Web Filter Profile Resource
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.0.0

.. contents::
   :local:
   :depth: 1

Synopsis
--------
Web Filter Profile Resource.

Use API "/resource-api/v2/security/web-filter-profile/{direction}/{primaryKey}".

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
 <li><span class="li-head">primary_key</span> <span class="li-required">[Required]</span><span class="li-normal">type: str</span></li>
 <li><span class="li-head">fortiguard_filters</span> <span class="li-normal">type: list</span><span class="li-normal">elements: dict</span> <ul class="ul-self"> <li><span class="li-head">action</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['allow', 'block', 'monitor', 'warning']</span></li>
 <li><span class="li-head">category</span> <span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">primary_key</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">datasource</span> <span class="li-normal">type: str</span></li>
 </ul></li>
 <li><span class="li-head">warning_duration</span> <span class="li-normal">type: str</span></li>
 </ul></li>
 <li><span class="li-head">fortiguard_local_category_filters</span> <span class="li-normal">type: list</span><span class="li-normal">elements: dict</span> <ul class="ul-self"> <li><span class="li-head">action</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['allow', 'block', 'disable', 'monitor', 'warning']</span></li>
 <li><span class="li-head">category</span> <span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">primary_key</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">datasource</span> <span class="li-normal">type: str</span></li>
 </ul></li>
 <li><span class="li-head">warning_duration</span> <span class="li-normal">type: str</span></li>
 </ul></li>
 <li><span class="li-head">fqdn_threat_feed_filters</span> <span class="li-normal">type: list</span><span class="li-normal">elements: dict</span> <ul class="ul-self"> <li><span class="li-head">action</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['allow', 'block', 'disable', 'monitor', 'warning']</span></li>
 <li><span class="li-head">category</span> <span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">primary_key</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">datasource</span> <span class="li-normal">type: str</span></li>
 </ul></li>
 <li><span class="li-head">warning_duration</span> <span class="li-normal">type: str</span></li>
 </ul></li>
 <li><span class="li-head">use_fortiguard_filters</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">block_invalid_url</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">enforce_safe_search</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">traffic_on_rating_error</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">content_filters</span> <span class="li-normal">type: list</span><span class="li-normal">elements: dict</span> <ul class="ul-self"> <li><span class="li-head">status</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">pattern</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">pattern_type</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['regexp', 'wildcard']</span></li>
 <li><span class="li-head">lang</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['cyrillic', 'french', 'japanese', 'korean', 'simch', 'spanish', 'thai', 'trach', 'western']</span></li>
 <li><span class="li-head">action</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['block', 'exempt']</span></li>
 <li><span class="li-head">score</span> <span class="li-normal">type: int</span></li>
 </ul></li>
 <li><span class="li-head">url_filters</span> <span class="li-normal">type: list</span><span class="li-normal">elements: dict</span> <ul class="ul-self"> <li><span class="li-head">status</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">url</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">type</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['regex', 'simple', 'wildcard']</span></li>
 <li><span class="li-head">action</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['allow', 'block', 'exempt', 'monitor']</span></li>
 </ul></li>
 <li><span class="li-head">http_headers</span> <span class="li-normal">type: list</span><span class="li-normal">elements: dict</span> <ul class="ul-self"> <li><span class="li-head">name</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">action</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['add-to-request', 'add-to-response', 'remove-from-request', 'remove-from-response']</span></li>
 <li><span class="li-head">content</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">destinations</span> <span class="li-normal">type: list</span><span class="li-normal">elements: dict</span> <ul class="ul-self"> <li><span class="li-head">primary_key</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">datasource</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['network/host-groups', 'network/hosts']</span></li>
 </ul></li>
 </ul></li>
 </ul></li>
 </ul>



Examples
-------------

.. code-block:: yaml

  - name: Update security web filter profile
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
            primary_key: "{{ profile_group }}"
      - name: Update security web filter profile
        fortinet.fortisase.security_web_filter_profile:
          params:
            direction: "{{ direction }}"
            primary_key: "{{ profile_group }}"
            block_invalid_url: "disable"
            content_filters: []
            enforce_safe_search: "disable"
            fqdn_threat_feed_filters: []
            http_headers: []
            traffic_on_rating_error: "enable"
            url_filters: []
            use_fortiguard_filters: "enable"
  


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

