Frequently Asked Questions (FAQ)
================================

|

**TABLE OF CONTENTS:**
 - `What You Need To Know About Logging.`_
 - `When to Use Parameter bypass_validation?`_
 - `Error: No fact modules available and we could not find a fact module for your network OS`_

|

What You Need To Know About Logging. 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Set environment variable ``FORTISASE_ENABLE_LOG`` to ``true`` to enable logging.

::

   export FORTISASE_ENABLE_LOG=true

Then, log data will be appended to the log file ``/tmp/fortisase.ansible.log``.


When to Use Parameter bypass_validation?
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

You are not encouraged to use ``bypass_validation`` except that you are sure something is wrong with the parameter definition and you want to fix them on you own immediately.
by setting `bypass_validation` to `True`, the content of parameters is not examined, thus enabling you to send any parameters to FortiAnalyzer backend server.

To use this parameter, you are likely to look up the defnition for an API on `fortiapi spec page`_. 



Error: No fact modules available and we could not find a fact module for your network OS
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Solution 1 (Recommended): Add vars "ansible_facts_modules: setup" to the host file to avoid this error.
`What is host file?`_

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
   # ansible_user="ABCDEFGHIJKLMNOPQRSTUVWXYZ" # You can also specify the username in environment variable FORTISASE_USERNAME
   # ansible_password="123123123123123!1Aa" # You can also specify the password in environment variable FORTISASE_PASSWORD


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
.. _What is host file?: https://docs.ansible.com/ansible/latest/inventory_guide/intro_inventory.html