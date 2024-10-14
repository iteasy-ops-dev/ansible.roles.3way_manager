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


해야 할것.
타 서버에서 디비 작업 확인 및 다른 것이 있는지 확인.
타 서버 테스트
배포
프론트 개발


1. [Start] → 
2. [Input Variables] → 
   - 수집된 사용자, DB 정보 출력

3. [MySQL Connection Check] → 
   - "MySQL 로그인 시도"
   - [Decision: 성공/실패]
     - 실패 시: [Display Error: "MySQL 로그인 실패"] → [End]
     - 성공 시: [Proceed]

4. [User Account Creation] →
   - 사용자 계정 생성 및 비밀번호 설정
   - [Decision: 성공/실패]
     - 실패 시: [Display Error: "사용자 계정 생성 실패"] → [End]
     - 성공 시: [Proceed]

5. [Directory Setup] → 
   - 홈 디렉토리 생성, 권한 설정, 로그 디렉토리 생성, 인덱스 파일 추가

6. [Virtual Host & CBand Config] → 
   - 임시파일 생성 및 설정 추가
   - VHost 및 CBand 설정 파일 백업 및 추가

7. [Database Setup] → 
   - MySQL 쿼리로 DB 및 사용자 생성
   - [Decision: 성공/실패]
     - 실패 시: [Display Error: "DB 생성 실패"] → [End]
     - 성공 시: [Proceed]

8. [Apache Configuration Test] → 
   - Apache 설정 테스트 수행
   - [Decision: 성공/실패]
     - 실패 시: [Display Error: "Apache 설정 오류"] → [End]
     - 성공 시: [Apache Restart]

9. [Cleanup] → 
   - 임시 파일 삭제

10. [End] → 
   - "✅ 스크립트 완료"
