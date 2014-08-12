Backup SaltStack Formula
=============

Setup backup for all databases on the server using https://meskyanichi.github.io/backup/v4/

## What it does

  1. Basic
    1. Install basic packages
    2. Setup ssh
    3. Setup prompt
  2. Install Monit
  3. Install newrelic daemon
  4. Install and setup backup
  5. Install and setup lamp

## Install

1. Add remotes to /etc/salt/master

  ```yaml
  gitfs_remotes:
    - git://github.com/trexglobal/basic-formula
    - git://github.com/trexglobal/openssh-formula
    - git://github.com/trexglobal/monit-formula
    - git://github.com/trexglobal/newrelic-formula
    - git://github.com/trexglobal/backup-formula
    - git://github.com/trexglobal/lamp-formula
    - git://github.com/trexglobal/apache-formula
    - git://github.com/trexglobal/mysql-formula
    - git://github.com/trexglobal/php-formula
  ```

2. Setup [pillar](http://docs.saltstack.com/en/latest/topics/pillar/) from pillar.example
3. Add php-app to your server [state file](http://docs.saltstack.com/en/latest/topics/tutorials/starting_states.html)

  ```yaml
  include:
      - php-app
  ```

  or to the [top.sls](http://docs.saltstack.com/en/latest/ref/states/top.html) file

  ```yaml
  base:
    'some.server.example.com':
      - php-app
  ```
