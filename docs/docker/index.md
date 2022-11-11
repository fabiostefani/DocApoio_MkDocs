# Docker ![](/images/icons8-docker-24.png)

Comandos do Docker 

## CLI Docker (https://docs.docker.com/engine/reference/run/)

### Imagens
* `docker`
    * [`<comando> --help`] - informações adicionados do comando docker.    
    * [`image`] - trabalha com as imagens
        * [`ls`] - lista as imagens
    * [`build <caminho docker file> -t <nome imagem:`] - compila uma imagem. Precisa de um 
            * [`-t <nome imagem>`] - especifica o nome da imagem
    * [`push`] - envia a imagem para o docker hub
    * [`pull <imagem:version>`] - baixa a imagem para o servidor
    * [`rmi <nome da imagem>`] - remove uma imagem
    
### Containers
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
        * [`-it`] - interactive mode, deixa o console do container disponível para ser utilizado
        * [`--entrypoint <entrypoint>`] - especifica qual é o entrypoint da imagem que estou executando
        * [`-v <origem>:<destino container>`] - mapeia um volume para dentro do container
        * [`-e <enviroment>`] - para informar uma variável de ambiente que será utilizada pelo container. Pode ser passada várias vezes. Exemplo -e app=fabio 
        * [`--rm`] - vai remover o container após utilizar ele.
    * [`stop <id container>`] - interrompe um container em execução
    * [`start <id container>`] - inicia um container ja criado
    * [`exec --it nginx //bin/bash`] - disponibiliza a execução de comandos dentro do container
        * [`--it`] - 
        * [`<nome do container>`] - 
        * [`<bash dentro container>`] - 
    * [`logs <id containier>`] - mostra os logs do container
    * [`rm <id containier>`] - remove um container
        * [`-f`] - força a remoção do container
    * [`inspect <id containier>`] - apresenta as informações do container    
    * [`push`] - envia a imagem para o docker hub
    * [`top <idcontainer>`] - mostra os processos que estão em execução dentro do container
    * [`kill <idcontainer>`] - encerra a execução do container

### Volumes    


## Comandos úteis Linux

* `docker rm $(docker ps -aq) -f` - apaga todas os containers que estão em execução
* `docker ps -a | grep <termo pesquisa>` - irá aplciar um filtro no retorno do docker ps -a