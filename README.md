# Ansible role `mailserver`

![](https://i.imgur.com/waxVImv.png)
### [View all Roadmaps](https://github.com/nholuongut/all-roadmaps) &nbsp;&middot;&nbsp; [Best Practices](https://github.com/nholuongut/all-roadmaps/blob/main/public/best-practices/) &nbsp;&middot;&nbsp; [Questions](https://www.linkedin.com/in/nholuong/)
<br/>

An Ansible role for installing a mail server on Enterprise Linux 7 (RHEL, CentOS). Specifically, the responsibilities of this role are to:

- Install and configure the Postfix service
- Install and configure the Dovecot service
- Integrate both services
- Configure user mailboxes
- Install and configure the SpamAssassin service
- Install and configure the ClamAV Service
- Integrate ldap in postfix

## Requirements

No specific requirements

## Role Variables


| Variable   | Default | Comments (type)  |
| :---       | :---    | :---             |
| `postfix_myhostname` | mail.bertvv.local      | The internet hostname of this mail systems |
| `postfix_mydomain` |  bertvv.local |  The internet domain name of this mail system. |
| `postfix_home_mailbox`  |  /mail |   Path name of the mailbox in the user's home directory|
| `postfix_ldap`  |  false |   To use or not to use ldap |
| `ldap_fqdn1`  |  / |   The FQDN of the ldap server, if `postfix_ldap` is true |
| `ldap_ou`  |  / |   The OU where the ldap users are created, if `postfix_ldap` is true |
| `ldap_dcname`  |  / |   The name of the ldap server, if `postfix_ldap` is true |
| `ldap_domainname`  |  / |   The domainname the network, if `postfix_ldap` is true |
| `ldap_root_domain`  |  / |   The root domain lever extension of the network, if `postfix_ldap` is true |

## Dependencies

No dependencies.

Ports to open:

```
rhbase_firewall_allow_services:
  - imap
  - imaps
  - pop3
  - pop3s
  - smtp
  - smtps
  - smtp-submission

```

To creat a user and to create his mailbox:

```
rhbase_users:
  - name: nholuong
    password: 'xxxx [...]'
    shell: /sbin/nologin
```

This created user can login to the mailserver but not into the linux machine.

## Testing

There are two types of test environments available. One powered by Vagrant, another by Docker. The latter is suitable for running automated tests on Travis-CI. Test code is kept in separate orphan branches. For details of how to set up these test environments on your own machine, see the README files in the respective branches:

- Vagrant: [vagrant-tests](https://github.com/bertvv/ansible-role-mailserver/tree/vagrant-tests)
- Docker: [docker-tests](https://github.com/bertvv/ansible-role-mailserver/tree/docker-tests)

## Contributing

Issues, feature requests, ideas are appreciated and can be posted in the Issues section.

Pull requests are also very welcome. The best way to submit a PR is by first creating a fork of this Github project, then creating a topic branch for the suggested change and pushing that branch to your own fork. Github can then easily create a PR based on that branch. Don't forget to add your name to the contributor list below!

# 🚀 I'm are always open to your feedback.  Please contact as bellow information:
### [Contact ]
* [Name: nho Luong]
* [Skype](luongutnho_skype)
* [Github](https://github.com/nholuongut/)
* [Linkedin](https://www.linkedin.com/in/nholuong/)
* [Email Address](luongutnho@hotmail.com)

![](https://i.imgur.com/waxVImv.png)
![](Donate.png)
[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/nholuong)

# License
* Nho Luong (c). All Rights Reserved.🌟