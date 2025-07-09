endpoint_connection_profiles - Connection Profile Resource API V2 for FortiSASE
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.0.0

.. contents::
   :local:
   :depth: 1

Synopsis
--------
Connection Profile Resource API V2 for FortiSASE

Requirements
------------

The below requirements are needed on the host that executes this module.

- ansible>=2.17.0


Parameters
----------
.. raw:: html

 <ul>
 <li><span class="li-head">state</span> The state of the module.<span class="li-normal">type: str</span><span class="li-normal">choices: ['present', 'absent']</span><span class="li-normal">default: present</span></li>
 <li><span class="li-head">force_method</span> Specify this option to force the method to use to interact with the resource.<span class="li-normal">type: str</span><span class="li-normal">choices: ['none', 'read', 'create', 'update', 'delete']</span><span class="li-normal">default: none</span></li>
 <li><span class="li-head">bypass_validation</span> Bypass validation of the module.<span class="li-normal">type: bool</span><span class="li-normal">default: False</span></li>
 <li><span class="li-head">params</span> The parameters of the module.<span class="li-normal">type: dict</span><span class="li-normal">required: True</span></li>
 <ul class="ul-self"> <li><span class="li-head">primaryKey</span> <span class="li-normal">type: str</span><span class="li-normal">required: True</span></li>
 <li><span class="li-head">connectToFortiSASE</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['automatically', 'manually']</span></li>
 <li><span class="li-head">lockdown</span> <span class="li-normal">type: dict</span></li>
 <li><span class="li-head">onFabricRuleSet</span> <span class="li-normal">type: dict</span></li>
 <li><span class="li-head">offNetSplitTunnel</span> <span class="li-normal">type: dict</span></li>
 <li><span class="li-head">splitTunnel</span> <span class="li-normal">type: dict</span></li>
 <li><span class="li-head">allowInvalidServerCertificate</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">endpointOnNetBypass</span> <span class="li-normal">type: bool</span></li>
 <li><span class="li-head">authBeforeUserLogon</span> <span class="li-normal">type: bool</span></li>
 <li><span class="li-head">secureInternetAccess</span> <span class="li-normal">type: dict</span></li>
 <li><span class="li-head">preferredDTLSTunnel</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">useGuiSamlAuth</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">allowPersonalVpns</span> <span class="li-normal">type: bool</span></li>
 <li><span class="li-head">availableVPNs</span> <span class="li-normal">type: list</span></li>
 <li><span class="li-head">showDisconnectBtn</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">enableInvalidServerCertWarning</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['disable', 'enable']</span></li>
 <li><span class="li-head">preLogon</span> <span class="li-normal">type: dict</span></li>
 </ul> </ul>



Examples
-------------

.. code-block:: yaml

  - name: Update policy connection-profiles
    hosts: fortisase
    gather_facts: false
    tasks:
      - name: Create policies, do nothing if already exists
        fortinet.fortisase.endpoint_policies:
          state: present
          params:
            primaryKey: "policy1"
            enabled: true
      - name: Update policy connection-profiles
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

