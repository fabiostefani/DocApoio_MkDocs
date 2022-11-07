# Docker ![](/images/icons8-docker-24.png)

Comandos do Docker 

## CLI Docker 

* `docker`
    * [`ps`] - mostra os containers que estão em execução.
        * [`-a`] - mostra todo os containers.
        * [`-aq`] - mostra somente o ID do container.
    * [`<comando> --help`] - informações adicionados do comando docker.
    * [`run --name <nome do container> -p <porta servidor>:<porta container> <imagem docker>:<version>`] - Executa um container.
        * [`--name <nome do container>`] - Executa um container especificando o nome do container.
        * [`-p <porta servidor>:<porta container>`] - Executa um container fazendo o roteamento das portas do servidor para a porta do container.
        * [`<imagem docker>:<version>`] - Informa qual a imagem docker deve ser executada. Se não for informado qual o version, será considerada o latest        
        * [`-d`] - vai executar a imagem e desatachar o prompt, libera para continuar sendo utilizado
    * [`stop <id container>`] - interrompe um container em execução
    * [`start <id container>`] - inicia um container ja criado
    * [`exec --it nginx //bin/bash`] - disponibiliza a execução de comandos dentro do container
        * [`--it`] - 
        * [`<nome do container>`] - 
        * [`<bash dentro container>`] - 
    * [`pull <imagem:version>`] - baixa a imagem para o servidor
    * [`logs <id containier>`] - mostra os logs do container
    * [`rm <id containier>`] - remove um container
        * [`-f`] - força a remoção do container
    * [`inspect <id containier>`] - apresenta as informações do container
    * [`rmi <nome da imagem>`] - remove uma imagem
    * [`image`] - trabalha com as imagens
        * [`ls`] - lista as imagens

## Comandos úteis Linux

* `docker rm $(docker ps -aq) -f` - apaga todas os containers que estão em execução
* `docker ps -a | grep <termo pesquisa>` - irá aplciar um filtro no retorno do docker ps -a