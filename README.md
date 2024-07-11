# HA Proxy & Keepalived para Kube-apiserver

Este projeto instala e configura o HA Proxy e Keepalived para utilização junto com um Cluster Kubernetes (kube-apiserver). 

Pode ser utilizado para outros fins também.

## Requisitos 

Configurar Hosts e Variáveis:

| grupo hosts | descrição |
|-------------|-----------|
| [masterha] | host que será o MASTER do Keepalived (é obrigatório especificar 1). |
| [haproxy]  | hosts que serão instalados e configurados o HA. |

É necessário especificar a variável abaixo:
```
ipvirtual:
```

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
ansible-playbook -i hosts.cfg -u user --private-key suachave playbook.yaml --extra-vars "ipvirtual=10.x.y.z" -b -K
```

