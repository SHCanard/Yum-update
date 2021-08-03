# Yum-update
Uses yum to auto-apply kernel patches and critical updates. Designed to be used as an Ansible playbook.

## Description:

Designed for performing updates on RHEL servers.
  * kpatch: Install or maintain kpatch up to date.
  * security: Install security updates except for kernel.
  
## Tags:

  * sendmail : send emails to report kpatch updates and if a security update needs a reboot.

## Outputs:

  * E-mail (optionnal, see Tags).
  
## Assumes:

  * The machine is able to use yum as a package-management utility.
  * User executing the playbook can become root.
  * If you wish to use the sendmail functionality, provide the "recipients" extra variable in your template, e.g.: "recipients: email@domain.com".
  Modify also :
    - the sender to use a valid one in roles/kpatch/tasks/main.yml - line 39 and roles/security/tasks/main.yml - line 34.
    - the smtp server to use a valid one in roles/kpatch/tasks/main.yml - line 33 and roles/security/tasks/main.yml - line 29.
