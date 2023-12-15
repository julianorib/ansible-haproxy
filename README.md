# HA Proxy & Keepalived para Kube-apiserver

Este projeto instala e configura o HA Proxy e Keepalived para utilização junto com um Cluster Kubernetes (kube-apiserver). 

Pode ser utilizado para outros fins também.\
Basta modificar as regras de frontend e backend na role haproxy/tasks/main.yaml.

## Requisitos 

É necessário configurar os IPs dos Hosts no arquivo hosts.cfg.\
Normalmente são 2 servidores e um deles será o MASTER.

- Haproxy 
- Keepalived 
- master 

É necessário configurar as VARS de ipvirtual do keepalived.\
ipvirtual:      roles/keepalived/vars/main.yaml

## Detalhes do projeto

- Instala o haproxy em todos os hosts.
- Instala o keepalived em todos os hosts.
- Configura 1 host como master do Keepalived.
- Reinicia e ativa os serviços na inicialização.

# Como utilizar:

## Faça o clone para sua estação
```
git clone https://github.com/julianorib/ansible-haproxy.git
```

## Execute o Playbook para instalação

```
ansible-playbook -i hosts.cfg -u user --private-key suachave playbook.yaml -b
```

