# graylog

[![Source Code](https://img.shields.io/badge/github-source%20code-blue?logo=github&logoColor=white)](https://github.com/rolehippie/graylog) [![Build Status](https://img.shields.io/drone/build/rolehippie/graylog/master?logo=drone)](https://cloud.drone.io/rolehippie/graylog) [![License: Apache-2.0](https://img.shields.io/github/license/rolehippie/graylog)](https://github.com/rolehippie/graylog/blob/master/LICENSE) 

Ansible role to install and configure a Graylog centralized logging server. 

## Sponsor 

[![Proact Deutschland GmbH](https://proact.eu/wp-content/uploads/2020/03/proact-logo.png)](https://proact.eu) 

Building and improving this Ansible role have been sponsored by my employer **Proact Deutschland GmbH**.

## Table of content

* [Default Variables](#default-variables)
  * [graylog_allow_highlighting](#graylog_allow_highlighting)
  * [graylog_allow_leading_wildcard_searches](#graylog_allow_leading_wildcard_searches)
  * [graylog_async_eventbus_processors](#graylog_async_eventbus_processors)
  * [graylog_command_wrapper](#graylog_command_wrapper)
  * [graylog_elasticsearch_hosts](#graylog_elasticsearch_hosts)
  * [graylog_group](#graylog_group)
  * [graylog_http_bind_address](#graylog_http_bind_address)
  * [graylog_http_enable_cors](#graylog_http_enable_cors)
  * [graylog_http_enable_gzip](#graylog_http_enable_gzip)
  * [graylog_http_max_header_size](#graylog_http_max_header_size)
  * [graylog_http_publish_uri](#graylog_http_publish_uri)
  * [graylog_http_thread_pool_size](#graylog_http_thread_pool_size)
  * [graylog_initial_heap_space](#graylog_initial_heap_space)
  * [graylog_inputbuffer_processors](#graylog_inputbuffer_processors)
  * [graylog_is_master](#graylog_is_master)
  * [graylog_logs_path](#graylog_logs_path)
  * [graylog_maximum_heap_space](#graylog_maximum_heap_space)
  * [graylog_message_journal_enabled](#graylog_message_journal_enabled)
  * [graylog_message_journal_flush_age](#graylog_message_journal_flush_age)
  * [graylog_message_journal_flush_interval](#graylog_message_journal_flush_interval)
  * [graylog_message_journal_max_age](#graylog_message_journal_max_age)
  * [graylog_message_journal_max_size](#graylog_message_journal_max_size)
  * [graylog_message_journal_segment_age](#graylog_message_journal_segment_age)
  * [graylog_message_journal_segment_size](#graylog_message_journal_segment_size)
  * [graylog_mongodb_uri](#graylog_mongodb_uri)
  * [graylog_mongodb_uris](#graylog_mongodb_uris)
  * [graylog_node_id](#graylog_node_id)
  * [graylog_outputbuffer_processors](#graylog_outputbuffer_processors)
  * [graylog_password_secret](#graylog_password_secret)
  * [graylog_processbuffer_processors](#graylog_processbuffer_processors)
  * [graylog_repository](#graylog_repository)
  * [graylog_root_email](#graylog_root_email)
  * [graylog_root_password](#graylog_root_password)
  * [graylog_root_timezone](#graylog_root_timezone)
  * [graylog_root_username](#graylog_root_username)
  * [graylog_server_args](#graylog_server_args)
  * [graylog_server_version](#graylog_server_version)
  * [graylog_storage_path](#graylog_storage_path)
  * [graylog_transport_email_auth_password](#graylog_transport_email_auth_password)
  * [graylog_transport_email_auth_username](#graylog_transport_email_auth_username)
  * [graylog_transport_email_enabled](#graylog_transport_email_enabled)
  * [graylog_transport_email_from_email](#graylog_transport_email_from_email)
  * [graylog_transport_email_hostname](#graylog_transport_email_hostname)
  * [graylog_transport_email_port](#graylog_transport_email_port)
  * [graylog_transport_email_subject_prefix](#graylog_transport_email_subject_prefix)
  * [graylog_transport_email_use_auth](#graylog_transport_email_use_auth)
  * [graylog_transport_email_use_ssl](#graylog_transport_email_use_ssl)
  * [graylog_transport_email_use_tls](#graylog_transport_email_use_tls)
  * [graylog_transport_email_web_interface_url](#graylog_transport_email_web_interface_url)
  * [graylog_trusted_proxies](#graylog_trusted_proxies)
  * [graylog_user](#graylog_user)
  * [http_external_uri](#http_external_uri)
* [Dependencies](#dependencies)
* [License](#license)
* [Author](#author)

---

## Default Variables

### graylog_allow_highlighting

Allow searches to be highlighted

#### Default value

```YAML
graylog_allow_highlighting: true
```

### graylog_allow_leading_wildcard_searches

Allow searches with leading wildcards

#### Default value

```YAML
graylog_allow_leading_wildcard_searches: true
```

### graylog_async_eventbus_processors

Number of threads used exclusively for dispatching internal events

#### Default value

```YAML
graylog_async_eventbus_processors: 2
```

### graylog_command_wrapper

Program that will be used to wrap the graylog-server command

#### Default value

```YAML
graylog_command_wrapper:
```

### graylog_elasticsearch_hosts

List of Elasticsearch hosts Graylog should connect to

#### Default value

```YAML
graylog_elasticsearch_hosts:
  - http://127.0.0.1:9200
```

### graylog_group

Name of the group owning Elasticsearch

#### Default value

```YAML
graylog_group: graylog
```

### graylog_http_bind_address

Network interface used by the Graylog HTTP interface

#### Default value

```YAML
graylog_http_bind_address: 0.0.0.0:9000
```

### graylog_http_enable_cors

Enable CORS headers for HTTP interface

#### Default value

```YAML
graylog_http_enable_cors: true
```

### graylog_http_enable_gzip

Enable GZIP support for HTTP interface

#### Default value

```YAML
graylog_http_enable_gzip: true
```

### graylog_http_max_header_size

Maximum size of the HTTP request headers in bytes

#### Default value

```YAML
graylog_http_max_header_size: 8192
```

### graylog_http_publish_uri

Public URI of Graylog which will be used by the Graylog web interface

#### Default value

```YAML
graylog_http_publish_uri: http://{{ ansible_default_ipv4.address }}:9000/
```

### graylog_http_thread_pool_size

Size of the thread pool used exclusively for serving the HTTP interface

#### Default value

```YAML
graylog_http_thread_pool_size: 16
```

### graylog_initial_heap_space

Represents the initial size of total heap space

#### Default value

```YAML
graylog_initial_heap_space: 1g
```

### graylog_inputbuffer_processors

Number of parallel running input buffer processors

#### Default value

```YAML
graylog_inputbuffer_processors: 2
```

### graylog_is_master

Define if this server acts as a Graylog master node

#### Default value

```YAML
graylog_is_master: true
```

### graylog_logs_path

Path to the logs directory

#### Default value

```YAML
graylog_logs_path: /var/log/graylog-server
```

### graylog_maximum_heap_space

Represents the maximum size of total heap space

#### Default value

```YAML
graylog_maximum_heap_space: 1g
```

### graylog_message_journal_enabled

Enable the disk based message journal

#### Default value

```YAML
graylog_message_journal_enabled: true
```

### graylog_message_journal_flush_age

General flush age for journal messages

#### Default value

```YAML
graylog_message_journal_flush_age: 1m
```

### graylog_message_journal_flush_interval

Journal flush interval

#### Default value

```YAML
graylog_message_journal_flush_interval: 1000000
```

### graylog_message_journal_max_age

Max age of journal messages before written to elasticsearch

#### Default value

```YAML
graylog_message_journal_max_age: 12h
```

### graylog_message_journal_max_size

Max size of journal messages before written to elasticsearch

#### Default value

```YAML
graylog_message_journal_max_size: 5gb
```

### graylog_message_journal_segment_age

Journal segment age

#### Default value

```YAML
graylog_message_journal_segment_age: 1h
```

### graylog_message_journal_segment_size

Journal segment size

#### Default value

```YAML
graylog_message_journal_segment_size: 100m
```

### graylog_mongodb_uri

#### Default value

```YAML
graylog_mongodb_uri: mongodb://localhost:27017/graylog
```

### graylog_mongodb_uris

MongoDB connection string

### graylog_node_id

Node ID for the Graylog server instance

#### Default value

```YAML
graylog_node_id: '{{ ansible_hostname | to_uuid }}'
```

### graylog_outputbuffer_processors

Number of parallel running output buffer processors

#### Default value

```YAML
graylog_outputbuffer_processors: 3
```

### graylog_password_secret

Secret used to encrypt values and sessions, generate it with "pwgen -N 1 -s 96"

#### Default value

```YAML
graylog_password_secret:
```

### graylog_processbuffer_processors

Number of parallel running process buffer processors

#### Default value

```YAML
graylog_processbuffer_processors: 5
```

### graylog_repository

Dict of repositories matching the choosen version

#### Default value

```YAML
graylog_repository:
  '3.3': deb https://packages.graylog2.org/repo/debian/ stable 3.3
```

### graylog_root_email

Email for the general admin user

#### Default value

```YAML
graylog_root_email:
```

### graylog_root_password

Password for the general admin user, got to be sha256 hash

#### Default value

```YAML
graylog_root_password: 8c6976e5b5410415bde908bd4dee15dfb167a9c873fc4bb8a81f6f2ab448a918
```

### graylog_root_timezone

Timezone for the general admin user

#### Default value

```YAML
graylog_root_timezone: UTC
```

### graylog_root_username

Username for the general admin user

#### Default value

```YAML
graylog_root_username: admin
```

### graylog_server_args

Pass some extra args to graylog-server command

#### Default value

```YAML
graylog_server_args:
```

### graylog_server_version

Version of Elasticsearch that gets installed

#### Default value

```YAML
graylog_server_version: '3.3'
```

### graylog_storage_path

Path to the storage directory

#### Default value

```YAML
graylog_storage_path: /var/lib/graylog-server
```

### graylog_transport_email_auth_password

Password for email transport

#### Default value

```YAML
graylog_transport_email_auth_password:
```

### graylog_transport_email_auth_username

Username for email transport

#### Default value

```YAML
graylog_transport_email_auth_username:
```

### graylog_transport_email_enabled

Enable email transport

#### Default value

```YAML
graylog_transport_email_enabled: false
```

### graylog_transport_email_from_email

Sender address used for email transport

#### Default value

```YAML
graylog_transport_email_from_email: graylog@example.com
```

### graylog_transport_email_hostname

Hostname for email transport

#### Default value

```YAML
graylog_transport_email_hostname: mail.example.com
```

### graylog_transport_email_port

Port for email transport

#### Default value

```YAML
graylog_transport_email_port: 587
```

### graylog_transport_email_subject_prefix

Subject prefix used for email transport

#### Default value

```YAML
graylog_transport_email_subject_prefix: '[graylog]'
```

### graylog_transport_email_use_auth

Use authentication for email transport

#### Default value

```YAML
graylog_transport_email_use_auth: true
```

### graylog_transport_email_use_ssl

Use SSL (SMTPS) for email transport

#### Default value

```YAML
graylog_transport_email_use_ssl: false
```

### graylog_transport_email_use_tls

Use STARTTLS for email transport

#### Default value

```YAML
graylog_transport_email_use_tls: true
```

### graylog_transport_email_web_interface_url

URL used within emails to access the streams

#### Default value

```YAML
graylog_transport_email_web_interface_url: '{{ http_external_uri }}'
```

### graylog_trusted_proxies

List of trusted proxy IPs or networks

#### Default value

```YAML
graylog_trusted_proxies: []
```

### graylog_user

Name of the user owning Elasticsearch

#### Default value

```YAML
graylog_user: graylog
```

### http_external_uri

#### Default value

```YAML
http_external_uri:
```

#### Example usage

```YAML
http_external_uri: https://graylog.example.com
```

## Dependencies

* [rolehippie.docker](https://github.com/rolehippie/docker)

## License

Apache-2.0

## Author

[Thomas Boerger](https://github.com/tboerger)
