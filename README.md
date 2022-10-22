# DIO - k8s-projeto1-app-base

## Antes de executar o script.sh, troque o valor da variável registryDocker para seu usuário no Docker Hub e execute o comando `docker login` para logar o terminal no seu registry e permitir o push da imagem corretamente.

<br>

## 1. Teste realizado utilizando o [Kind](https://kind.sigs.k8s.io) com WSL2; 
## 2. Como foi realizado teste local, foi utilizado o serviceType:NodePort na porta 30006.
* Pode ser testado também via requisição cURL:
    * ~~~bash
        curl --location --request POST '172.19.0.2:30006' \
        --form 'nome="manney"' \
        --form 'email="manney@manney"' \
        --form 'comentario="DIO K8S"'
      ~~~~
      * Note que utilizei o ip do cluster local.

## 3. No frontend utilizar o ip do cluster local com a porta 30006 ou se estiver usando alguma Cloud Service, utilizar o ip do LoadBalancer.