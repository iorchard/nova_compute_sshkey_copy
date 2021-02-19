Nova compute sshkey copy playbook
=====================================

This is an ansible playbook to copy a ssh key to nova compute nodes.

It is needed for instance cold migration and live migration with block 
migration.

Usage
-------

Edit roles/nova-compute-sshkey-copy/default/main.yml.::

   ---
   # defaults file for nova-compute-sshkey-copy
   nova_gid: 42436
   nova_uid: 42436
   nova_home: "/var/lib/nova"
   sshkey_dir: "/tmp/sshkey"

Change nova_gid, nova_uid, and nova_home for your environment.

There is a sample inventory file - inventory.ini.sample.
Copy and edit it for your environment.

Assumption

* admin node can log into compute nodes without password.
* The user running the playbook has passwordless sudo privilege on admin node
  and compute nodes.

Run the playbook.::

    ansible-playbook -i <inventory_file> nova-compute-sshkey-copy.yml
