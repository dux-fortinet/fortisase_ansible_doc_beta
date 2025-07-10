security_web_filter_profiles - Web Filter Profile Resource
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.0.0

.. contents::
   :local:
   :depth: 1

Synopsis
--------
Web Filter Profile Resource.

Use API "/resource-api/v2/security/web-filter-profiles/{primaryKey}".

Requirements
------------

The below requirements are needed on the host that executes this module.

- ansible>=2.17.0


Parameters
----------
.. raw:: html

 <ul>
 <li><span class="li-head">state</span> The state of the module. "present" means update the resource. This resource can't be deleted, and does not support "absent" state.<span class="li-normal">type: str</span><span class="li-normal">choices: ['present', 'absent']</span><span class="li-normal">default: present</span></li>
 <li><span class="li-head">force_method</span> Specify this option to force the method to use to interact with the resource.<span class="li-normal">type: str</span><span class="li-normal">choices: ['none', 'get', 'post', 'put', 'delete']</span><span class="li-normal">default: none</span></li>
 <li><span class="li-head">bypass_validation</span> Bypass validation of the module.<span class="li-normal">type: bool</span><span class="li-normal">default: False</span></li>
 <li><span class="li-head">params</span> The parameters of the module.<span class="li-required">[Required]</span><span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">primaryKey</span> <span class="li-required">[Required]</span><span class="li-normal">type: str</span></li>
 <li><span class="li-head">fortiguardFilters</span> <span class="li-normal">type: list</span><span class="li-normal">elements: dict</span> <ul class="ul-self"> <li><span class="li-head">action</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['allow', 'block', 'monitor', 'warning']</span></li>
 <li><span class="li-head">category</span> <span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">primaryKey</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">datasource</span> <span class="li-normal">type: str</span></li>
 </ul></li>
 <li><span class="li-head">warningDuration</span> <span class="li-normal">type: str</span></li>
 </ul></li>
 <li><span class="li-head">fortiguardLocalCategoryFilters</span> <span class="li-normal">type: list</span><span class="li-normal">elements: dict</span> <ul class="ul-self"> <li><span class="li-head">action</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['allow', 'block', 'disable', 'monitor', 'warning']</span></li>
 <li><span class="li-head">category</span> <span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">primaryKey</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">datasource</span> <span class="li-normal">type: str</span></li>
 </ul></li>
 <li><span class="li-head">warningDuration</span> <span class="li-normal">type: str</span></li>
 </ul></li>
 <li><span class="li-head">fqdnThreatFeedFilters</span> <span class="li-normal">type: list</span><span class="li-normal">elements: dict</span> <ul class="ul-self"> <li><span class="li-head">action</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['allow', 'block', 'disable', 'monitor', 'warning']</span></li>
 <li><span class="li-head">category</span> <span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">primaryKey</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">datasource</span> <span class="li-normal">type: str</span></li>
 </ul></li>
 <li><span class="li-head">warningDuration</span> <span class="li-normal">type: str</span></li>
 </ul></li>
 <li><span class="li-head">useFortiguardFilters</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">blockInvalidUrl</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">enforceSafeSearch</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">trafficOnRatingError</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">contentFilters</span> <span class="li-normal">type: list</span><span class="li-normal">elements: dict</span> <ul class="ul-self"> <li><span class="li-head">status</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">pattern</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">patternType</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['regexp', 'wildcard']</span></li>
 <li><span class="li-head">lang</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['cyrillic', 'french', 'japanese', 'korean', 'simch', 'spanish', 'thai', 'trach', 'western']</span></li>
 <li><span class="li-head">action</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['block', 'exempt']</span></li>
 <li><span class="li-head">score</span> <span class="li-normal">type: int</span></li>
 </ul></li>
 <li><span class="li-head">urlFilters</span> <span class="li-normal">type: list</span><span class="li-normal">elements: dict</span> <ul class="ul-self"> <li><span class="li-head">status</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">url</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">type</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['regex', 'simple', 'wildcard']</span></li>
 <li><span class="li-head">action</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['allow', 'block', 'exempt', 'monitor']</span></li>
 </ul></li>
 <li><span class="li-head">httpHeaders</span> <span class="li-normal">type: list</span><span class="li-normal">elements: dict</span> <ul class="ul-self"> <li><span class="li-head">name</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">action</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['add-to-request', 'add-to-response', 'remove-from-request', 'remove-from-response']</span></li>
 <li><span class="li-head">content</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">destinations</span> <span class="li-normal">type: list</span><span class="li-normal">elements: dict</span> <ul class="ul-self"> <li><span class="li-head">primaryKey</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">datasource</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['network/host-groups', 'network/hosts']</span></li>
 </ul></li>
 </ul></li>
 </ul></li>
 </ul>



Examples
-------------

.. code-block:: yaml

  - name: Update security web filter profiles
    hosts: fortisase
    gather_facts: false
    tasks:
      - name: Update security web filter profiles
        fortinet.fortisase.security_web_filter_profiles:
          params:
            primaryKey: "outbound" # internal or outbound
            blockInvalidUrl: "disable"
            contentFilters: []
            enforceSafeSearch: "disable"
            fqdnThreatFeedFilters: []
            httpHeaders: []
            trafficOnRatingError: "enable"
            urlFilters: []
            useFortiguardFilters: "enable"
  


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

