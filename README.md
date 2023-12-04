# HA Proxy & Keepalived

Este projeto innstala o HA Proxy e Keepalived para criar um Proxy de alta disponibilidade.\
Foi feito para ser utilizado em derivados do Linux Redhat.

## Requisitos 

É necessário configurar os IPs dos Hosts no arquivo hosts.cfg.\
Normalmente são 2 servidores e um deles será o MASTER.

- Haproxy 
- Keepalived 
- master 

É necessário configurar o Frontend e Backend do haproxy.\
Foi criado para um backend de Cluster Kubernetes.
Edite a roles\haproxy\tasks\main.yaml conforme necessidade.


## Detalhes do projeto

- Instala o haproxy em todos os hosts.
- Instala o keepalived em todos os hosts.
- Configura 1 host como master do Keepalived.
- Reinicia e ativa os serviços na inicialização.


## Faça o clone para sua estação
```
git clone https://github.com/julianorib/ansible-haproxy.git
```

## Execute o Playbook para instalação

```
ansible-playbook -i hosts.cfg -u user --private-key suachave playbook.yaml -b
```

