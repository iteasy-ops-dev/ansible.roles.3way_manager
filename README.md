Ansible Role: 3way Manager
=========

- 3way를 전문으로 관리합니다.

Requirements
------------
None.

Role Variables
--------------
- `defaults/main.yml` 참조
```yaml
user_id: ""
user_pass: ""
cband_limit: ""
disk_quota: ""
vhost_domain: ""
listen_port: ""

mysql_root_user: ""
mysql_root_password: ""
db_user: ""
db_name: ""
db_password: ""

setup: true
```

Dependencies
------------
Unknown.

Example Playbook
----------------
- `test/` 참조
```yaml
- hosts: vms
  remote_user: root
  roles:
    - ansible.roles.3way_manager
```

License
------------
BSD




```
flask/
├── app.py
├── blueprints/
│   ├── init.py
│   ├── abuse_report.py
│   ├── alarm.py
│   ├── cloud_ips_report.py
│   ├── customer.py
│   ├── customer_report.py
│   ├── cve_report.py
│   ├── ips_report.py
│   ├── monitoring.py
│   ├── networkflow.py
│   ├── search.py
│   └── waf_report.py
├── templates/
│   ├── base.html
│   ├── abuse_report.html
│   ├── alarm_page.html
│   ├── cloud_ips_report.html
│   ├── customer_report.html
│   ├── customer_report_detail.html
│   ├── cve_detail.html
│   ├── cve_report.html
│   ├── index.html
│   ├── ips_report.html
│   ├── monitoring.html
│   ├── networkflow.html
│   ├── register_customer.html
│   ├── search.html
│   └── waf_report.html
├── static/
│   ├── charts
│   ├── fonts
│   ├── picture
│   └── report
│       ├── abuse_report/
│       └── waf/
│   └── script
├── utils/
│   ├── init.py
│   ├── abuse_report_mail.py
│   ├── elasticsearch_utils.py
│   ├── mail_body.html
│   ├── report_generator.py
│   ├── report_template.html
│   ├── report_template_cloud.html
│   ├── report_utils.py
│   └── search_utils.py
├── log/
├── googlesheet/
└── requirements.txt
```