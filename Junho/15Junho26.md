# **Dia 15 de Junho 2026**
## Começo do projeto

# Linux (Ubuntu 26.04)
- **Comandos basicos:**
    - `man`: comando que mostra o *manual* de uso de todos os outros comandos (ex: `man ls` mostrará as funcionalidade do comando `ls`). Esse comando prende o terminal, para sair tecle Q. Se quiser ficar com o prompt livre, utilize `--help`, para ter um manual resumido do comando antecedente.
    - `su` : comando usado para trocar de usuário (ex: `su outroUsuario`, se `su` sem nada, vai direto para o usuário root, no qual caso precisará da senha e o $ mudará para #).
    - `apt` : em sistemas Debian/Ubuntu, sendo usuário root, permite o gerenciamento de pacotes.
        - `update`: parâmetro que apresenta os pacotes que podem ser atualizados.
        - `upgrade`: parâmetro que efetivamente atualiza os pacotes.
        - `install`: parâmetro que instala o pacote desejado.
        - `search`: parâmetro que busca versões dos pacotes.
        - `remove`: remove o pacote especificado.
    - `sudo`: comando que utiliza os privilégios do usuário root pontualmente (melhor do que trocar de usuário toda hóra).
    - `passwd`: permite de trocar a senha do usuário atúal, ou de outro usuário especificado depois do comando.
    - `useradd`: para criar um novo usuário (ex: `useradd nome -d /home/nome -p senha_nome`, na sequência o nome do novo usuário, o percurso da pasta nova e a senha).
    - `groupadd`: cria um novo grupo de usuários (precisa colocar `sudo groupadd nome_grupo` pois precisa de privilégios).
    - `usermod`: modifica os parâmetros de um usuário:
        - `-d`: estabelece um novo diretório para o usuário.
        - `-L`: bloqueia o usuário.
        - `-u`: desbloqueia.
        - `-e`: estabelece uma data de expiração, ápos a qual o usuário será bloqueado.
        - `-aG`: adiciona o usuário a novos grupos.

- **Pastas/diretórios:** todos os diretórios são construidos (*volumes montados*) sobre o "diretório-raiz" (`/`). Em Linux tudo é diretório, inclusive, os *devices* como mouse, teclado... o que facilita o processo de navigação.
    - `/bin`: é onde são armazenados os comandos da Shell.
    - `/dev`: diretórios dos *devices*.
    - `/home`: armazena as pastas do usuário.
    - `/usr`: onde os programs são instalados.

- **Comandos de navegação:** como o sistema é costruido sobre pastas, a navegação via Shell permite de encontrar praticamente tudo com alguns comandos.
    - `ls`: mostra as informações de pastas e arquivos dentro da pasta atual (pastas em *azul* e arquivos em *verde*).
        - `-l`: mostra uma lista longa e detalhada.
        - `-a`: mostra todas as pastas, mesmo as ocultas (os diretórios ocultos são precedidos por `.`).

        | Coluna | Descrição| 
        | :---: | :---:| 
        | 1 | **Tipo de arquivo e permissões** Sempre 10 caracteres: *d*: diretorio ou *-*: arquivo; permissões do dono do arquivo (*r*, *w*, *x*); permissões do grupo do dono do arquivo (*r*, *w*, *x*); permissões dos demais (*r*, *w*, *x*) |
        | 2 | **Quantidade de arquivos** Se arquivo, possui sempre 1, se diretório, tantos quantos arquivos que possui |
        | 3 | **Nome do dono do arquivo** se nome não disponível, exibe o *UID* (número identificador usuário) |
        | 4 | **Nome do grupo do dono do arquivo** se não disponível, exibe o *GID* (número identificador grupo) |
        | 5 | **Tamanho em bytes** `-h`: human readable |
        | 6 | **Data da última modificação** |
        | 7 | **Nome do arquivo ou pasta** |
    - `pwd`: exibe a pasta atual (`~` indica sempre o diretório-padrão / home do usuário).
    - `cd`: change directory, pode se mencionar caminho absoluto (ex: `/home/pasta1/pasta2`) ou relativo (ex: `user@ubuntu:/home$ cd pasta1`). `cd..` volta ao diretório pai, `cd` ou `cd ~` volta ao diretório-padrão do usuário.
    - `mkdir`: cria uma pasta; `mkdir -p`cria diretórios e subdiretórios (ex: `mkdir -p pasta/subpasta`).
    - `rm`: remove arquivos (melhor com caminho absoluto para limitar erros) ou pastas (só se a pasta estiver vazia).
        - `-r`: recursivo, se tentar apagar uma pasta não vazia, com esse parâmetro, o comando apagará primeiro o que estiver dentro da pasta, para em seguida eliminar a pasta (vai pedir Y/n antes de fazer) **ATENÇÃO OS DADOS REMOVIDOS ASSIM NÃO FICARÃO NA LIXEIRA, SERÃO PERDIDOS PARA SEMPRE**
    - `cp`: copia arquivos na pasta selecionada (ex: `cp /home/arquivo.txt /tmp`) nesse caso o nome ficará igual; se `cp /home/arquivo.txt /tmp/novoArquivo.txt` será copiado o arquivo na pasta de destino e trocado de nome.
        - `cp -Rvp`: copia pasta inteiras (`-R` de recursivo, para copiar o conteúdo inteiro; `-v` de verbose para mostrar o que foi copiado; `-p` preserva as permissões originais).
    - `mv`: move arquivos e pastas, solicitando origem e destino; pode renomear indicando no destino o novo nome.
    - `cat`: mostra o conteúdo de um arquivo diretamente no terminal.
        - `head`: similar ao comando `cat`, mas mostra só o cabeçalho do arquivo (`-n 5`: mostra só as primeiras 5 linhas).
        - `tail`: como `head`, mas para as linhas finais (usado em arquivos de *log*).
    - `grep`: busca de palavras-chaves em arquivos (ex: `grep palavra /home/pasta/arquivo.txt`); `-r` busca a palavra-chave em diretórios completosn graças à recursividade (pode precisar de `sudo` para vasculhar em todas as pastas).
