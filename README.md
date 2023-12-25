# Objetivo

Instalar, usando o charts Helm, duas aplicações: wordpress e mysql, no namespace virtualizacao.

## Passo a Passo para Implementação do Projeto

### Preparação do Ambiente

1. Instale e inicie o Minikube:
   ```bash
   minikube start
   ```
2. Verifique se o Minikube está rodando corretamente:
    ```bash
    minikube status
    ```
3. Crie o namespace virtualizacao:
   ```bash
   kubectl create ns virtualizacao
   ```

### Implantação do Serviço

1. Clone este repositório:
   ```bash
   git clone https://github.com/MG10exe/k8s-local-wordpress-mysql
   ```
2. Entre na pasta do projeto:
    ```bash
    cd k8s-local-wordpress-mysql/
    ```
3. Instale o chart do wordpress com mysql:
    ```bash
    helm install wordpress-mysql ./wordpress-mysql
    ```
4. Verifique se a aplicação foi implantada com sucesso:
    ```bash
    kubectl get all -n virtualizacao
    ```
5. Verifique o ip do minikube usando:
    ```bash
    minikube ip
    ```
6. Verifique o ip do pod do Mysql usando:
    ```bash
    kubectl describe pod `nome-do-pode^` -n virtualizacao
    ```   

### Testes

1. Acesse o endereço `íp-do-minikube`:30355 para entrar no painel de configurações inicial do Wordpress.

2. Conecte o Mysql com o WordPress.

### Prints

![shot-2023-12-25_17-38-16](https://github.com/MG10exe/k8s-local-wordpress-mysql/assets/61914401/c853ee05-f928-418b-926a-ff4491e8cc89)

![shot-2023-12-25_17-44-03](https://github.com/MG10exe/k8s-local-wordpress-mysql/assets/61914401/cf4c7c47-bf8e-43d5-b88a-fa1106849c48)

![shot-2023-12-25_17-51-42](https://github.com/MG10exe/k8s-local-wordpress-mysql/assets/61914401/b628bb03-493a-4247-a016-589bdf25adca)

![shot-2023-12-25_17-51-52](https://github.com/MG10exe/k8s-local-wordpress-mysql/assets/61914401/9c0613e1-1612-45a4-8484-9ef841a5f53d)
