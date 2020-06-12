Logstash-OSS
=========

Installs and configures logstash-oss, the open source version of Logstash.

Requirements
------------

None.

Role Variables
--------------

```yml
logstash_oss_install_java_11: false
```

Set this to true to install Java 11.

```yml
logstash_oss_elasticsearch_repository: true
```
Set this to false, if you do not want the role to create a Yum or Apt repository.
Useful to set to false, if you have already have the repository configured.

```yml
logstash_oss_version: "7.x"
```
The logstash version to be installed.

```yml
logstash_beats_input: true
```
A common beats input configuration is included. Set this to false, if you do not
want the beats input to be configured.

```yml
logstash_beats_port: 5044
```
If beats input is configured, the port on which to listen to.

```yml
logstash_local_ssl_certificate_file_path: ""
```
Local path to the SSL/TLS certificate. This will be copied over to the target.

```yml
logstash_local_ssl_key_file_path: ""
```
Local path to the SSL/TLS key file. This will be copied over to the target.

```yml
logstash_ssl_private_directory: /etc/ssl/private
```
The private directory to store key file.

```yml
logstash_ssl_certificate_directory: /etc/ssl/certs
```
The directory to store SSL/TLS certificates.

logstash_main_configuration:
  path.data: /var/lib/logstash
  pipeline.ordered: auto
  path.logs: /var/log/logstash

logstash_elasticsearch_output: true
logstash_elasticsearch_hosts:
  - http://localhost:9200

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
