# **Dia 11 de Julho 2026**

# Git e GitHub
- **Workflow de trabalho**: o fluxo de trabalho necessário ao trabalhar com versionamento de código, para poder publicar projetos ou exercicios na plataforma GitHub, poder adicionar file ou fazer commit dos mesmo, trabalhando através do terminal da maquina.
    - **Verificar e navegar**: primeiramente tem que verificar se está na pasta raiz onde deseja trabalhar, dentro do VSCode ou no editor de texto da sua escolha: para fazer isso use `pwd` para ver em que pasta está atualmente, `ls` para ver as pastas contidas dentro da pasta atual, `cd` para navegar entre as pastas.
    - **Inicializar o repositório**: `git init` cria uma nova pasta `.git` do zero, e permite que a pasta atual vire um repositório local vazio; `git status` mostra o diagnóstico: em que *branch* está, quais arquivos são *staged* ou seja, prontos para commit, quais arquivos são modificados mas não *staged*, e quais são *untracked* ou seja, novos, que o Git ainda não conhece.
    - **Adicionar conteúdos para a *staging area***: `git add .` adiciona todos os arquivos da pasta atual para a *staging area*, que é uma area intermediaria entre o nosso repositório local e o Git.
        - ***`.gitignore`***: se não queremos adicionar algum conteúdo para o Git, podemos criar um `.gitignore`, uma pasta que contém os elementos que o Git deve ignorar (sem rastreio, sem commit, por exemplo chaves privadas de API ou informções privadas). Para criar essa pasta: `touch .gitignore` no arquivo raiz: `touch` modifica a data de um arquivo existente, se não existe ele o cria vazio; `nano .gitignore` abre o editor de texto do terminal, no meu caso o `nano`, para incluir os datos a serem ignorados; `cat .gitignore` mostra o conteúdo do arquivo.
    - **Commit**: `git commit -m "nosso texto"` grava no histórico do Git o conteúdo adicionado junto com uma mensagem descritiva (expressada com `-m`); o commit é como um "snapshot" com hash unico, autor, data e ligado ao commit anterior.
    - **Conectar-se ao repositorio do GitHub**: após ter criado um repositório vazio no GitHub, usar `git remote add origin https...` para apontar o endereço URL daquele repositório (`origin` é convenção padrão); `git remote -v` mostra os remotos configurados; `git branch -M main` renomeia o branch atual como `main` (`-M` força a renomeação).
    - **Push**: `git push -u origin main` envia os commits feitos da branch `main` para o remoto `origin` (`-u` cria um vincúlo permanente entre o local `main` e o remoto `origin/main`, chamado de upstream, para que possamos fazer push usando simplesmente `git push`, nas proximas vezes).
    - **Organizar em arquivos o repositório do GitHub via terminal**: primeiro naveguee com `cd` até a pasta de trabalho, pois fazer um `git pull origin main` para trazer o remoto no local e deixá-lo atualizado; vamos começar a criação dos novos arquivos e mover os dados neles:

    ```bash
    mkdir NovaPasta
    git mv file1 file2 file3 NovaPasta/
    ```
    `git mv` facilita o processo, permitindo de passar diretamente ao commit sem usar `git add`, pois Git já reconhece isso; feito isso, `git commit -m "texto"` pois `git push`.