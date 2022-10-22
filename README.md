# DIO - Desafio CICD 1
## - Arquivo [CI](.gitlab-ci.yml) se utilizado no Gitlab, realizará build e push de imagens docker no registry público Docker, e também fará deploy se utilizado a variável de ambiente $KUBECONFIG do Gitlab apontando para um cluster K8S.

<br>

## - Para uso da app sem o CI/CD do Gitlab:

### Antes de executar o script.sh, troque o valor da variável registryDocker para seu usuário no Docker Hub e execute o comando docker login para logar o terminal no seu registry e permitir o push da imagem corretamente.

### 1. Teste realizado utilizando o [Kind](https://kind.sigs.k8s.io) com WSL2; 
### 2. Como foi realizado teste local, foi utilizado o serviceType:NodePort na porta 30006.
* Pode ser testado também via requisição cURL:
    * ~~~bash
        curl --location --request POST '172.19.0.2:30006' \
        --form 'nome="manney"' \
        --form 'email="manney@manney"' \
        --form 'comentario="DIO K8S"'
      ~~~~
      * Note que utilizei o ip do cluster local.

### 3. No frontend utilizar o ip do cluster local com a porta 30006 ou se estiver usando alguma Cloud Service, utilizar o ip do LoadBalancer.
