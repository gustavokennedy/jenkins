# Jenkins
Repositório para estudo do Jenkins utilizando aplicação teste ReactJS e NodeJS.

[Para erro de permissão no Docker](https://stackoverflow.com/questions/47854463/docker-got-permission-denied-while-trying-to-connect-to-the-docker-daemon-socke)
chmod 777 /var/run/docker.sock

## Nodes
Os Nodes no Jenkins precisam ser configurado no Linux ambiente de produção.

Para adicionar Host:

```shell
ssh -o HostKeyAlgorithms=ssh-rsa IP_SERVIDOR
nano /var/lib/jenkins/.ssh/known_hosts
```

<i>Adicionar no servidor de Pipeline e no Produção.</i>
