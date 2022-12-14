# Docker ![](/images/icons8-docker-24.png)

Comandos do Docker 

## CLI Docker (https://docs.docker.com/engine/reference/run/)

### Imagens
* `docker`
    * [`<comando> --help`] - informações adicionados do comando docker.    
    * [`image`] - trabalha com as imagens
        * [`ls`] - lista as imagens
        * [`history <nome imagem>`] - apresenta o histórico dos comandos de execução da criação da imagem
        * [`inspect <nome imagem>`] - inspeciona a imagem, mostrando suas propriedades
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
        * [`--network <rede>`] - especifica qual rede aquele container vai usar
        * [`-P`] - expoe uma porta de forma aleatória
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
    * [`attach <nome da container>`] - entra no container para executar comandos. OBS: o container deve ter sido executado com -it

### Volumes    
* `docker`
    * [`<comando> --help`] - informações adicionados do comando docker.    
    * [`volume`] - trabalha com os volumes
        * [`ls`] - lista os volumes
        * [`create <nome>`] - cria um volume
        * [`inspect <nome>`] - apresenta as informações do volume

### Redes    
* `docker`
    * [`<comando> --help`] - informações adicionados do comando docker.    
    * [`networl`] - trabalha com network
        * [`ls`] - lista as redes
        * [`create <nome> -d bridge`] - cria uma rede, especificando o driver, que nesse caso é o Bridge                
        * [`inspect <nome>`] - apresenta as informações da rede
        * [`connect <rede> <container>`] - conecta um container em uma rede
        * [`disconnect <rede> <container>`] - desconecta um container em uma rede
        * [`prune`] - apaga as redes não utilizadas
        * [`rm <nome da rede>`] - remove uma rede
    
    OBS: se precisar fazer o container acessar alguma rede da máquina, é só utilizar o
    host.docker.internal, exemplo http://host.docker.internal:8000

### Compose 
* `docker-compose`
    * [`<comando> --help`] - informações adicionados do comando docker.    
    * [`config`] - valida a configuração daquele compose
    * [`up`] - sobe aquele compose iniciando as config e serviços
    * [`down`] - baixa aquele compose desativando os serviços

## Comandos úteis Linux

* `docker rm $(docker ps -aq) -f` - apaga todas os containers que estão em execução
* `docker ps -a | grep <termo pesquisa>` - irá aplciar um filtro no retorno do docker ps -a