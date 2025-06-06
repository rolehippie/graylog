# graylog

[![Source Code](https://img.shields.io/badge/github-source%20code-blue?logo=github&logoColor=white)](https://github.com/rolehippie/graylog)
[![General Workflow](https://github.com/rolehippie/graylog/actions/workflows/general.yml/badge.svg)](https://github.com/rolehippie/graylog/actions/workflows/general.yml)
[![Readme Workflow](https://github.com/rolehippie/graylog/actions/workflows/docs.yml/badge.svg)](https://github.com/rolehippie/graylog/actions/workflows/docs.yml)
[![Galaxy Workflow](https://github.com/rolehippie/graylog/actions/workflows/galaxy.yml/badge.svg)](https://github.com/rolehippie/graylog/actions/workflows/galaxy.yml)
[![License: Apache-2.0](https://img.shields.io/github/license/rolehippie/graylog)](https://github.com/rolehippie/graylog/blob/master/LICENSE)
[![Ansible Role](https://img.shields.io/badge/role-rolehippie.graylog-blue)](https://galaxy.ansible.com/rolehippie/graylog)

Ansible role to install and configure a Graylog centralized logging server.

## Sponsor

Building and improving this Ansible role have been sponsored by my current and previous employers like **[Cloudpunks GmbH](https://cloudpunks.de)** and **[Proact Deutschland GmbH](https://www.proact.eu)**.

## Table of content

- [Requirements](#requirements)
- [Default Variables](#default-variables)
  - [graylog_allow_highlighting](#graylog_allow_highlighting)
  - [graylog_allow_leading_wildcard_searches](#graylog_allow_leading_wildcard_searches)
  - [graylog_async_eventbus_processors](#graylog_async_eventbus_processors)
  - [graylog_command_wrapper](#graylog_command_wrapper)
  - [graylog_default_plugins](#graylog_default_plugins)
  - [graylog_elasticsearch_hosts](#graylog_elasticsearch_hosts)
  - [graylog_enable_enterprise](#graylog_enable_enterprise)
  - [graylog_enterprise_legacy](#graylog_enterprise_legacy)
  - [graylog_enterprise_packages](#graylog_enterprise_packages)
  - [graylog_extra_config](#graylog_extra_config)
  - [graylog_extra_plugins](#graylog_extra_plugins)
  - [graylog_group](#graylog_group)
  - [graylog_http_bind_address](#graylog_http_bind_address)
  - [graylog_http_enable_cors](#graylog_http_enable_cors)
  - [graylog_http_enable_gzip](#graylog_http_enable_gzip)
  - [graylog_http_max_header_size](#graylog_http_max_header_size)
  - [graylog_http_publish_uri](#graylog_http_publish_uri)
  - [graylog_http_thread_pool_size](#graylog_http_thread_pool_size)
  - [graylog_initial_heap_space](#graylog_initial_heap_space)
  - [graylog_inputbuffer_processors](#graylog_inputbuffer_processors)
  - [graylog_inputbuffer_ring_size](#graylog_inputbuffer_ring_size)
  - [graylog_inputbuffer_wait_strategy](#graylog_inputbuffer_wait_strategy)
  - [graylog_is_master](#graylog_is_master)
  - [graylog_logs_path](#graylog_logs_path)
  - [graylog_maximum_heap_space](#graylog_maximum_heap_space)
  - [graylog_message_journal_enabled](#graylog_message_journal_enabled)
  - [graylog_message_journal_flush_age](#graylog_message_journal_flush_age)
  - [graylog_message_journal_flush_interval](#graylog_message_journal_flush_interval)
  - [graylog_message_journal_max_age](#graylog_message_journal_max_age)
  - [graylog_message_journal_max_size](#graylog_message_journal_max_size)
  - [graylog_message_journal_segment_age](#graylog_message_journal_segment_age)
  - [graylog_message_journal_segment_size](#graylog_message_journal_segment_size)
  - [graylog_minor_version](#graylog_minor_version)
  - [graylog_mongodb_uri](#graylog_mongodb_uri)
  - [graylog_mongodb_uris](#graylog_mongodb_uris)
  - [graylog_node_id](#graylog_node_id)
  - [graylog_oauth2_allowed_groups](#graylog_oauth2_allowed_groups)
  - [graylog_oauth2_client_id](#graylog_oauth2_client_id)
  - [graylog_oauth2_client_secret](#graylog_oauth2_client_secret)
  - [graylog_oauth2_cookie_secret](#graylog_oauth2_cookie_secret)
  - [graylog_oauth2_download](#graylog_oauth2_download)
  - [graylog_oauth2_enabled](#graylog_oauth2_enabled)
  - [graylog_oauth2_keycloak_url](#graylog_oauth2_keycloak_url)
  - [graylog_oauth2_listen_address](#graylog_oauth2_listen_address)
  - [graylog_oauth2_provider](#graylog_oauth2_provider)
  - [graylog_oauth2_static_groups](#graylog_oauth2_static_groups)
  - [graylog_oauth2_static_users](#graylog_oauth2_static_users)
  - [graylog_oauth2_upstream](#graylog_oauth2_upstream)
  - [graylog_oauth2_version](#graylog_oauth2_version)
  - [graylog_openjdk_version](#graylog_openjdk_version)
  - [graylog_output_batch_size](#graylog_output_batch_size)
  - [graylog_output_fault_count_threshold](#graylog_output_fault_count_threshold)
  - [graylog_output_fault_penalty_seconds](#graylog_output_fault_penalty_seconds)
  - [graylog_output_flush_interval](#graylog_output_flush_interval)
  - [graylog_outputbuffer_processors](#graylog_outputbuffer_processors)
  - [graylog_password_secret](#graylog_password_secret)
  - [graylog_processbuffer_processors](#graylog_processbuffer_processors)
  - [graylog_processor_wait_strategy](#graylog_processor_wait_strategy)
  - [graylog_ring_size](#graylog_ring_size)
  - [graylog_root_email](#graylog_root_email)
  - [graylog_root_password](#graylog_root_password)
  - [graylog_root_timezone](#graylog_root_timezone)
  - [graylog_root_username](#graylog_root_username)
  - [graylog_server_args](#graylog_server_args)
  - [graylog_server_version](#graylog_server_version)
  - [graylog_standard_legacy](#graylog_standard_legacy)
  - [graylog_standard_packages](#graylog_standard_packages)
  - [graylog_storage_path](#graylog_storage_path)
  - [graylog_transport_email_auth_password](#graylog_transport_email_auth_password)
  - [graylog_transport_email_auth_username](#graylog_transport_email_auth_username)
  - [graylog_transport_email_enabled](#graylog_transport_email_enabled)
  - [graylog_transport_email_from_email](#graylog_transport_email_from_email)
  - [graylog_transport_email_hostname](#graylog_transport_email_hostname)
  - [graylog_transport_email_port](#graylog_transport_email_port)
  - [graylog_transport_email_subject_prefix](#graylog_transport_email_subject_prefix)
  - [graylog_transport_email_use_auth](#graylog_transport_email_use_auth)
  - [graylog_transport_email_use_ssl](#graylog_transport_email_use_ssl)
  - [graylog_transport_email_use_tls](#graylog_transport_email_use_tls)
  - [graylog_transport_email_web_interface_url](#graylog_transport_email_web_interface_url)
  - [graylog_trusted_proxies](#graylog_trusted_proxies)
  - [graylog_user](#graylog_user)
  - [http_external_uri](#http_external_uri)
- [Discovered Tags](#discovered-tags)
- [Dependencies](#dependencies)
- [License](#license)
- [Author](#author)

---

## Requirements

- Minimum Ansible version: `2.10`

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

### graylog_default_plugins

List of default plugins to install

#### Default value

```YAML
graylog_default_plugins:
  - name: metrics-reporter-prometheus
    url: 
      https://github.com/graylog-labs/graylog-plugin-metrics-reporter/releases/download/3.0.0/metrics-reporter-prometheus-3.0.0.deb
    type: deb
    state: present
```

#### Example usage

```YAML
graylog_default_plugins:
  - name: graylog-plugin1
    url: https://example.com/graylog-plugin1.jar
    type: jar
  - name: graylog-plugin2
    url: https://example.com/graylog-plugin2.jar
    type: jar
    state: absent
  - name: graylog-plugin3
    url: https://example.com/graylog-plugin3-1.0.0.deb
    type: deb
    state: present
  - name: graylog-plugin4
    url: https://example.com/graylog-plugin4-1.3.3.deb
    type: deb
    state: absent
```

### graylog_elasticsearch_hosts

List of Elasticsearch hosts Graylog should connect to

#### Default value

```YAML
graylog_elasticsearch_hosts:
  - http://127.0.0.1:9200
```

### graylog_enable_enterprise

Enable the installation of enterprise plugins

#### Default value

```YAML
graylog_enable_enterprise: false
```

### graylog_enterprise_legacy

Package list for enterprise Graylog server prior v5

#### Default value

```YAML
graylog_enterprise_legacy:
  - graylog-enterprise-integrations-plugins={{ graylog_server_version }}*
  - graylog-enterprise-plugins={{ graylog_server_version }}*
```

### graylog_enterprise_packages

Package list for enterprise Graylog server

#### Default value

```YAML
graylog_enterprise_packages:
  - graylog-enterprise={{ graylog_server_version }}*
```

### graylog_extra_config

Free text for of additional config appended to server config

#### Default value

```YAML
graylog_extra_config:
```

### graylog_extra_plugins

List of extra plugins to install

#### Default value

```YAML
graylog_extra_plugins: []
```

#### Example usage

```YAML
graylog_extra_plugins:
  - name: graylog-plugin1
    url: https://example.com/graylog-plugin1.jar
    type: jar
  - name: graylog-plugin2
    url: https://example.com/graylog-plugin2.jar
    type: jar
    state: absent
  - name: graylog-plugin3
    url: https://example.com/graylog-plugin3-1.0.0.deb
    type: deb
    state: present
  - name: graylog-plugin4
    url: https://example.com/graylog-plugin4-1.3.3.deb
    type: deb
    state: absent
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

### graylog_inputbuffer_ring_size

Input buffer ring size

#### Default value

```YAML
graylog_inputbuffer_ring_size: 65536
```

### graylog_inputbuffer_wait_strategy

Input buffer wait strategy

#### Default value

```YAML
graylog_inputbuffer_wait_strategy: blocking
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

### graylog_minor_version

Minor version used for repo selection

#### Default value

```YAML
graylog_minor_version: "{{ graylog_server_version.split('.')[0] }}.{{ graylog_server_version.split('.')[1]
  }}"
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

### graylog_oauth2_allowed_groups

List of groups to allow access

#### Default value

```YAML
graylog_oauth2_allowed_groups: []
```

#### Example usage

```YAML
graylog_oauth2_allowed_groups:
  - /Group1
  - /Group2
  - /Group3
```

### graylog_oauth2_client_id

Client ID for OAuth2 authentication

#### Default value

```YAML
graylog_oauth2_client_id:
```

### graylog_oauth2_client_secret

Client secret for OAuth2 authentication

#### Default value

```YAML
graylog_oauth2_client_secret:
```

### graylog_oauth2_cookie_secret

Cookie secret used by OAuth2 proxy

#### Default value

```YAML
graylog_oauth2_cookie_secret:
```

### graylog_oauth2_download

#### Default value

```YAML
graylog_oauth2_download: https://github.com/oauth2-proxy/oauth2-proxy/releases/download/v{{
  graylog_oauth2_version }}/oauth2-proxy-v{{ graylog_oauth2_version }}.linux-amd64.tar.gz
```

### graylog_oauth2_enabled

URL of the OAuth2 Proxy to download

#### Default value

```YAML
graylog_oauth2_enabled: false
```

### graylog_oauth2_keycloak_url

URL of the Keycloak realm

#### Default value

```YAML
graylog_oauth2_keycloak_url:
```

### graylog_oauth2_listen_address

Listem address for the OAuth2 proxy

#### Default value

```YAML
graylog_oauth2_listen_address: 0.0.0.0:9001
```

### graylog_oauth2_provider

Provider for OAuth2 authentication

#### Default value

```YAML
graylog_oauth2_provider: keycloak
```

### graylog_oauth2_static_groups

List of groups assigned to static users

#### Default value

```YAML
graylog_oauth2_static_groups: []
```

### graylog_oauth2_static_users

List of users to allow access

#### Default value

```YAML
graylog_oauth2_static_users: []
```

#### Example usage

```YAML
graylog_oauth2_static_users:
  - username: username1
    password: p455w0rd
  - username: username2
    password: p455w0rd
  - username: username3
    password: p455w0rd
```

### graylog_oauth2_upstream

Upstream target for the OAuth2 proxy

#### Default value

```YAML
graylog_oauth2_upstream: http://{{ graylog_http_bind_address }}
```

### graylog_oauth2_version

Version of the OAuth2 Proxy to download

#### Default value

```YAML
graylog_oauth2_version: 7.9.0
```

### graylog_openjdk_version

Version OpenJDK to install

#### Default value

```YAML
graylog_openjdk_version: 11
```

### graylog_output_batch_size

Batch size for the Elasticsearch output

#### Default value

```YAML
graylog_output_batch_size: 500
```

### graylog_output_fault_count_threshold

Output fault count threshold

#### Default value

```YAML
graylog_output_fault_count_threshold: 5
```

### graylog_output_fault_penalty_seconds

Output fault penalty seconds

#### Default value

```YAML
graylog_output_fault_penalty_seconds: 30
```

### graylog_output_flush_interval

Flush interval (in seconds) for the Elasticsearch output

#### Default value

```YAML
graylog_output_flush_interval: 1
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

### graylog_processor_wait_strategy

Wait strategy describing how buffer processors wait on a cursor sequence

#### Default value

```YAML
graylog_processor_wait_strategy: blocking
```

### graylog_ring_size

Size of internal ring buffers

#### Default value

```YAML
graylog_ring_size: 65536
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

Version of Graylog that gets installed

#### Default value

```YAML
graylog_server_version: 6.2.3
```

### graylog_standard_legacy

Package list for regular Graylog server prior v5

#### Default value

```YAML
graylog_standard_legacy:
  - graylog-server={{ graylog_server_version }}*
  - graylog-integrations-plugins={{ graylog_server_version }}*
```

### graylog_standard_packages

Package list for regular Graylog server

#### Default value

```YAML
graylog_standard_packages:
  - graylog-server={{ graylog_server_version }}*
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

## Discovered Tags

**_graylog_**

**_oauth2_**


## Dependencies

- [community.general](https://github.com/ansible-collections/community.general)

## License

Apache-2.0

## Author

[Thomas Boerger](https://github.com/tboerger)
