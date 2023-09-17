# Semaphore
### HELM CHART FOR USE TO KUBERNETES

## Sources

* https://docs.ansible-semaphore.com/
* https://github.com/ansible-semaphore/semaphore

### Before use HELM Chart you need to create namespace and secret

#### create namespace
```shell
kubectl create ns semaphore
```
#### create secret on namespace semaphore
```shell
kubectl -n semaphore create secret generic semaphore-secret \
  --SEMAPHORE_DB_USER: semaphore \
  --SEMAPHORE_DB_PASS: semaphore \
  --SEMAPHORE_DB_HOST: mysql \ # for postgres, change to: postgres
  --SEMAPHORE_DB_PORT: 3306 \ # change to 5432 for postgres
  --SEMAPHORE_DB_DIALECT: mysql \ # for postgres, change to: postgres
  --SEMAPHORE_DB: semaphore \
  --SEMAPHORE_PLAYBOOK_PATH: /tmp/semaphore/ \
  --SEMAPHORE_ADMIN_PASSWORD: changeme \
  --SEMAPHORE_ADMIN_NAME: admin \
  --SEMAPHORE_ADMIN_EMAIL: admin@localhost \
  --SEMAPHORE_ADMIN: admin \
  --SEMAPHORE_ACCESS_KEY_ENCRYPTION: gs72mPntFATGJs9qK0pQ0rKtfidlexiMjYCH9gWKhTU= \
  --SEMAPHORE_LDAP_ACTIVATED: 'no' \ # if you wish to use ldap, set to: 'yes' 
  --SEMAPHORE_LDAP_HOST: dc01.local.example.com \
  --SEMAPHORE_LDAP_PORT: '636' \
  --SEMAPHORE_LDAP_NEEDTLS: 'yes' \
  --SEMAPHORE_LDAP_DN_BIND: 'uid=bind_user,cn=users,cn=accounts,dc=local,dc=shiftsystems,dc=net' \
  --SEMAPHORE_LDAP_PASSWORD: 'ldap_bind_account_password' \
  --SEMAPHORE_LDAP_DN_SEARCH: 'dc=local,dc=example,dc=com' \
  --SEMAPHORE_LDAP_SEARCH_FILTER: "(\u0026(uid=%s)(memberOf=cn=ipausers,cn=groups,cn=accounts,dc=local,dc=example,dc=com))"
```