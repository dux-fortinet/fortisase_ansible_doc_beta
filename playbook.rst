Run Your First Playbook
==============================

This document explains how to run your first FortiSASE Ansible playbook.

Prepare host inventory file
~~~~~~~~~~~~~~~~~~~~~~~~~~~

Create a file named ``hosts`` in the current directory.

Please change the ``ansible_user`` and ``ansible_password`` to your own FortiSASE username and password.

If you don't want to specify the username and password in the inventory file, you can also specify them in environment variables ``FORTISASE_USERNAME`` and ``FORTISASE_PASSWORD``.

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
   # Authentication credentials (Specify the username and password in the inventory file or in environment variables)
   ansible_user="ABCDEFGHIJKLMNOPQRSTUVWXYZ" # You can also specify the username in environment variable FORTISASE_USERNAME
   ansible_password="123123123123123!1Aa" # You can also specify the password in environment variable FORTISASE_PASSWORD

Write the playbook
~~~~~~~~~~~~~~~~~~

Create a file named ``test.yml``:

::

  - name: Get FortiSASE Facts
    hosts: fortisase
    gather_facts: false
    tasks:
      - name: Query one network dns rule
        fortinet.fortisase.fortisase_facts:
          selector: "network_dns_rules"
          params:
            primaryKey: "1"
      - name: Query all network dns rules
        fortinet.fortisase.fortisase_facts:
          selector: "network_dns_rules"
          params:
            primaryKey: null


Run the playbook
~~~~~~~~~~~~~~~~

::

   ansible-playbook -i hosts test.yml

you can also observe the verbose output by adding option at the tail:
``-vvv``.

::

   ansible-playbook -i hosts test.yml -vvv

For all available modules, please refer to the :doc:`Modules Index <modules>`.

For more information, please refer to the :doc:`FAQ <faq>`.
