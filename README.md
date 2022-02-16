To deploy a 'datacenter' as described in task #3, run

```
ansible-playbook rz.yml
```

The solution's idepotency relies on Ansible 'cacheable' facts. If the intention is to create another
'datacenter', the locally cached facts for `localhost` must be deleted first.

The individual roles used in this playbook are described in the repective README files.

```
find . -name 'README*'
```
