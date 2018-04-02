# ansible-role-elasticsearch [![Build Status](https://travis-ci.org/shengyou/ansible-role-elasticsearch.svg?branch=master)](https://travis-ci.org/shengyou/ansible-role-elasticsearch)
=========

安裝 elasticsearch。

適用於
* Ubuntu 14.04, 16.04
* CentOS 6, 7

Requirements
------------

* ansible >= 2.4
* python >= 2.6

Role Variables
--------------

以下為預設值，請自行覆蓋。

```
elasticsearch_version: 5.6.4

install_plugins:
  - "https://github.com/medcl/elasticsearch-analysis-ik/releases/download/v5.6.4/elasticsearch-analysis-ik-5.6.4.zip"

```

以下 Variables 非必填項目，想要設定客製的 elasticsearch 才需要設置。

使用方式請參考範例。

* custom_elasticsearch_conf


Dependencies
------------

none.

Example Playbook
----------------

```
- name: install_elasticsearch.yml
  hosts: your_host
  gather_facts: yes
  become: yes

  vars:
    - elasticsearch_version: 6.2.3
    - install_plugins:
        - ingest-attachment
    - custom_elasticsearch_conf: /path/to/your/custom_elasticsearchrc.yml

  roles:
    - ansible-role-elasticsearch
```

License
-------

MIT
