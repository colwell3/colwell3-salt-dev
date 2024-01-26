# Salt Local Development

### Configuring your host for Development

- Stop salt-minion.service
```
systemctl stop salt-minion.service
```
- move /etc/salt/minion.d 
```
mv /etc/salt/minion.d /etc/salt/minion.d_old
```
- Create or copy the minion file from config_files /etc/salt/minion config file
``` yaml
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