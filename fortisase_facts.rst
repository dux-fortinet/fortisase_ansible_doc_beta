.. _fortisase_facts:

fortisase_facts -- Gather FortiSASE Facts.
++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.0.0


.. contents::
   :local:
   :depth: 1


Requirements
------------
The below requirements are needed on the host that executes this module.

- ansible>=2.17.0


Parameters
----------
.. raw:: html

 <ul>
 <li><span class="li-head">selector</span> The selector of the facts.<span class="li-normal">type: str</span><span class="li-normal">required: True</span></li>
 <li><span class="li-head">params</span> The params of the facts. Different selectors have different required params.<span class="li-normal">type: dict</span></li>
 </ul>

 <table class="docutils">
 <thead>
 <tr>
 <th>Selector</th>
 <th>Required Params</th>
 <th>API</th>
 </tr>
 </thead>
 <tbody>
 
 <tr>
 <td>endpoints_access_proxy</td>
 <td></td>
 <td>/monitor-api/v1/endpoints/access-proxy</td>
 </tr>
 
 <tr>
 <td>endpoints_client_user_details</td>
 <td>client_user_id</td>
 <td>/monitor-api/v1/endpoints/client-user-details/{client_user_id}</td>
 </tr>
 
 <tr>
 <td>endpoints_details</td>
 <td>device_id</td>
 <td>/monitor-api/v1/endpoints/details/{device_id}</td>
 </tr>
 
 <tr>
 <td>endpoints_donut</td>
 <td>donut_type</td>
 <td>/monitor-api/v1/endpoints/donut/{donut_type}</td>
 </tr>
 
 <tr>
 <td>endpoints_endpoints_with_software</td>
 <td>software_id</td>
 <td>/monitor-api/v1/endpoints/endpoints-with-software/{software_id}</td>
 </tr>
 
 <tr>
 <td>endpoints_groups</td>
 <td>primary_key</td>
 <td>/monitor-api/v1/endpoints/groups/{primary_key}</td>
 </tr>
 
 <tr>
 <td>endpoints_software</td>
 <td></td>
 <td>/monitor-api/v1/endpoints/software</td>
 </tr>
 
 <tr>
 <td>endpoints_software_on_client_user</td>
 <td>client_user_id</td>
 <td>/monitor-api/v1/endpoints/software-on-client-user/{client_user_id}</td>
 </tr>
 
 <tr>
 <td>endpoints_software_on_endpoint</td>
 <td>device_id</td>
 <td>/monitor-api/v1/endpoints/software-on-endpoint/{device_id}</td>
 </tr>
 
 <tr>
 <td>endpoints_uid_tags</td>
 <td></td>
 <td>/monitor-api/v1/endpoints/uid-tags</td>
 </tr>
 
 <tr>
 <td>endpoints_users</td>
 <td></td>
 <td>/monitor-api/v1/endpoints/users</td>
 </tr>
 
 <tr>
 <td>endpoints_vulnerabilities</td>
 <td></td>
 <td>/monitor-api/v1/endpoints/vulnerabilities</td>
 </tr>
 
 <tr>
 <td>endpoints_vulnerabilities_endpoints</td>
 <td>vulnerability_id</td>
 <td>/monitor-api/v1/endpoints/vulnerabilities/{vulnerability_id}/endpoints</td>
 </tr>
 
 <tr>
 <td>endpoints_ztna_count</td>
 <td></td>
 <td>/monitor-api/v1/endpoints/ztna-count</td>
 </tr>
 
 <tr>
 <td>endpoints_ztna_tags</td>
 <td></td>
 <td>/monitor-api/v1/endpoints/ztna-tags</td>
 </tr>
 
 <tr>
 <td>security_botnet_domains</td>
 <td></td>
 <td>/monitor-api/v1/security/botnet-domains</td>
 </tr>
 
 <tr>
 <td>security_botnet_domains_stat</td>
 <td></td>
 <td>/monitor-api/v1/security/botnet-domains/stat</td>
 </tr>
 
 <tr>
 <td>traffic_history</td>
 <td></td>
 <td>/monitor-api/v1/traffic-history</td>
 </tr>
 
 <tr>
 <td>traffic_history_vpn_connections</td>
 <td></td>
 <td>/monitor-api/v1/traffic-history/vpn-connections</td>
 </tr>
 
 <tr>
 <td>user_swg_sessions</td>
 <td></td>
 <td>/monitor-api/v1/user/swg/sessions</td>
 </tr>
 
 <tr>
 <td>user_vpn_sessions</td>
 <td></td>
 <td>/monitor-api/v1/user/vpn/sessions</td>
 </tr>
 
 <tr>
 <td>auth_fsso_agents</td>
 <td>primary_key</td>
 <td>/resource-api/v2/auth/fsso-agents/{primary_key}</td>
 </tr>
 
 <tr>
 <td>auth_ldap_servers</td>
 <td>primary_key</td>
 <td>/resource-api/v2/auth/ldap-servers/{primary_key}</td>
 </tr>
 
 <tr>
 <td>auth_radius_servers</td>
 <td>primary_key</td>
 <td>/resource-api/v2/auth/radius-servers/{primary_key}</td>
 </tr>
 
 <tr>
 <td>auth_swg_saml_server</td>
 <td></td>
 <td>/resource-api/v2/auth/swg-saml-server</td>
 </tr>
 
 <tr>
 <td>auth_user_groups</td>
 <td>primary_key</td>
 <td>/resource-api/v2/auth/user-groups/{primary_key}</td>
 </tr>
 
 <tr>
 <td>auth_users</td>
 <td>primary_key</td>
 <td>/resource-api/v2/auth/users/{primary_key}</td>
 </tr>
 
 <tr>
 <td>auth_vpn_saml_server</td>
 <td></td>
 <td>/resource-api/v2/auth/vpn-saml-server</td>
 </tr>
 
 <tr>
 <td>dem_custom_saas_apps</td>
 <td>primary_key</td>
 <td>/resource-api/v2/dem/custom-saas-apps/{primary_key}</td>
 </tr>
 
 <tr>
 <td>dem_spa_applications</td>
 <td>primary_key</td>
 <td>/resource-api/v2/dem/spa-applications/{primary_key}</td>
 </tr>
 
 <tr>
 <td>endpoint_connection_profiles</td>
 <td>primary_key</td>
 <td>/resource-api/v2/endpoint/connection-profiles/{primary_key}</td>
 </tr>
 
 <tr>
 <td>endpoint_fsso_profiles</td>
 <td>primary_key</td>
 <td>/resource-api/v2/endpoint/fsso-profiles/{primary_key}</td>
 </tr>
 
 <tr>
 <td>endpoint_group_ad_user_profiles</td>
 <td>primary_key</td>
 <td>/resource-api/v2/endpoint/group-ad-user-profiles/{primary_key}</td>
 </tr>
 
 <tr>
 <td>endpoint_group_invitation_codes</td>
 <td>primary_key</td>
 <td>/resource-api/v2/endpoint/group-invitation-codes/{primary_key}</td>
 </tr>
 
 <tr>
 <td>endpoint_policies</td>
 <td>primary_key</td>
 <td>/resource-api/v2/endpoint/policies/{primary_key}</td>
 </tr>
 
 <tr>
 <td>endpoint_protection_profiles</td>
 <td>primary_key</td>
 <td>/resource-api/v2/endpoint/protection-profiles/{primary_key}</td>
 </tr>
 
 <tr>
 <td>endpoint_sandbox_profiles</td>
 <td>primary_key</td>
 <td>/resource-api/v2/endpoint/sandbox-profiles/{primary_key}</td>
 </tr>
 
 <tr>
 <td>endpoint_setting_profiles</td>
 <td>primary_key</td>
 <td>/resource-api/v2/endpoint/setting-profiles/{primary_key}</td>
 </tr>
 
 <tr>
 <td>endpoint_ztna_profiles</td>
 <td>primary_key</td>
 <td>/resource-api/v2/endpoint/ztna-profiles/{primary_key}</td>
 </tr>
 
 <tr>
 <td>endpoint_ztna_rules</td>
 <td>primary_key</td>
 <td>/resource-api/v2/endpoint/ztna-rules/{primary_key}</td>
 </tr>
 
 <tr>
 <td>endpoint_ztna_tags</td>
 <td>primary_key</td>
 <td>/resource-api/v2/endpoint/ztna-tags/{primary_key}</td>
 </tr>
 
 <tr>
 <td>infra_extenders</td>
 <td>primary_key</td>
 <td>/resource-api/v2/infra/extenders/{primary_key}</td>
 </tr>
 
 <tr>
 <td>infra_fortigates</td>
 <td>primary_key</td>
 <td>/resource-api/v2/infra/fortigates/{primary_key}</td>
 </tr>
 
 <tr>
 <td>infra_ssids</td>
 <td>primary_key</td>
 <td>/resource-api/v2/infra/ssids/{primary_key}</td>
 </tr>
 
 <tr>
 <td>network_basic_internet_services</td>
 <td>primary_key</td>
 <td>/resource-api/v2/network/basic-internet-services/{primary_key}</td>
 </tr>
 
 <tr>
 <td>network_dns_rules</td>
 <td>primary_key</td>
 <td>/resource-api/v2/network/dns-rules/{primary_key}</td>
 </tr>
 
 <tr>
 <td>network_host_groups</td>
 <td>primary_key</td>
 <td>/resource-api/v2/network/host-groups/{primary_key}</td>
 </tr>
 
 <tr>
 <td>network_hosts</td>
 <td>primary_key</td>
 <td>/resource-api/v2/network/hosts/{primary_key}</td>
 </tr>
 
 <tr>
 <td>network_implicit_dns_rules</td>
 <td>primary_key</td>
 <td>/resource-api/v2/network/implicit-dns-rules/{primary_key}</td>
 </tr>
 
 <tr>
 <td>network_internet_services</td>
 <td>primary_key</td>
 <td>/resource-api/v2/network/internet-services/{primary_key}</td>
 </tr>
 
 <tr>
 <td>network_wildcard_fqdn_customs</td>
 <td>primary_key</td>
 <td>/resource-api/v2/network/wildcard-fqdn-customs/{primary_key}</td>
 </tr>
 
 <tr>
 <td>security_antivirus_filetypes</td>
 <td>primary_key</td>
 <td>/resource-api/v2/security/antivirus-filetypes/{primary_key}</td>
 </tr>
 
 <tr>
 <td>security_antivirus_profile</td>
 <td>direction, primary_key</td>
 <td>/resource-api/v2/security/antivirus-profile/{direction}/{primary_key}</td>
 </tr>
 
 <tr>
 <td>security_antivirus_profiles</td>
 <td></td>
 <td>/resource-api/v2/security/antivirus-profiles</td>
 </tr>
 
 <tr>
 <td>security_app_custom_signatures</td>
 <td>primary_key</td>
 <td>/resource-api/v2/security/app-custom-signatures/{primary_key}</td>
 </tr>
 
 <tr>
 <td>security_application_categories</td>
 <td>primary_key</td>
 <td>/resource-api/v2/security/application-categories/{primary_key}</td>
 </tr>
 
 <tr>
 <td>security_application_control_profile</td>
 <td>direction, primary_key</td>
 <td>/resource-api/v2/security/application-control-profile/{direction}/{primary_key}</td>
 </tr>
 
 <tr>
 <td>security_application_control_profiles</td>
 <td></td>
 <td>/resource-api/v2/security/application-control-profiles</td>
 </tr>
 
 <tr>
 <td>security_applications</td>
 <td>primary_key</td>
 <td>/resource-api/v2/security/applications/{primary_key}</td>
 </tr>
 
 <tr>
 <td>security_dlp_data_types</td>
 <td>primary_key</td>
 <td>/resource-api/v2/security/dlp-data-types/{primary_key}</td>
 </tr>
 
 <tr>
 <td>security_dlp_dictionaries</td>
 <td>primary_key</td>
 <td>/resource-api/v2/security/dlp-dictionaries/{primary_key}</td>
 </tr>
 
 <tr>
 <td>security_dlp_exact_data_matches</td>
 <td>primary_key</td>
 <td>/resource-api/v2/security/dlp-exact-data-matches/{primary_key}</td>
 </tr>
 
 <tr>
 <td>security_dlp_file_patterns</td>
 <td>primary_key</td>
 <td>/resource-api/v2/security/dlp-file-patterns/{primary_key}</td>
 </tr>
 
 <tr>
 <td>security_dlp_fingerprint_databases</td>
 <td>primary_key</td>
 <td>/resource-api/v2/security/dlp-fingerprint-databases/{primary_key}</td>
 </tr>
 
 <tr>
 <td>security_dlp_profile</td>
 <td>direction, primary_key</td>
 <td>/resource-api/v2/security/dlp-profile/{direction}/{primary_key}</td>
 </tr>
 
 <tr>
 <td>security_dlp_profiles</td>
 <td></td>
 <td>/resource-api/v2/security/dlp-profiles</td>
 </tr>
 
 <tr>
 <td>security_dlp_sensors</td>
 <td>primary_key</td>
 <td>/resource-api/v2/security/dlp-sensors/{primary_key}</td>
 </tr>
 
 <tr>
 <td>security_dns_filter_profile</td>
 <td>direction, primary_key</td>
 <td>/resource-api/v2/security/dns-filter-profile/{direction}/{primary_key}</td>
 </tr>
 
 <tr>
 <td>security_dns_filter_profiles</td>
 <td></td>
 <td>/resource-api/v2/security/dns-filter-profiles</td>
 </tr>
 
 <tr>
 <td>security_domain_threat_feeds</td>
 <td>primary_key</td>
 <td>/resource-api/v2/security/domain-threat-feeds/{primary_key}</td>
 </tr>
 
 <tr>
 <td>security_endpoint_to_endpoint_policies</td>
 <td>primary_key</td>
 <td>/resource-api/v2/security/endpoint-to-endpoint-policies/{primary_key}</td>
 </tr>
 
 <tr>
 <td>security_file_filter_profile</td>
 <td>direction, primary_key</td>
 <td>/resource-api/v2/security/file-filter-profile/{direction}/{primary_key}</td>
 </tr>
 
 <tr>
 <td>security_file_filter_profiles</td>
 <td></td>
 <td>/resource-api/v2/security/file-filter-profiles</td>
 </tr>
 
 <tr>
 <td>security_fortiguard_categories</td>
 <td>primary_key</td>
 <td>/resource-api/v2/security/fortiguard-categories/{primary_key}</td>
 </tr>
 
 <tr>
 <td>security_fortiguard_local_categories</td>
 <td>primary_key</td>
 <td>/resource-api/v2/security/fortiguard-local-categories/{primary_key}</td>
 </tr>
 
 <tr>
 <td>security_geoip_countries</td>
 <td>primary_key</td>
 <td>/resource-api/v2/security/geoip-countries/{primary_key}</td>
 </tr>
 
 <tr>
 <td>security_internal_policies</td>
 <td>primary_key</td>
 <td>/resource-api/v2/security/internal-policies/{primary_key}</td>
 </tr>
 
 <tr>
 <td>security_internal_reverse_policies</td>
 <td>primary_key</td>
 <td>/resource-api/v2/security/internal-reverse-policies/{primary_key}</td>
 </tr>
 
 <tr>
 <td>security_ip_threat_feeds</td>
 <td>primary_key</td>
 <td>/resource-api/v2/security/ip-threat-feeds/{primary_key}</td>
 </tr>
 
 <tr>
 <td>security_ips_custom_signatures</td>
 <td>primary_key</td>
 <td>/resource-api/v2/security/ips-custom-signatures/{primary_key}</td>
 </tr>
 
 <tr>
 <td>security_ips_profile</td>
 <td>direction, primary_key</td>
 <td>/resource-api/v2/security/ips-profile/{direction}/{primary_key}</td>
 </tr>
 
 <tr>
 <td>security_ips_profiles</td>
 <td></td>
 <td>/resource-api/v2/security/ips-profiles</td>
 </tr>
 
 <tr>
 <td>security_onetime_schedules</td>
 <td>primary_key</td>
 <td>/resource-api/v2/security/onetime-schedules/{primary_key}</td>
 </tr>
 
 <tr>
 <td>security_outbound_policies</td>
 <td>primary_key</td>
 <td>/resource-api/v2/security/outbound-policies/{primary_key}</td>
 </tr>
 
 <tr>
 <td>security_profile_group</td>
 <td>direction, primary_key</td>
 <td>/resource-api/v2/security/profile-group/{direction}/{primary_key}</td>
 </tr>
 
 <tr>
 <td>security_profile_groups</td>
 <td>primary_key</td>
 <td>/resource-api/v2/security/profile-groups/{primary_key}</td>
 </tr>
 
 <tr>
 <td>security_recurring_schedules</td>
 <td>primary_key</td>
 <td>/resource-api/v2/security/recurring-schedules/{primary_key}</td>
 </tr>
 
 <tr>
 <td>security_schedule_groups</td>
 <td>primary_key</td>
 <td>/resource-api/v2/security/schedule-groups/{primary_key}</td>
 </tr>
 
 <tr>
 <td>security_service_categories</td>
 <td>primary_key</td>
 <td>/resource-api/v2/security/service-categories/{primary_key}</td>
 </tr>
 
 <tr>
 <td>security_service_groups</td>
 <td>primary_key</td>
 <td>/resource-api/v2/security/service-groups/{primary_key}</td>
 </tr>
 
 <tr>
 <td>security_services</td>
 <td>primary_key</td>
 <td>/resource-api/v2/security/services/{primary_key}</td>
 </tr>
 
 <tr>
 <td>security_ssl_ssh_profile</td>
 <td>direction, primary_key</td>
 <td>/resource-api/v2/security/ssl-ssh-profile/{direction}/{primary_key}</td>
 </tr>
 
 <tr>
 <td>security_ssl_ssh_profiles</td>
 <td></td>
 <td>/resource-api/v2/security/ssl-ssh-profiles</td>
 </tr>
 
 <tr>
 <td>security_url_threat_feeds</td>
 <td>primary_key</td>
 <td>/resource-api/v2/security/url-threat-feeds/{primary_key}</td>
 </tr>
 
 <tr>
 <td>security_video_filter_fortiguard_categories</td>
 <td>primary_key</td>
 <td>/resource-api/v2/security/video-filter-fortiguard-categories/{primary_key}</td>
 </tr>
 
 <tr>
 <td>security_video_filter_profile</td>
 <td>direction, primary_key</td>
 <td>/resource-api/v2/security/video-filter-profile/{direction}/{primary_key}</td>
 </tr>
 
 <tr>
 <td>security_video_filter_profiles</td>
 <td></td>
 <td>/resource-api/v2/security/video-filter-profiles</td>
 </tr>
 
 <tr>
 <td>security_video_filter_youtube_key</td>
 <td></td>
 <td>/resource-api/v2/security/video-filter-youtube-key</td>
 </tr>
 
 <tr>
 <td>security_web_filter_profile</td>
 <td>direction, primary_key</td>
 <td>/resource-api/v2/security/web-filter-profile/{direction}/{primary_key}</td>
 </tr>
 
 <tr>
 <td>security_web_filter_profiles</td>
 <td></td>
 <td>/resource-api/v2/security/web-filter-profiles</td>
 </tr>
 
 <tr>
 <td>usage_auth_fsso_agents</td>
 <td>primary_key</td>
 <td>/resource-api/v2/usage/auth/fsso-agents/{primary_key}</td>
 </tr>
 
 <tr>
 <td>usage_auth_ldap_servers</td>
 <td>primary_key</td>
 <td>/resource-api/v2/usage/auth/ldap-servers/{primary_key}</td>
 </tr>
 
 <tr>
 <td>usage_auth_radius_servers</td>
 <td>primary_key</td>
 <td>/resource-api/v2/usage/auth/radius-servers/{primary_key}</td>
 </tr>
 
 <tr>
 <td>usage_auth_user_groups</td>
 <td>primary_key</td>
 <td>/resource-api/v2/usage/auth/user-groups/{primary_key}</td>
 </tr>
 
 <tr>
 <td>usage_endpoint_ztna_tags</td>
 <td>primary_key</td>
 <td>/resource-api/v2/usage/endpoint/ztna-tags/{primary_key}</td>
 </tr>
 
 <tr>
 <td>usage_infra_ssids</td>
 <td>primary_key</td>
 <td>/resource-api/v2/usage/infra/ssids/{primary_key}</td>
 </tr>
 
 <tr>
 <td>usage_network_host_groups</td>
 <td>primary_key</td>
 <td>/resource-api/v2/usage/network/host-groups/{primary_key}</td>
 </tr>
 
 <tr>
 <td>usage_network_hosts</td>
 <td>primary_key</td>
 <td>/resource-api/v2/usage/network/hosts/{primary_key}</td>
 </tr>
 
 <tr>
 <td>usage_security_app_custom_signatures</td>
 <td>primary_key</td>
 <td>/resource-api/v2/usage/security/app-custom-signatures/{primary_key}</td>
 </tr>
 
 <tr>
 <td>usage_security_dlp_dictionaries</td>
 <td>primary_key</td>
 <td>/resource-api/v2/usage/security/dlp-dictionaries/{primary_key}</td>
 </tr>
 
 <tr>
 <td>usage_security_dlp_exact_data_matches</td>
 <td>primary_key</td>
 <td>/resource-api/v2/usage/security/dlp-exact-data-matches/{primary_key}</td>
 </tr>
 
 <tr>
 <td>usage_security_dlp_file_patterns</td>
 <td>primary_key</td>
 <td>/resource-api/v2/usage/security/dlp-file-patterns/{primary_key}</td>
 </tr>
 
 <tr>
 <td>usage_security_dlp_fingerprint_databases</td>
 <td>primary_key</td>
 <td>/resource-api/v2/usage/security/dlp-fingerprint-databases/{primary_key}</td>
 </tr>
 
 <tr>
 <td>usage_security_dlp_sensors</td>
 <td>primary_key</td>
 <td>/resource-api/v2/usage/security/dlp-sensors/{primary_key}</td>
 </tr>
 
 <tr>
 <td>usage_security_domain_threat_feeds</td>
 <td>primary_key</td>
 <td>/resource-api/v2/usage/security/domain-threat-feeds/{primary_key}</td>
 </tr>
 
 <tr>
 <td>usage_security_endpoint_to_endpoint_policies</td>
 <td>primary_key</td>
 <td>/resource-api/v2/usage/security/endpoint-to-endpoint-policies/{primary_key}</td>
 </tr>
 
 <tr>
 <td>usage_security_fortiguard_local_categories</td>
 <td>primary_key</td>
 <td>/resource-api/v2/usage/security/fortiguard-local-categories/{primary_key}</td>
 </tr>
 
 <tr>
 <td>usage_security_internal_policies</td>
 <td>primary_key</td>
 <td>/resource-api/v2/usage/security/internal-policies/{primary_key}</td>
 </tr>
 
 <tr>
 <td>usage_security_internal_reverse_policies</td>
 <td>primary_key</td>
 <td>/resource-api/v2/usage/security/internal-reverse-policies/{primary_key}</td>
 </tr>
 
 <tr>
 <td>usage_security_ip_threat_feeds</td>
 <td>primary_key</td>
 <td>/resource-api/v2/usage/security/ip-threat-feeds/{primary_key}</td>
 </tr>
 
 <tr>
 <td>usage_security_ips_custom_signatures</td>
 <td>primary_key</td>
 <td>/resource-api/v2/usage/security/ips-custom-signatures/{primary_key}</td>
 </tr>
 
 <tr>
 <td>usage_security_onetime_schedules</td>
 <td>primary_key</td>
 <td>/resource-api/v2/usage/security/onetime-schedules/{primary_key}</td>
 </tr>
 
 <tr>
 <td>usage_security_outbound_policies</td>
 <td>primary_key</td>
 <td>/resource-api/v2/usage/security/outbound-policies/{primary_key}</td>
 </tr>
 
 <tr>
 <td>usage_security_profile_group</td>
 <td>direction, primary_key</td>
 <td>/resource-api/v2/usage/security/profile-group/{direction}/{primary_key}</td>
 </tr>
 
 <tr>
 <td>usage_security_recurring_schedules</td>
 <td>primary_key</td>
 <td>/resource-api/v2/usage/security/recurring-schedules/{primary_key}</td>
 </tr>
 
 <tr>
 <td>usage_security_schedule_groups</td>
 <td>primary_key</td>
 <td>/resource-api/v2/usage/security/schedule-groups/{primary_key}</td>
 </tr>
 
 <tr>
 <td>usage_security_service_groups</td>
 <td>primary_key</td>
 <td>/resource-api/v2/usage/security/service-groups/{primary_key}</td>
 </tr>
 
 <tr>
 <td>usage_security_services</td>
 <td>primary_key</td>
 <td>/resource-api/v2/usage/security/services/{primary_key}</td>
 </tr>
 
 <tr>
 <td>usage_security_url_threat_feeds</td>
 <td>primary_key</td>
 <td>/resource-api/v2/usage/security/url-threat-feeds/{primary_key}</td>
 </tr>
 
 <tr>
 <td>private_access_network_configuration</td>
 <td></td>
 <td>/resource-api/v1/private-access/network-configuration</td>
 </tr>
 
 <tr>
 <td>private_access_service_connections</td>
 <td>service_connection_id</td>
 <td>/resource-api/v1/private-access/service-connections/{service_connection_id}</td>
 </tr>
 
 <tr>
 <td>security_cert_local_certs</td>
 <td>primary_key</td>
 <td>/resource-api/v1/security/cert/local-certs/{primary_key}</td>
 </tr>
 
 <tr>
 <td>security_cert_remote_ca_certs</td>
 <td>primary_key</td>
 <td>/resource-api/v1/security/cert/remote-ca-certs/{primary_key}</td>
 </tr>
 
 <tr>
 <td>security_pki_users</td>
 <td>primary_key</td>
 <td>/resource-api/v1/security/pki-users/{primary_key}</td>
 </tr>
 
 </tbody>
 </table>

Examples
-------------

.. code-block:: yaml

 - name: Get FortiSASE Facts
   hosts: fortisase
   gather_facts: false
   tasks:
     - name: Query one network dns rule
       fortinet.fortisase.fortisase_facts:
         selector: "network_dns_rules"
         params:
           primary_key: "1"
     - name: Query all network dns rules
       fortinet.fortisase.fortisase_facts:
         selector: "network_dns_rules"
         params:
           primary_key: null


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
