# Criando um cluster no Google Cloud Kubernetes

- Kubernetes é um orquestrador de containers.

- A orquestração de containers veio para facilitar o uso de containers em ambiente produtivo, tornando tarefas como aumentar o número de instâncias, remover uma instância que está quebrada, realizar tarefas agendadas, distribuir carga de requisições, entre outras operações que ocorrem em ambiente produtivo de maneira mais fácil e rápida.


## Instruções para criar um projeto no Google Cloud Kubernetes Engine (GKE)

### Passo 1: Autorizando o Google Cloud SDK

- Primeiro temos que indicar para o gcloudsdk a conta da nuvem que iremos interagir pela linha de comando, para isso, execute no prompt de comando:

`gcloud init`

- Digite`y` para continuar, após isso aparecerá uma tela para que escolha o usuário desejado.
- Clique em allow para continuar
- Com as autorizações concedidas ao gcloudsdk, volte para o terminal, nele verá uma lista de projetos existentes vinculados a sua conta no GCP, escolha aquele que deseja utilizar para os próximos passos e pressione [Enter]. Agora o gcloudsdk está vinculado a sua conta

#### Criando o Cluster GKE

- Dentro do seu projeto, no console GCP: clique em Kubernetes engine;
- Cluster;
- Para criar cluster use o comando no shell: `gcloud container clusters create [cluster_name]`

- Por padrão, o comando de criação de cluster cria 3 nodes, cada um com 1 vCPU e 3.75 GB de memória, somando todos, no total o cluster padrão possui 3 vCPUs e 11.25 GB de memória para alocar recursos, é possível customizar isso conforme a necessidade, mas por enquanto não farei isso.


#### Instalando e configurando Kubectl

- Para interagirmos com o cluster, utilize o executável kubectl, para instalar ele:
`sudo apt-get install kuberct`

- Feito isso, execute o comando a seguir para obter as credenciais de acesso ao seu cluster, para começar a interagir com ele por linha de comando.
`gcloud container clusters get-credential[cluster_name]`

- Com as credenciais obtidas, agora é possível interagir com o cluster criado através do kubectl. A seguir listamos os nodes existentes no cluster criado utilizando o kubectl.
`kubectl get nodes`

### Passo 2: PODs e Services
