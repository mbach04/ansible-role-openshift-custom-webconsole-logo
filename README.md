Ansible Role: Openshift Custom Webconsole Logo
=========

This role provides custom branding to the OpenShift web console

Requirements
------------
None

Role Variables
--------------

| Name                      | Default value                         |        Requird       | Description                                                                 |
|---------------------------|---------------------------------------|----------------------|-----------------------------------------------------------------------------|
| openshift_master_conf_dir | /etc/origin/master                    |         no           | Where openshift configuation dir is                                         |
| stylesheet_base_dir       | /etc/origin/master/stylesheet         |         no           | Where css/image file will place                                             |
| logo_img                  | ' '                                   |         yes          | Logo image path                                                             |
| temp_dir                  | /tmp                                  |         no           | Temp directory                                                              |
| overwrite_force           | false                                 |         no           | Overwrite all static files                                                  |
| ha_environment            | false                                 |         yes          | Is this a multi-master environment                                          |

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
    - { role: ansible-role-openshift-custom-webconsole-logo, logo_img: "/tmp/logo.png", stylesheet_base_dir: "/etc/origin/master/stylesheet" }
~~~

License
-------

BSD/MIT

Author Information
------------------

This role was created in 2017 by [Jooho Lee](http://github.com/jooho).

