# Ansible Role: apache-modsecurity

Ansible Role to install and configure Apache mod_security2 in Ubuntu, Debian or Red Hat based distributions.

## Requirements

None.

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

Set the Apache config folder.

    apache_conf_dir: "/etc/apache2/conf-available"

Set the location of the log file.

    sec_audit_log: "/var/log/apache/apache_modsecurity_audit.log"

Configure which parts of the HTTP request and response will be logged.

    sec_audit_log_parts: "ABIFHZ" # # ABCDEFGHIJKZ

Set the HTTP "X-Powered-By" header value.

    sec_server_signature: "Apache 7000"

Set which rules to not log.

    sec_rule_remove_by_id: "960017,970901,960015"

## Dependencies

Must have installed Apache. Suggested role:

    geerlingguy.apache

For Red Hat and CentOS the EPEL repository is necessary:

    geerlingguy.epel

## Example Playbook

    - hosts: all
      roles:
        - leogallego.apache-modsecurity

## License

GPLv3

## Author Information

By Leonardo Gallego for Debian and Red Hat, based on work by Apollo Clark.
