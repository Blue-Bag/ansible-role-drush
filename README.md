# Ansible Role: Drush

Installs Drush, a command line shell and scripting interface for Drupal, on any Linux or UNIX system.

Forked from geerlingguy.drush

Main differences:
Install Drush modules
Configure Drush RC

## Requirements

None.

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

    drush_install_path: /usr/local/share/drush

The location of the entire drush installation (includes all the supporting files, as well as the `drush` executable file.

    drush_path: /usr/local/bin/drush

The path where drush will be installed and available to your system. Should be in your user's `$PATH` so you can run commands simply with `drush` instead of the full path.

    drush_version: master

The version of Drush to install (examples: `master` for the bleeding edge, `7.x`, `6.x`, `6.2.0`).

    drush_keep_updated: no

Whether to keep Drush up-to-date with the latest revision of the branch specified by `drush_version`.

## Dependencies

Breaks dependencies to geerlingguy php and composer.
Also has a soft dependency on git (but use whichever git role you favour)

  - ansible-role-php (Installs PHP).
  - ansible-role-composer (Installs Composer).
    # - { role: ansible-role-git }

## Example Playbook

    - hosts: servers
      roles:
        - { role: geerlingguy.drush }

After the playbook runs, the `drush` command will be accessible from normal system accounts.

## License

MIT / BSD

## Author Information

This role was created in 2014 by [Jeff Geerling](http://jeffgeerling.com/), author of [Ansible for DevOps](http://ansiblefordevops.com/).
