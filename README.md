# Gitea

[Gitea](https://gitea.io/en-us/) is a lightweight code hosting solution written in GO language.

## app.tpl
[Template](https://www.terraform.io/docs/providers/template/index.html) file for terraform.

**Purpose:**
Self prepared configuration file for gitea. It contains required configs used by gitea at startup. 

**Used by:**

 * Terraform: (terraform generated the value of "public_dns_var" --> DNS name of gitea server.
 
 * Ansible: Copy this terraform prepared file to target instance (gitea instance).
  
## gitea_install.yml
[Ansible playbook](https://docs.ansible.com/ansible/latest/user_guide/playbooks_intro.html#about-playbooks) to install gitea application.

**Purpose:**
Automated installation of application. 

**Used by:**

 * Terraform: Copy this playbook on affected instance.

 * Ansible: Run this playbook on affected instance.
 
## gitea.service
[SystemD Unit File](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/7/html/system_administrators_guide/sect-managing_services_with_systemd-unit_files) file for OS (RedHat / CentOS 7 )

**Purpose:**
Control application as service (start / stop / restart / reload / ...)

**Used by:**

 * OS: Control status of gitea application on target instance.
 
 * Ansible: Implement this service defintion.
  

