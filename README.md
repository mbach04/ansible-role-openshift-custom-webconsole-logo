Ansible Role: Openshift Custom Webconsole Logo
=========

This role help change openshift webconsole logo.

Requirements
------------
None

Role Variables
--------------

| Name                      | Default value                         |        Requird       | Description                                                                 |
|---------------------------|---------------------------------------|----------------------|-----------------------------------------------------------------------------|
| openshift_master_conf_dir | /etc/origin/master                    |         yes          | Where openshift configuation dir is                                         |
| master_url                | http://master1.example.com:8443       |         yes          | API Server URL                                                              |
| stylesheet_base_dir       | /etc/origin/master/stylesheet         |         yes          | Where css/image file will place                                             |
| logo_image                | /tmp/sample-openshift-ori.png         |         yes          | Logo image path                                                             |
| temp_dir                  | /tmp                                  |         no           | Temp directory                                                              |
| force                     | false                                 |         no           | Overwrite all static/configuration files                                    |


Dependencies
------------

None



Example Playbook
----------------
~~~
- name: Example Playbook
  hosts: masters
  gather_facts: false

   roles:
      - { role: Jooho.openshift_custom_webconsole_logo, logo_img: "/tmp/sample-openshift-ori.png", master_url: "master1.example.com:8443", login_html_dir: "/etc/origin/master/stylesheet" }

~~~

Restart OpenShift Masters
----------
~~~
# Restart Openshift Master Server restart

# Single Master
ansible masters -m shell -a "systemctl restart atomic-openshift-master"

# Multiple Masters
ansible masters -m shell -a "systemctl restart atomic-openshift-master-api"
~~~

License
-------

BSD/MIT

Author Information
------------------

This role was created in 2017 by [Jooho Lee](http://github.com/jooho).

