security_dns_filter_profile - DNS Filter Profile Resource
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.0.0

.. contents::
   :local:
   :depth: 1

Synopsis
--------
DNS Filter Profile Resource.

Use API "/resource-api/v2/security/dns-filter-profile/{direction}/{primaryKey}".

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
 <li><span class="li-head">use_for_edge_devices</span> <span class="li-normal">type: bool</span></li>
 <li><span class="li-head">use_fortiguard_filters</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">enable_all_logs</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">enable_botnet_blocking</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">enable_safe_search</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">allow_dns_requests_on_rating_error</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">dns_translation_entries</span> <span class="li-normal">type: list</span><span class="li-normal">elements: dict</span> <ul class="ul-self"> <li><span class="li-head">src</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">dst</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">netmask</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">status</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 </ul></li>
 <li><span class="li-head">domain_filters</span> <span class="li-normal">type: list</span><span class="li-normal">elements: dict</span> <ul class="ul-self"> <li><span class="li-head">url</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">type</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['regex', 'simple', 'wildcard']</span></li>
 <li><span class="li-head">action</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['allow', 'block', 'exempt', 'monitor']</span></li>
 <li><span class="li-head">enabled</span> <span class="li-normal">type: bool</span></li>
 </ul></li>
 <li><span class="li-head">fortiguard_filters</span> <span class="li-normal">type: list</span><span class="li-normal">elements: dict</span> <ul class="ul-self"> <li><span class="li-head">action</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['allow', 'block', 'monitor', 'warning']</span></li>
 <li><span class="li-head">category</span> <span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">primary_key</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">datasource</span> <span class="li-normal">type: str</span></li>
 </ul></li>
 </ul></li>
 <li><span class="li-head">domain_threat_feed_filters</span> <span class="li-normal">type: list</span><span class="li-normal">elements: dict</span> <ul class="ul-self"> <li><span class="li-head">action</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['allow', 'block', 'disable', 'monitor', 'warning']</span></li>
 <li><span class="li-head">category</span> <span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">primary_key</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">datasource</span> <span class="li-normal">type: str</span></li>
 </ul></li>
 </ul></li>
 </ul></li>
 </ul>



Examples
-------------

.. code-block:: yaml

  - name: Update security dns filter profile
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
      - name: Update security dns filter profile
        fortinet.fortisase.security_dns_filter_profile:
          params:
            direction: "{{ direction }}"
            primary_key: "{{ profile_group }}"
            use_for_edge_devices: false
            allow_dns_requests_on_rating_error: "enable"
            dns_translation_entries: []
            domain_filters: []
            domain_threat_feed_filters: []
            enable_all_logs: "disable"
            enable_botnet_blocking: "enable"
            enable_safe_search: "disable"
            use_fortiguard_filters: "enable"
            fortiguard_filters:
              - action: monitor
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Alternative Beliefs
              - action: monitor
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Abortion
              - action: monitor
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Other Adult Materials
              - action: monitor
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Advocacy Organizations
              - action: monitor
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Gambling
              - action: monitor
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Extremist Groups
              - action: monitor
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Nudity and Risque
              - action: monitor
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Pornography
              - action: monitor
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Dating
              - action: monitor
                category:
                  datasource: security/fortiguard-categories
                  primary_key: "Weapons (Sales)"
              - action: monitor
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Unrated
              - action: monitor
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Marijuana
              - action: monitor
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Sex Education
              - action: monitor
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Alcohol
              - action: monitor
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Tobacco
              - action: monitor
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Lingerie and Swimsuit
              - action: monitor
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Sports Hunting and War Games
              - action: block
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Malicious Websites
              - action: block
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Phishing
              - action: block
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Spam URLs
              - action: block
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Dynamic DNS
              - action: block
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Newly Observed Domain
              - action: block
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Newly Registered Domain
              - action: block
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Terrorism
              - action: block
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Crypto Mining
              - action: block
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Potentially Unwanted Program
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Drug Abuse
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Hacking
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Illegal or Unethical
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Discrimination
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Explicit Violence
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Proxy Avoidance
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Plagiarism
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Child Sexual Abuse
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Freeware and Software Downloads
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primary_key: File Sharing and Storage
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Streaming Media and Download
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Peer-to-peer File Sharing
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Internet Radio and TV
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Internet Telephony
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Advertising
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Brokerage and Trading
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Games
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Web-based Email
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Entertainment
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Arts and Culture
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Education
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Health and Wellness
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Job Search
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Medicine
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primary_key: News and Media
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Social Networking
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Political Organizations
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Reference
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Global Religion
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Shopping
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Society and Lifestyles
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Sports
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Travel
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Personal Vehicles
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Dynamic Content
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Meaningless Content
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Folklore
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Web Chat
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Instant Messaging
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Newsgroups and Message Boards
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Digital Postcards
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Child Education
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Real Estate
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Restaurant and Dining
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Personal Websites and Blogs
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Content Servers
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Domain Parking
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Personal Privacy
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Auction
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Finance and Banking
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Search Engines and Portals
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primary_key: General Organizations
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Business
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Information and Computer Security
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Government and Legal Organizations
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Information Technology
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Armed Forces
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Web Hosting
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Secure Websites
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Web-based Applications
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Charitable Organizations
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Remote Access
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Web Analytics
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Online Meeting
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primary_key: URL Shortening
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Artificial Intelligence Technology
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primary_key: Cryptocurrency
  


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

