# Ansible Role: PHP Extensions

[![MIT License](http://img.shields.io/badge/license-MIT-003399.svg)](http://opensource.org/licenses/MIT)

An Ansible role that manages common PHP extensions on Ubuntu 14.04

## Requirements

None

## Role Variables

Ansible variables are listed here along with their default values:

`php_ext_ppa_repo` is a list of Ubuntu PPA repositories that are managed for
this role. Each entry in the list may designate:

* **repo** *required* (ppa: is prepended)
* **state** (default is present)
* **update_cache** (default is yes)
* **validate_certs** (default is yes)

By default, the `ppa:ondrej/php5-5.6` repository is used:

    php_ext_ppa_repo:
    - repo: "ondrej/php5-5.6"

`php_ext_packages` is a list of Ubuntu packages that are managed for this role.
Each entry in the list may designate:

* **name** *required*
* **state** (default is present)

By default, the following PHP extensions are used:

    php_ext_packages:
    - name: "php5-common"
    - name: "php5-curl"
    - name: "php5-intl"
    - name: "php5-json"
    - name: "php5-mcrypt"
    - name: "php5-mysql"
    - name: "php5-readline"
    - name: "php5-sqlite"
    - name: "php5-xdebug"

## Dependencies

None

## Example Playbook

    ---
    - hosts: all
      roles:
      - novuso.php-ext

## License

This is released under the [MIT license](http://opensource.org/licenses/MIT).
