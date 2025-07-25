security_ssl_ssh_profiles - SSL Inspection Profile Resource
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.0.0

.. contents::
   :local:
   :depth: 1

Synopsis
--------
SSL Inspection Profile Resource.

Use API "/resource-api/v2/security/ssl-ssh-profiles/{primaryKey}".

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
 <li><span class="li-head">inspectionMode</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['certificate-inspection', 'deep-inspection', 'no-inspection']</span></li>
 <li><span class="li-head">profileProtocolOptions</span> <span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">unknownContentEncoding</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['block', 'bypass', 'inspect']</span></li>
 <li><span class="li-head">oversizedAction</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['allow', 'block']</span></li>
 <li><span class="li-head">compressedLimit</span> <span class="li-normal">type: int</span></li>
 <li><span class="li-head">uncompressedLimit</span> <span class="li-normal">type: int</span></li>
 </ul></li>
 <li><span class="li-head">caCertificate</span> <span class="li-normal">type: dict</span> <ul class="ul-self"> <li><span class="li-head">primaryKey</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">datasource</span> <span class="li-normal">type: str</span></li>
 </ul></li>
 <li><span class="li-head">expiredCertificateAction</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['allow', 'block']</span></li>
 <li><span class="li-head">revokedCertificateAction</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['allow', 'block']</span></li>
 <li><span class="li-head">timedOutValidationCertificateAction</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['allow', 'block']</span></li>
 <li><span class="li-head">validationFailedCertificateAction</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['allow', 'block']</span></li>
 <li><span class="li-head">certProbeFailure</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['allow', 'block']</span></li>
 <li><span class="li-head">hostExemptions</span> <span class="li-normal">type: list</span><span class="li-normal">elements: raw</span></li>
 <li><span class="li-head">urlCategoryExemptions</span> <span class="li-normal">type: list</span><span class="li-normal">elements: dict</span> <ul class="ul-self"> <li><span class="li-head">primaryKey</span> <span class="li-normal">type: str</span></li>
 <li><span class="li-head">datasource</span> <span class="li-normal">type: str</span><span class="li-normal">choices: ['security/fortiguard-categories', 'security/fortiguard-local-categories']</span></li>
 </ul></li>
 </ul></li>
 </ul>



Examples
-------------

.. code-block:: yaml

  - name: Update security ssl ssh profiles
    hosts: fortisase
    gather_facts: false
    tasks:
      - name: Update security ssl ssh profiles
        fortinet.fortisase.security_ssl_ssh_profiles:
          params:
            primaryKey: "outbound" # internal or outbound
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

