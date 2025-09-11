endpoint_connection_profiles - Connection Profile Resource
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.0.0

.. contents::
   :local:
   :depth: 1

Synopsis
--------
Connection Profile Resource.

Use API "/resource-api/v2/endpoint/connection-profiles/{primaryKey}".

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
 <li><span class="li-head">params</span> The parameters of the module.<span class="li-required">[Required]</span><span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">primaryKey</span> <span class="li-required">[Required]</span><span class="li-normal">type: str</span></li>
 <li><span class="li-head">connectToFortiSASE</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['automatically', 'manually']</span></li>
 <li><span class="li-head">lockdown</span> <span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">status</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">gracePeriod</span> <span class="li-normal">type: int</span></li>
 <li><span class="li-head">maxAttempts</span> <span class="li-normal">type: int</span></li>
 <li><span class="li-head">ips</span> <span class="li-normal">type: list</span><span class="li-normal">elements: dict</span> <ul class="ul-self"> <li><span class="li-head">ip</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">port</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">protocol</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['', 'icmp', 'tcp', 'udp']</span></li>
 </ul></li>
 <li><span class="li-head">domains</span> <span class="li-normal">type: list</span><span class="li-normal">elements: dict</span> <ul class="ul-self"> <li><span class="li-head">address</span> <span class="li-normal">type: str</span></li>
 </ul></li>
 <li><span class="li-head">detectCaptivePortal</span> <span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">status</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 </ul></li>
 </ul></li>
 <li><span class="li-head">onFabricRuleSet</span> <span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">primaryKey</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">datasource</span> <span class="li-normal">type: str</span></li>
 </ul></li>
 <li><span class="li-head">offNetSplitTunnel</span> <span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">localApps</span> <span class="li-normal">type: list</span><span class="li-normal">elements: str</span></li>
 <li><span class="li-head">isdbs</span> <span class="li-normal">type: list</span><span class="li-normal">elements: dict</span> <ul class="ul-self"> <li><span class="li-head">primaryKey</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">datasource</span> <span class="li-normal">type: str</span></li>
 </ul></li>
 <li><span class="li-head">fqdns</span> <span class="li-normal">type: list</span><span class="li-normal">elements: str</span></li>
 <li><span class="li-head">subnets</span> <span class="li-normal">type: list</span><span class="li-normal">elements: dict</span> <ul class="ul-self"> <li><span class="li-head">primaryKey</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">datasource</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['network/host-groups', 'network/hosts']</span></li>
 </ul></li>
 <li><span class="li-head">subnetsIpsec</span> <span class="li-normal">type: list</span><span class="li-normal">elements: str</span></li>
 </ul></li>
 <li><span class="li-head">splitTunnel</span> <span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">localApps</span> <span class="li-normal">type: list</span><span class="li-normal">elements: str</span></li>
 <li><span class="li-head">isdbs</span> <span class="li-normal">type: list</span><span class="li-normal">elements: dict</span> <ul class="ul-self"> <li><span class="li-head">primaryKey</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">datasource</span> <span class="li-normal">type: str</span></li>
 </ul></li>
 <li><span class="li-head">fqdns</span> <span class="li-normal">type: list</span><span class="li-normal">elements: str</span></li>
 <li><span class="li-head">subnets</span> <span class="li-normal">type: list</span><span class="li-normal">elements: dict</span> <ul class="ul-self"> <li><span class="li-head">primaryKey</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">datasource</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['network/host-groups', 'network/hosts']</span></li>
 </ul></li>
 <li><span class="li-head">subnetsIpsec</span> <span class="li-normal">type: list</span><span class="li-normal">elements: str</span></li>
 </ul></li>
 <li><span class="li-head">allowInvalidServerCertificate</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">endpointOnNetBypass</span> <span class="li-normal">type: bool</span></li>
 <li><span class="li-head">authBeforeUserLogon</span> <span class="li-normal">type: bool</span></li>
 <li><span class="li-head">secureInternetAccess</span> <span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">authenticateWithSSO</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">enableLocalLan</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">externalBrowserSamlLogin</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 </ul></li>
 <li><span class="li-head">preferredDTLSTunnel</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">useGuiSamlAuth</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">allowPersonalVpns</span> <span class="li-normal">type: bool</span></li>
 <li><span class="li-head">mtuSize</span> <span class="li-normal">type: int</span></li>
 <li><span class="li-head">availableVPNs</span> <span class="li-normal">type: list</span><span class="li-normal">elements: dict</span> <ul class="ul-self"> <li><span class="li-head">type</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['ipSecVPN', 'sslVPN']</span></li>
 <li><span class="li-head">name</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">remoteGateway</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">usernamePrompt</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">saveUsername</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">showAlwaysUp</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">showAutoConnect</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">showRememberPassword</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">authenticateWithSSO</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">enableLocalLan</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">externalBrowserSamlLogin</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">port</span> <span class="li-normal">type: int</span></li>
 <li><span class="li-head">requireCertificate</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">authMethod</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['preSharedKey', 'smartCardCert', 'systemStoreCert']</span></li>
 <li><span class="li-head">showPasscode</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">preSharedKey</span> <span class="li-normal">type: str</span></li>
 </ul></li>
 <li><span class="li-head">showDisconnectBtn</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">enableInvalidServerCertWarning</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">preLogon</span> <span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">vpnType</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['ipSecVPN', 'sslVPN']</span></li>
 <li><span class="li-head">remoteGateway</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">commonName</span> <span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">matchType</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['regex', 'wildcard']</span></li>
 <li><span class="li-head">pattern</span> <span class="li-normal">type: str</span></li>
 </ul></li>
 <li><span class="li-head">issuer</span> <span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">matchType</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['regex', 'wildcard']</span></li>
 <li><span class="li-head">pattern</span> <span class="li-normal">type: str</span></li>
 </ul></li>
 <li><span class="li-head">port</span> <span class="li-normal">type: int</span></li>
 </ul></li>
 </ul></li>
 </ul>



Examples
-------------

.. code-block:: yaml

  - name: Update connection profile
    hosts: fortisase
    gather_facts: false
    tasks:
      - name: Create a new endpoint profile, do nothing if the endpoint profile already exists
        fortinet.fortisase.endpoint_policies:
          state: present
          params:
            primaryKey: "policy1"
            enabled: true
      - name: Update connection profile
        fortinet.fortisase.endpoint_connection_profiles:
          params:
            primaryKey: "policy1"
            allowInvalidServerCertificate: "enable"
            allowPersonalVpns: false
            authBeforeUserLogon: false
            availableVPNs: []
            connectToFortiSASE: "manually"
            enableInvalidServerCertWarning: "disable"
            endpointOnNetBypass: false
            preferredDTLSTunnel: "enable"
            secureInternetAccess:
              authenticateWithSSO: "disable"
              externalBrowserSamlLogin: "disable"
            useGuiSamlAuth: "disable"
  


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

