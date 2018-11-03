Role : ansible-role-terraform
===========================

Installs Terraform

Currently tested on these Operating Systems
* RHEL/CentOS/Oracle
* Windows 2-12 R2


Requirements
------------

Ansible 2.4 or higher

Role Variables
--------------

```
terraform_version        : Version of Terraform to be installed (latest if set to latest)
terraform_checkpoint_url : Terraform information URL location e.g. https://checkpoint-api.hashicorp.com/v1/check/terraform
terraform_arch           : Architecture of processor for URL location e.g. amd64
terraform_zipfile        : Name of the ZIP file to be downloaded
terraform_os             : Operating System name for URL location 
terraform_path           : Path to install downloaded executable
terraform_tmp            : Temporary download location
verbosity_level          : The level at which verbose output is display e.g. -vv = 2
```

Dependencies
------------

None

Example Playbook
----------------
Running with elevated privileges if unzip package needing to be installed and package is being installed to default /usr/local/bin on Linux.  

```
---
- name: Install Terraform
  hosts: all
  become: True

  roles:
    - name: Terraform client install
      role: ansible-role-terraform
```


Overiding default/prompted variables

```
ansible-playbook -i inventory terraform.yml -e "terraform_version=0.10.3"
```

License
-------

MIT

Author Information
------------------

Tony Skidmore

Contributors
------------

Adam Goldsmith

