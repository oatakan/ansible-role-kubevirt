# kubevirt
This repo contains an Ansible role that provision one more VMs onto kubevirt/OpenShift Container-native Virtualization (CNV) environment.

Requirements
------------

You need to have the following packages installed on your control machine:

- mkisofs
- genisoimage

Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - name: provision a new vm
      hosts: all
      gather_facts: False
      connection: local
      become: no
      vars:
        target_namespace: openshift-cnv
        template_namespace: openshift-cnv
        pvc_storage_class: hostpath-provisioner
        kubevirt_upload_proxy_url: https://localhost:443
        nodes:
          - name: rhel81test1
            role: rhel
            app_name: kubevirt_test
            memory: 4096
            cpu: 2
            template: rhel81-x64-v1   # there should be a DV with this name on kubernetes/OpenShift environment

License
-------

MIT

Author Information
------------------

Orcun Atakan
