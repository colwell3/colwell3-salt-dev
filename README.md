# Salt Local Development

### Configuring your host for Development

- As root, Create or copy the minion file from config_files /etc/salt/minion config file
``` yaml
pillarenv_from_saltenv: True

file_roots:
  test:
    - /srv/salt/salt

pillar_roots:
  test:
    - /srv/salt/pillar
```
- As root, Create salt directory with user permissions 
```
sudo mkdir /srv/salt
setfacl -m u:user:rwx /srv/salt
```
- As your netid, Clone this template 
```
cd /srv/salt
git clone https://github.com/colwell3/colwell3-salt-dev.git .
```

### Developing

- Create directory in /srv/salt/salt/my_state
- Create init.sls

### Running Tests
- salt-call
```
salt-call --local state.apply saltenv=test -l debug
```
