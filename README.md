# AtalhosLinux
Quia de alguns atalhos do linux terminal


### zip ####

#zipar um arquivo ou diretorio
zip -r   <nomeArquivo>.zip   <arquivo ou diretorio>

#descompactar
unzip -r   <nomeArquivo>.zip

#listar arquivos dentro do zip
unzip -r   <nomeArquivo>.zip

#mostar menos log da descompactacao
unzip -r   <nomeArquivo>.zip


### tar ###
-c create
-z zip
-x extract
-f file
-v verbose

### gz ###
 
#zipando arquivo com tar com direcionardor ">"
$ tar -cz <arquivo ou diretorio>   >   <nomeArquivo>.tar.gz 

#descompactar arquivo tar com direcionador "<"
$ tar -xz <  <nomeArquivo>.tar.gz

#zipando arquivo tar sem o direcionador
$ tar -czf <arquivoArquivo>.tar.gz  <arquivo ou diretorio>

#descompactar arquivo tar sem direcionador
$ tar -xzf <nomeArquivo>.tar.gz

#zipando arquivo tar sem o direcionador e mostrando a verboside (log dos arquivos)
$ tar -vczf <arquivoArquivo>.tar.gz  <arquivo ou diretorio>

#descompactar arquivo tar sem direcionador e mostrando a verboside (log dos arquivos)
$ tar -vxzf <nomeArquivo>.tar.gz

### bzip2 ###

Para compactar ou descompactacao utilizando o tar é necessario apenas trocar o -z (zip) por -j (bz2)
ex:

$ tar -cjf <nomeArquivo>.tar.bz2 <arquivo ou diretorio>


### Comandos de leitura de arquivos. ###

-n nummero de linhas

# retorna as 10 primeiras linhas do inicio do arquivo
$ head <nomeAquiro>

# retorna as 10 primeiras linhas do final do arquivo
$ tail <nomeAquiro>

# utilizando o -n para informar o numero de linhas desejados ex:
$ head -n <nomeAquiro>

# comando para ler todo arquivo utlizando as setas para direcionar para cima ou para baixo.
$ less <nomeAquiro>



### Comandos editor de texto vi. ###
$ i entrar no modo de insercao
$ a entrar no modo de insercao so proximo espaco
$ x remove o caracter sem entrar no modo de insercao.
$ <numeroDeCaracteres> x remove a quantide de caracteres informado.
$ dd remove linha por completo
$ esc -> sair da modo de insercao.
$ shift+G ou G (maiusculo) vai para ultima linha
$ <numeroLinha> gg ou G(maiusculo) vai para numero da linha informado.
$ $ vai para final de uma linha
$ 0 inicio da linha
$ / abre opção para pesquina dentro do texto e "n" navega para proxima ocorrencia, "N" volta para ocorrencia anterios.
$ yy copia uma linha.
$ <numeroDeLinhas> yy copias a quantidade de linhas informado.
$ p cola texto copiado.
$ <quantidadeDeRepeticao> p de acordo com numero informado repete as copias.


# lista os processos em execucao
$ ps -e 
$ ps -ef

# lista os processos em execucao e mostra o caminho do arquivo.
$ ps -ea 

# lista os processos em execucao em formato arvore.
$ pstree

# lista os processo em execucao por consumo.
$ top
$ top -u <nomeUsuario>     *mostrar apenas os processos de um determinado usuário
$ top -p <idProcesso>      *acompanhar as informações de um processo específico
  
# mata um processo
$ kill -TERM <idProcesso>  *e permitir que ele possa realizar algumas tarefas antes de ser encerrado
$ kill <idProcesso>        *por default quando nao passado opção é TERM
$ kill -9 <idProcesso>     *mata um processo em definitivo
$ kill -STOP <idProcesso>  *para um processo
$ kill -CONT <idProcesso>  *volta de um processo parado
$ kill <idProcesso>  <idProcesso>  <idProcesso>  <idProcesso>  <idProcesso>  * matando varios processos
$ killall <nomeProcesso>   *matando todos os processo pelo nome do comando.
$ killall -9 <nomeProcesso> *mata todos os processos pelo nome do comando em definitivo.


### redirecionando o conteudo para o programa grep "|" (indica se a saída deve ser redirecionado para um programa)
$ <comando> | grep <filtroDesejado>


### jobs, fg, bg ###

Quando você aberto um processo dentro do terminal, esse processo trava o terminal.

Ao apertar "CRTL+Z" isso faz que o processo, fique em STOP e libere o termintal.

$ jobs *lista os processo que estao sendo executados a partir do terminal.
$ bg <numeroIdenticaoDoJobs> *joga o processo em execucao em BackGround liberando o terminal.
$ fg <numeroIdenticaoDoJobs> *volta o processo prezo ao terminal.

$ CTRL+C mata o processo de vez.
$ jobs <nomeDaAplicao> & * já inicia um processo em BackGround.


### chmod ###
-r  leitura
-w  escrita
-x  execucao

u -user
g -group
o -outros

$ chmod +<tipo>   *aumentar a permissao para todos (usuario, grupo, outros)
$ chmod -<tipo>   *remove a permissao para todos (usuario, grupo, outros)
$ chmod u+<tipo>  *apenas para usuaro
$ chmod g+<tipo>  *apenas para grupo
$ chmod o+<tipo>  *apenas para outros



ex:
Permitindo a executacao em todo os usuarios.

-rwxr-xr-x   1 wesly  staff     45 14 Mai 16:00 dorme

|diretorio|usuario|grupo|outros| |nomeUsuario|nomeGrupo|  |data e hora  |nomeArquivo
|    -    |rw-    |rw-  |r--   |1|wesly      |wesly    |45|14 Mai 16:00 |dorme


$ chmod +x 
|diretorio|usuario|grupo|outros| |nomeUsuario|nomeGrupo|  |data e hora  |nomeArquivo
|    -    |rwx    |rwx  |r-x   |1|wesly      |wesly    |45|14 Mai 16:00 |dorme



### busca de arquivos ###
# buscar por arquivos e programas no sistema operacional
$ locate <nomeDoArquivo>

$ sudo updatedb *Faz atualizaçao da base de dados do linux na busca de arquivos.

# Para saber onde os programas estão instalados
$ which <nomeDoPrograma> 

# mudar a senha do usuario
$ passwd 
$ sudo passwd       *Muda a senha do usuaro root

#logar com outro usuario
$ su <nomeDoUsuario>
ex: su root       *logando com o usuario root.

#Criando um novo usuario
$ adduser <nomeDoUsuario>
