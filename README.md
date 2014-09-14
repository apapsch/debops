
## [![DebOps project](http://debops.org/images/debops-small.png)](http://debops.org) ferm



[![Travis CI](http://img.shields.io/travis/debops/ansible-ferm.svg?style=flat)](http://travis-ci.org/debops/ansible-ferm) [![test-suite](http://img.shields.io/badge/test--suite-ansible--ferm-blue.svg?style=flat)](https://github.com/debops/test-suite/tree/master/ansible-ferm/)  [![Ansible Galaxy](http://img.shields.io/badge/galaxy-debops.ferm-660198.svg?style=flat)](https://galaxy.ansible.com/list#/roles/1565) [![Platforms](http://img.shields.io/badge/platforms-debian%20|%20ubuntu-lightgrey.svg?style=flat)](#)






[ferm](http://ferm.foo-projects.org/) is a wrapper around `iptables`
command which lets you manage host firewall in an easy and Ansible-friendly
way. This role can be used to setup firewall rules directly from inventory,
or it can be used as a dependency by other roles to setup firewall rules
for other services.





### Installation

This role requires at least Ansible `v1.7.0`. To install it, run:

    ansible-galaxy install debops.ferm

#### Are you using this as a standalone role without DebOps?

You may need to include missing roles from the [DebOps common
playbook](https://github.com/debops/debops-playbooks/blob/master/playbooks/common.yml)
into your playbook.

[Try DebOps now](https://github.com/debops/debops) for a complete solution to run your Debian-based infrastructure.








### Role variables

List of default variables available in the inventory:

    ---
    
    # Enable or disable iptables management
    ferm: True
    
    # Comment added at the beginning of iptables, set to False to disable
    ferm_comment: 'Generated by ferm - /etc/ferm/ferm.conf'
    
    # Default iptables policy for INPUT, OUTPUT and FORWARD chains
    ferm_default_policy_input: 'DROP'
    ferm_default_policy_output: 'ACCEPT'
    ferm_default_policy_forward: 'DROP'
    
    # Mark packets on invalid ports as bad guys (block port scanning)
    ferm_mark_portscan: False
    
    # List of iptables INPUT rules to manage, many variables can be found in
    # template files, located in templates/etc/ferm/filter-input.d/ directory.
    # Additional variables are described below.
    ferm_input_list: []
    ferm_input_group_list: []
    ferm_input_host_list: []
    
      #- type: ''             # name of template file to use, required
                              #   format: <type>.conf.j2
      #  dport: []            # list of destination ports to manage, required
      #  weight: '10'         # helps with file sorting in rule directory, optional
      #  filename: ''         # custom filename instead of a generated one, optional
      #  delete: False/True   # delete specified rule file, optional









### Authors and license

`ferm` role was written by:

- Maciej Delmanowski | [e-mail](mailto:drybjed@gmail.com) | [Twitter](https://twitter.com/drybjed) | [GitHub](https://github.com/drybjed)

License: [GPLv3](https://tldrlegal.com/license/gnu-general-public-license-v3-%28gpl-3%29)



***

This role is part of the [DebOps](http://debops.org/) project. README generated by [ansigenome](https://github.com/nickjj/ansigenome/).
