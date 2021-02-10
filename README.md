# Ansible(V2) Elasticsearch Callback Plugin
Ansible(v2) elasticsearch callback plugin.
It collects the result of ansible task runs and ships it to the elasticsearch.

##How to Use
You can add the plugin into your ansible project where all the playbooks are or in seperate directory of your choice. In any case you need to tell ansible where the callback plugin(s) are located. You can do this by adding following line into your ansible.cfg file.


```
callback_plugins = ~/.ansible/plugins/callback_plugins/:/usr/share/ansible_plugins/callback_plugins

```
then activate it by setting:

```
callback_whitelist = elasticsearch

```

You can customize the Settings by using the following environment variables:

```
ELASTICSEARCH_SERVER   (optional): defaults to localhost
ELASTICSEARCH_PORT     (optional): defaults to 9200
ELASTICSEARCH_TIMEOUT  (optional): defaults to 3 (seconds)
ELASTICSEARCH_INDEX    (optional): defaults to 3 ansible_logs
ELASTICSEARCH_DOC_ARGS (optional): Addtional json key-value pair(e.g. {"bar":"abc", "foo":"def"}) to be stored in each document

```

For more information about ansible configuration please refer to:

[http://docs.ansible.com/ansible/intro_configuration.html#bin-ansible-callbacks](http://docs.ansible.com/ansible/intro_configuration.html#bin-ansible-callbacks)


#License
MIT License.
