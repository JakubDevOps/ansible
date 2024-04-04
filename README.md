1. Stworzylem plik inventory: 

[SERWERY]
`node1 ansible_host=135.181.194.175 ansible_user=root`

[SERWERY] - grupa w pliku inventory
`node1` - przyjazna nazwa dla Anbible
`ansible_host=135.181.194.175` - zdefiniowanie adresu IP dla Ansibla
`ansible_user=root` - uzywany user przez Ansible

Playbook wykonuje dwa zadania:
1. Ping host - pinguje serwery
2. Restart servers - restartuje serwery

Moduly ping i reboot sa domyslnie wbudowane w moja wersje Ansible. Moglem uzyc tez:
```
tasks:
    - name: Ping hosts
      ping:
    - name: Restart servers
      reboot:
```
`-l` - moge okreslic na ktorych serwerach bedzie wykonuwany playbook

`ansible-playbook -i inventory ping.yaml -l node3`
`ansible-playbook -i inventory ping.yaml -l node3,node2`