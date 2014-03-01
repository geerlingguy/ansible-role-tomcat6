# Ansible Role: Tomcat 6

An Ansible Role that installs Tomcat 6 on RedHat Enterprise Linux or CentOS 6.x servers.

## Requirements

None.

## Role Variables

Available variables are listed below, along with default values (see `vars/main.yml`):

    tomcat6_hostname: localhost

The hostname for this server. `localhost` works fine for many Tomcat web applications which are not dependent on a particular hostname being set (e.g. Apache Solr).

    tomcat6_catalina_port: 8983

The port on which Catalina will listen for requests.

    tomcat6_catalina_redirect_port: 8443

This is the port to which requests will be redirected if they come in on a non-SSL port, but are required to be secure via a security constraint.

## Dependencies

  - geerlingguy.java (Installs Java for CentOS 6.x).

## Example Playbook

    - hosts: webservers
      vars_files:
        - vars/main.yml
      roles:
        - { role: geerlingguy.tomcat6 }

*Inside `vars/main.yml`*:

    tomcat6_hostname: example.com
    tomcat6_catalina_port: 8080

## License

MIT / BSD

## Author Information

This role was created in 2014 by Jeff Geerling (@geerlingguy), author of Ansible for DevOps. You can find out more about the book at http://ansiblefordevops.com/, and learn about the author at http://jeffgeerling.com/.
