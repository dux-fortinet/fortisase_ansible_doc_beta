Frequently Asked Questions (FAQ)
================================

|

**TABLE OF CONTENTS:**
 - `How to specify the username and password?`_
 - `Common Parameters`_
 - `How to enable logging?`_
 - `Error: No fact modules available and we could not find a fact module for your network OS`_

|


How to specify the username and password?
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

You can specify the username and password in the inventory file or in environment variables.

Inventory file:

::

   [fortisase]
   public_cloud ansible_host=portal.prod.fortisase.com
   # private_cloud ansible_host=<your_private_cloud_address>

   [fortisase:vars]
   ansible_network_os=fortinet.fortisase.fortisase
   ansible_connection=httpapi
   ansible_facts_modules=setup
   ansible_httpapi_port=443
   ansible_httpapi_use_ssl=true
   ansible_httpapi_validate_certs=false
   # Authentication credentials, specify the username and password in the inventory file
   ansible_user="ABCDEFGHIJKLMNOPQRSTUVWXYZ"
   ansible_password="123123123123123!1Aa"


Environment variables:

::

   # Authentication credentials, specify the username and password in environment variables
   export FORTISASE_USERNAME="ABCDEFGHIJKLMNOPQRSTUVWXYZ"
   export FORTISASE_PASSWORD="123123123123123!1Aa"

   # run playbook
   ansible-playbook -i <inventory_file_name> <playbook_file_name>

Common Parameters
~~~~~~~~~~~~~~~~~

Almost all modules support the following parameters (except for ``fortisase_generic`` and ``fortisase_facts``):

- ``state``
- ``force_method``
- ``bypass_validation``
- ``params``


Examples:

::

  - name: Add/Update Network DNS Rule
    hosts: fortisase
    gather_facts: false
    tasks:
      - name: Add/Update Network DNS Rule
        fortinet.fortisase.network_dns_rules:
          state: present
          # force_method: post # if you want to force to use the POST method
          # bypass_validation: true # if you want to bypass the Ansible built-in validation
          params:
            primaryKey: "1"
            primaryDns: "1.1.1.1"
            secondaryDns: "1.1.1.2"
            domains:
              - www.facebook.com
              - www.google.com
            popDnsOverride: {}

state
^^^^^

This parameter is used to control the state of the resource.

- "present" means create or update the resource.
- "absent" means delete the resource.

The default value is "present", so a resource will be created if it doesn't exist, and updated if it already exists.

Alough ``state`` is supported by almost all modules, some resources in FortiSASE can't be deleted, so the corresponding modules can not set state to "absent".


force_method
^^^^^^^^^^^^

We do not encourage to use ``force_method`` except that you are sure the API definition is wrong and you want to fix them on you own immediately.

This parameter is used to force the HTTP request method to use to interact with the FortiSASE API.

- "none" means don't force to use any method. The module handles the interaction with the resource based on the API definition.
- "get" means force to use the GET method.
- "post" means force to use the POST method.
- "put" means force to use the PUT method.
- "delete" means force to use the DELETE method.

The default value is "none".

bypass_validation
^^^^^^^^^^^^^^^^^

We do not encourage to use ``bypass_validation`` except that you are sure something is wrong with the parameter definition and you want to fix them on you own immediately.

This boolean parameter is used to bypass the Ansible built-in validation.

By setting `bypass_validation` to `true`, the content of parameters is not examined, thus enabling you to send any parameters to FortiAnalyzer backend server.

To use this parameter, you are likely to look up the defnition for an API on `fortiapi spec page`_. 


params
^^^^^^

This parameter is used to pass the parameters to the FortiSASE API.

Please refer to the "Parameters" section in the module document page for the details of the parameters.


How to enable logging?
~~~~~~~~~~~~~~~~~~~~~~

Set environment variable ``FORTISASE_ENABLE_LOG`` to ``true`` to enable logging.

::

   export FORTISASE_ENABLE_LOG=true

Then, log data will be appended to the log file ``/tmp/fortisase.ansible.log``.


Error: No fact modules available and we could not find a fact module for your network OS
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Solution 1 (Recommended): Add vars "ansible_facts_modules: setup" to the inventory file to avoid this error.
`What is inventory file?`_

::

   [fortisase]
   public_cloud ansible_host=portal.prod.fortisase.com
   # private_cloud ansible_host=<your_private_cloud_address>

   [fortisase:vars]
   ansible_network_os=fortinet.fortisase.fortisase
   ansible_connection=httpapi
   ansible_facts_modules=setup # add here
   ansible_httpapi_port=443
   ansible_httpapi_use_ssl=true
   ansible_httpapi_validate_certs=false
   # Authentication credentials (Specify the username and password in the inventory file or in environment variables)
   ansible_user="ABCDEFGHIJKLMNOPQRSTUVWXYZ" # You can also specify the username in environment variable FORTISASE_USERNAME
   ansible_password="123123123123123!1Aa" # You can also specify the password in environment variable FORTISASE_PASSWORD


Solution 2: Add vars "ansible_facts_modules: setup" to your playbook.

::

  - name: Get FortiSASE Facts
    hosts: fortisase
    vars:
      ansible_facts_modules: setup # add here
    tasks:
      - name: Query one network dns rule
        fortinet.fortisase.fortisase_facts:
          selector: "network_dns_rules"
          params:
            primaryKey: "1"

Solution 3: Add "gather_facts: false" to your playbook.

::

  - name: Get FortiSASE Facts
    hosts: fortisase
    gather_facts: false # add here
    tasks:
      - name: Query one network dns rule
        fortinet.fortisase.fortisase_facts:
          selector: "network_dns_rules"
          params:
            primaryKey: "1"

.. _fortiapi spec page: https://fndn.fortinet.net/index.php?/fortiapi/2625-fortisase/
.. _What is inventory file?: https://docs.ansible.com/ansible/latest/inventory_guide/intro_inventory.html