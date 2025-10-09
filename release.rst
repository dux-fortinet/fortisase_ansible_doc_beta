Release Notes
==============================

Release Galaxy 1.1.0
~~~~~~~~~~~~~~~~~~~~

Minor Changes
-------------

- Modify the code to be compatible with Python 2.7;
- Support 8 new modules;

Breaking Changes / Porting Guide
--------------------------------

- Change camelCase to snake_case for all module parameters;

New Modules
-----------

- fortinet.fortisase.endpoint_policies_clone - Endpoint Policy Resource
- fortinet.fortisase.endpoints_access_proxy_authorize - ZTNA Access Proxies monitor
- fortinet.fortisase.endpoints_access_proxy_disconnect - ZTNA Access Proxies monitor
- fortinet.fortisase.endpoints_disable_management - Endpoint management monitor
- fortinet.fortisase.endpoints_enable_management - Endpoint management monitor
- fortinet.fortisase.security_profile_group_clone - Profile Group Resource
- fortinet.fortisase.user_swg_sessions_deauth - User monitor
- fortinet.fortisase.user_vpn_sessions_deauth - User monitor

Release Galaxy 1.0.0
~~~~~~~~~~~~~~~~~~~~

- Initial release of the FortiSASE Ansible Collection.