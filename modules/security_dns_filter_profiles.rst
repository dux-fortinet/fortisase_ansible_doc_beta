security_dns_filter_profiles - DNS Filter Profile Resource
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.0.0

.. contents::
   :local:
   :depth: 1

Synopsis
--------
DNS Filter Profile Resource.

Use API "/resource-api/v2/security/dns-filter-profiles/{primaryKey}".

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
 <li><span class="li-head">useFortiguardFilters</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">enableAllLogs</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">enableBotnetBlocking</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">enableSafeSearch</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">allowDnsRequestsOnRatingError</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">dnsTranslationEntries</span> <span class="li-normal">type: list</span><span class="li-normal">elements: dict</span> <ul class="ul-self"> <li><span class="li-head">src</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">dst</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">netmask</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">status</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 </ul></li>
 <li><span class="li-head">domainFilters</span> <span class="li-normal">type: list</span><span class="li-normal">elements: dict</span> <ul class="ul-self"> <li><span class="li-head">url</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">type</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['regex', 'simple', 'wildcard']</span></li>
 <li><span class="li-head">action</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['allow', 'block', 'exempt', 'monitor']</span></li>
 <li><span class="li-head">enabled</span> <span class="li-normal">type: bool</span></li>
 </ul></li>
 <li><span class="li-head">fortiguardFilters</span> <span class="li-normal">type: list</span><span class="li-normal">elements: dict</span> <ul class="ul-self"> <li><span class="li-head">action</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['allow', 'block', 'monitor', 'warning']</span></li>
 <li><span class="li-head">category</span> <span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">primaryKey</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">datasource</span> <span class="li-normal">type: str</span></li>
 </ul></li>
 </ul></li>
 <li><span class="li-head">domainThreatFeedFilters</span> <span class="li-normal">type: list</span><span class="li-normal">elements: dict</span> <ul class="ul-self"> <li><span class="li-head">action</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['allow', 'block', 'disable', 'monitor', 'warning']</span></li>
 <li><span class="li-head">category</span> <span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">primaryKey</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">datasource</span> <span class="li-normal">type: str</span></li>
 </ul></li>
 </ul></li>
 </ul></li>
 </ul>



Examples
-------------

.. code-block:: yaml

  - name: Update security dns filter profiles
    hosts: fortisase
    gather_facts: false
    tasks:
      - name: Update security dns filter profiles
        fortinet.fortisase.security_dns_filter_profiles:
          params:
            primaryKey: "outbound" # internal or outbound
            allowDnsRequestsOnRatingError: "enable"
            dnsTranslationEntries: []
            domainFilters: []
            domainThreatFeedFilters: []
            enableAllLogs: "disable"
            enableBotnetBlocking: "enable"
            enableSafeSearch: "disable"
            useFortiguardFilters: "enable"
            fortiguardFilters:
              - action: monitor
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Alternative Beliefs
              - action: monitor
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Abortion
              - action: monitor
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Other Adult Materials
              - action: monitor
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Advocacy Organizations
              - action: monitor
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Gambling
              - action: monitor
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Extremist Groups
              - action: monitor
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Nudity and Risque
              - action: monitor
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Pornography
              - action: monitor
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Dating
              - action: monitor
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: "Weapons (Sales)"
              - action: monitor
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Unrated
              - action: monitor
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Marijuana
              - action: monitor
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Sex Education
              - action: monitor
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Alcohol
              - action: monitor
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Tobacco
              - action: monitor
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Lingerie and Swimsuit
              - action: monitor
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Sports Hunting and War Games
              - action: block
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Malicious Websites
              - action: block
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Phishing
              - action: block
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Spam URLs
              - action: block
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Dynamic DNS
              - action: block
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Newly Observed Domain
              - action: block
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Newly Registered Domain
              - action: block
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Terrorism
              - action: block
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Crypto Mining
              - action: block
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Potentially Unwanted Program
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Drug Abuse
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Hacking
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Illegal or Unethical
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Discrimination
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Explicit Violence
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Proxy Avoidance
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Plagiarism
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Child Sexual Abuse
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Freeware and Software Downloads
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: File Sharing and Storage
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Streaming Media and Download
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Peer-to-peer File Sharing
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Internet Radio and TV
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Internet Telephony
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Advertising
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Brokerage and Trading
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Games
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Web-based Email
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Entertainment
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Arts and Culture
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Education
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Health and Wellness
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Job Search
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Medicine
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: News and Media
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Social Networking
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Political Organizations
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Reference
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Global Religion
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Shopping
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Society and Lifestyles
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Sports
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Travel
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Personal Vehicles
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Dynamic Content
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Meaningless Content
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Folklore
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Web Chat
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Instant Messaging
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Newsgroups and Message Boards
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Digital Postcards
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Child Education
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Real Estate
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Restaurant and Dining
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Personal Websites and Blogs
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Content Servers
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Domain Parking
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Personal Privacy
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Auction
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Finance and Banking
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Search Engines and Portals
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: General Organizations
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Business
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Information and Computer Security
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Government and Legal Organizations
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Information Technology
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Armed Forces
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Web Hosting
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Secure Websites
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Web-based Applications
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Charitable Organizations
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Remote Access
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Web Analytics
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Online Meeting
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: URL Shortening
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Artificial Intelligence Technology
              - action: allow
                category:
                  datasource: security/fortiguard-categories
                  primaryKey: Cryptocurrency
  


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

