# Dockerfile para WSO2 API Manager #

Esta seção define as instruções passo a passo para criar uma imagem do Docker baseada no Linux (https://hub.docker.com/_/ubuntu/) para o WSO2 API Manager 3.0.0.

## Pré-requisitos

* [Docker] (https://www.docker.com/get-docker) v17.09.0 ou superior
* Cliente [Git] (https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)

## Como criar uma imagem e executar
1. Faça o checkout deste repositório em sua máquina local usando o seguinte comando do cliente Git.

```
git clone https://github.com/wso2/docker-apim.git
```

2. Crie a imagem do Docker.
Execute o comando docker build como mostrado abaixo.

```
docker build -t wso2am: 3.0.0 .
```

3. Executando a imagem do Docker.

```
docker run -it -p 9443: 9443 wso2am: 3.0.0
```

> Aqui, apenas a porta 9443 (transporte de servlet HTTPS) foi mapeada para uma porta do host do Docker. Você pode mapear outras portas de serviço de contêiner, que foram expostas às portas do host do Docker, conforme desejado.

4. Acessando o console de gerenciamento.
* Para acessar o console de gerenciamento, use o IP do host da docker e a porta 9443.
https://localhost:9443/carbon
> Aqui,  refere-se ao nome do host ou ao IP da máquina host, sobre a qual os contêineres são gerados.

## Como subir imagem docker para o Dockerhub, pull e push
## Conta Dockerhub
* Criar um conta de usuário e id docker no site: https://hub.docker.com
* Criar um repositório no hub docker.
* Clique em Repositório e em seguida Criar Repositório, informe a descrição e o tipo de visibilidade (public ou private) em seguida clique em Criar.
* Após a criação da conta, você deverá realizar o login no docker executando o seguinte comando:
docker login.
* Informe Login e senha, os mesmos dados de acesso utilizados via navegador.
## Subindo imagem para o Dockerhub
* Execute o comando docker build como mostrado abaixo para criar uma nova imagem.

```
docker build -t <dockerID>/<image>:<versão> .
```
> Antes de executar o comando verifique se esta no mesmo diretorio do arquivo *dockerfile* para criar a imagem.

## Docker Push
* Após criar a imagem conforme descrito acima, verifique se esta logado no docker
* Logado no docker você deverá utilizar o seguinte comando:

```
docker push <dockerID>/<image>:<versão>
```

## Docker Pull
* Pronto sua imagem já está disponível no dockerhub para verificar entre no site do dockerhub ou realize o seguinte comando:

```
docker pull <dockerID>/<image>:<versão>
```
