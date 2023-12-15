# HA Proxy & Keepalived para Kube-apiserver

Este projeto instala e configura o HA Proxy e Keepalived para utilização junto com um Cluster Kubernetes (kube-apiserver). 

Pode ser utilizado para outros fins também.\
Basta modificar as regras de frontend e backend na role haproxy/tasks/main.yaml.

## Requisitos 

É necessário definir os IPS no arquivo hosts.cfg.\
[master]        -> host que será o MASTER do Keepalived (é obrigatório especificar 1).
[haproxy]       -> hosts que serão instalados e configurados o HA.
[control]       -> hosts que serão os Control Plane do Cluster Kubernetes. (backend)

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

