# Salt Local Development

### Configuring your host for Development

- Create or copy the minion file from config_files /etc/salt/minion config file
``` yaml
pillarenv_from_saltenv: True

file_roots:
  test:
    - /srv/salt/salt

pillar_roots:
  test:
    - /srv/salt/pillar
```
- Create salt directory with user permissions
```
sudo mkdir /srv/salt
setfacl setfacl -m u:netid:rwx /srv/salt
```
- Clone this template
```
cd /srv/salt
git clone git@github.com: .
```

### Developing

- Create directory in /srv/salt/salt/my_state
- Create init.sls

### Running Tests
- salt-call
```
salt-call --local state.apply saltenv=test -l debug
```