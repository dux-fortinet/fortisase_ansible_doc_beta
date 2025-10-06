security_ssl_ssh_profile - SSL Inspection Profile Resource
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.0.0

.. contents::
   :local:
   :depth: 1

Synopsis
--------
SSL Inspection Profile Resource.

Use API "/resource-api/v2/security/ssl-ssh-profile/{direction}/{primaryKey}".

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
 <li><span class="li-head">inspection_mode</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['certificate-inspection', 'deep-inspection', 'no-inspection']</span></li>
 <li><span class="li-head">profile_protocol_options</span> <span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">unknown_content_encoding</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['block', 'bypass', 'inspect']</span></li>
 <li><span class="li-head">oversized_action</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['allow', 'block']</span></li>
 <li><span class="li-head">compressed_limit</span> <span class="li-normal">type: int</span></li>
 <li><span class="li-head">uncompressed_limit</span> <span class="li-normal">type: int</span></li>
 </ul></li>
 <li><span class="li-head">ca_certificate</span> <span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">primary_key</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">datasource</span> <span class="li-normal">type: str</span></li>
 </ul></li>
 <li><span class="li-head">expired_certificate_action</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['allow', 'block']</span></li>
 <li><span class="li-head">revoked_certificate_action</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['allow', 'block']</span></li>
 <li><span class="li-head">timed_out_validation_certificate_action</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['allow', 'block']</span></li>
 <li><span class="li-head">validation_failed_certificate_action</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['allow', 'block']</span></li>
 <li><span class="li-head">cert_probe_failure</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['allow', 'block']</span></li>
 <li><span class="li-head">quic</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['block', 'bypass', 'inspect']</span></li>
 <li><span class="li-head">host_exemptions</span> <span class="li-normal">type: list</span><span class="li-normal">elements: dict</span> <ul class="ul-self"> <li><span class="li-head">primary_key</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">datasource</span> <span class="li-normal">type: str</span></li>
 </ul></li>
 <li><span class="li-head">url_category_exemptions</span> <span class="li-normal">type: list</span><span class="li-normal">elements: dict</span> <ul class="ul-self"> <li><span class="li-head">primary_key</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">datasource</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['security/fortiguard-categories', 'security/fortiguard-local-categories']</span></li>
 </ul></li>
 </ul></li>
 </ul>



Examples
-------------

.. code-block:: yaml

  - name: Update security ssl ssh profile
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
      - name: Update security ssl ssh profile
        fortinet.fortisase.security_ssl_ssh_profile:
          params:
            direction: "{{ direction }}"
            primaryKey: "{{ profile_group }}"
            caCertificate:
              datasource: "system/certificate/ca-certificates"
              primaryKey: "Fortinet_CA_SSL"
            certProbeFailure: "allow"
            expiredCertificateAction: "block"
            inspectionMode: "certificate-inspection"
            revokedCertificateAction: "block"
            timedOutValidationCertificateAction: "allow"
            validationFailedCertificateAction: "block"
  


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

