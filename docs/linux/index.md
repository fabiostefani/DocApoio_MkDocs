# LINUX 🐧

Comandos do linux 

## Administração

* `shutdown [tempo]` - desliga a máquina no tempo informado (minutos). Informar zero, desliga a máquina agora..
* `ip` - Mostra a configuração de rede.
* `date` - Mostra a data do servidor.
* `sudo` - Executa a ação como administrador.
* `clear` - Limpa o console. Pode ser usado a tecla de atalho CTRL L
* `apt-get` - Executa a instaalação/atualização de aplicativos. Comando válido para ubuntu e variáveis dele.
    * `[install]` - instala aplicativos
    * `[update]` - atualiza aplicativos
    * `[upgrade]` - atualiza a lista de aplicativos disponíveis
* `history` - Mostra o histórico dos comandos utilizados.
    * `[<qtde comandos>]` - apresenta os ultimos XX comandos executados
    * `[! <numero comando>]` - executa novamente o comando
    * `[!!]` - executa o último comando novamente
    * `[! grep "<nome >"]` - busca os comandos que contém aquele nome em sua sintaxe
* `nano/vim` - para editar arquivos
* `systemctl status [service]` - para verificar a situação de algum serviço
* `xxx | grep [texto]` - para fazer buscar
* `lsblk` - para listar os discos da máquina
* `fdisk` - para criar partições no disco
* `mkfs` - para formatar a partição criada. Deve ser informado qual o tipo de arquivo que desejo criar e qual disco.
* `mount [disco] [dir]` - para montar um disco no linux e exibir seu conteúdo.

    ✔️ Para montar o disco automaticamente quando iniciar, deve ser adicionado a config no disco **/etc/fstab**.

    /disco  /dir_que_monta  /sistema_arq    defaults 0 0

* `umount [disco] [dir]` - para desmontar um disco. Não perde as informações, só não lista mais.
* `ps` - lista os processos que estão em execução para o usuário
    * `[a]` - lista para todos os usuários
    * `[u]` - mostra o nome do usuário e a data
    * `[x]` - mostra os processos fora do console também
* `kill` - para encerrar um processo
* `killall [nome processo]` - para encerrar por nome do processo.
* `w` - mostra quem está logado
* `who` - mostra quem está logado com o pid para ser desconectado
* `[command] --help` - mostra a ajuda para aquele comando.
* `man [command]` - mostra o manual de utilização para o comando.
* `help [command]` - apresenta o help do comando de forma formatada
* `echo` - mostra informações na tela. Exemplo, **echo fabio**, vai mostrar fabio escrito na tela.
    * `[$$]` - mostra o PID do processo atual

## Arquivos

* `ls` - Lista os arquivos de um diretório.
    * `[-l]` - apresenta os arquivos de forma detalhada.
    * `[-a]` - mostra os arquivos que estão ocultos. Arquivos ocultos no linux são os arquivos que começam com **.**
    * `[| more]` - apresenta os arquivos de forma paginada. Para cancelar a exibição, CTRL C.
    * `[<nome/parte do arquivo>]` - verifica se o arquivo existe.
    * `[<nome/parte do arquivo>*]` - verifica se o arquivo existe com aqueles caracteres e qualquer caracter aonde tiver o *******.
    * `[<nome/parte do arquivo>?]` - verifica se o arquivo existe com aqueles caracteres e substitui o **?** por qualquer letra. Exemplo, g?o*, 
    irá buscar arquivos que iniciam com **g**, tenham qualquer letra, depois o **o** e por final qualquer caracter.
    * `[[<caracter>]]]` - busca o arquivo com aquele caracterer e posso ter mais valores. Exemplo, **Aula[12345]**, vai listar Aula1, Aula2, Aula3, Aula4 e Aula5. Uma outra alternativa é Aula[1-5], aonde mostra a mesma sequencia de arquivos anterior.
    * `[{<string>}]` - diferente a busca com os **[]**, a chave é passado uma string para fazer a busca dos arquivos. Exemplo, **[aula, Aula, AULA]11**, vai retornar os arquivos aula11, Aula11 e AULA11

* `cd` - Navega entre os diretórios.
    * `[]` - vai para o diretório padrão do usuário logado
    * `[/]` - vai para o diretório raíz (root).
    * `[..]` - retorna um nível de diretório.
    * `[<nome diretório>]` - vai para o diretório informado.
    * `[~]` - vai para o diretório padrão do usuário logado    

    ✔️ Quando estiver montando o comando de acesso ao diretório, se der tab 2x, vai ser listado os dir/arquivos que tem naquele caminho.

* `pwd` - Mostra o diretório currente.
* `touch [nome arquivo]` - Cria um arquivo
* `find <diretorio> -name [nome arquivo]` - Localiza um arquivo a partir do diretório currente
    * `[ -user <nome user>]` - para especificar o usuário proprietário
* `locate <name>` - busca a partir de uma base de dados que o SO constroi quando é inicializado. É mais rapido que o find. Porém arquivos recem adicionados não serão localizados, pois precisa ser atualizado a base de dados. Para efetuar a atualização, deve ser chamado o atualizadb
* `whereis <nome>` - busca de comandos, código fonte, manuais, etc.
* `which <nome>` - busca somente nos diretórios das variáveis de ambiente.
* `mkdir [nome dir]` - Cria um diretório com o nome informado. 
    
    ✔️ Para criar diretórios com espaços no nome, deve ser utilizado ' no nome. Se não colocar entre aspas, cada pedaço do nome vai ser considerado um diretório a ser criado.

* `rmdir [nome dir]` - para remover um diretório.
* `rm` - para excluir arquivos.
    * `[ -r]` - apaga os arquivos de forma recorrente, vai entrando em cada diretório e apagando os arquivos.
    * `[ -rf]` - executa de forma recorrente a exclusão dos arquivos e apaga os diretórios juntos.
    * `[ -rv]` - vai mostrando em tela o que está sendo feito.
    * `[ -ri]` - solicita confirmação arquivo por arquivo.

    ✔️ Pode ser utilizado todas as variações de comandos juntos.

* `cat [nome arquivo]` - para visualizar o conteudo de um arquivo
* `cp` - para efetuar a copia de arquivos
* `mov` - move arquivos. Também utilizado para renomear arquivos.
* `tar` - para agrupar ou desagrupar os arquivos
    * `[ c ]` - para agrupar em um unico arquivo
    * `[ x ]` - para desagrupar em um unico arquivo
    * `[ t ]` - para listar os arquivos dentro um grupo
    * `[ f ]` - para informar o nome do arquivo
    * `[ v ]` - para mostrar o que está sendo feito passo a passo
    * `[ z ]` - para ja compactar quando estiver agrupando o arquivo
    Sintaxe: `tar cf backup.tar *png`

* `gzip` - para compactar um arquivo
    * `[ -k ]` - para manter o arquivo original sem alterações
    * `[ -d ]` - para descompactar um arquivo
* `gunzip` - para descompactar um arquivo .gz

![Estrutura de diretórios](/images/estruturaDiretorioLinux.png "Estrutura diretórios")

## Permissões

* `chmod` - para dar permissões a arquivos/diretórios. A estrutura padrão de apresentação das permissões é: **drwxrwxrwx**
    * **d**rwxrwxrwx - indica se é diretório **(d)**, file **(-)** ou link **(l)**.
    * d**rwx**rwxrwx os próximos indicam as permissões do dono do arquivo.
    * drwx**rwx**rwx esses indicam as permissões do grupo.
    * drwxrwx**rwx** indica as permissões dos demais usuários

    ✔️ As permissões deem ser calculadas de acordo com uma base numérica.

    * Leitura(r) - valor 4
    * Gravação(w) - valor 2
    * Execução(x) - valor 1
    * Nenhuma - valor 0
    * `[777]` - vai dar permissão total para os 3 níveis de acesso
    * `[750]` - vai dar permissão total para o dono, leitura e execução para o grupo e nenhuma permissão para os demais usuários
* `chowm` - para mudar o proprietário de um diretório/arquivo    


## Variáveis

* Para declarar uma varável no linux, deve ser utilizado a sintaxe <br>
`VARIAVEL=VALOR` <br>
E para efetuar a leitura dela, deve ser utilizado o **$** na frente <br>
`$VARIAVEL`
* Por padrão, as variáveis somente são visiveis dentro da sessão que ela foi criada. <br>
Se precisar que a variável fique visível para outras sessões filhas, deve ser efetuada uma exportação dela. <br>
`export VARIAVEL` <br>
* `set` - mostra todas as variáveis do ambiente
* `env` - mostra somente as variáveis exportadas

## Dicas

**$** no final do caminho do prompt indica que não está logado como super user

**#** no final do caminho do prompt indica que está logado como super user.    
