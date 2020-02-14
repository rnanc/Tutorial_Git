# Tutorial Git
![git-icon](https://github.com/rnanc/Tutorial_Git/blob/master/icons8-git-48.png)
![github-icon](https://github.com/rnanc/Tutorial_Git/blob/master/icons8-github-50.png)

Tutorial de uso básico do git com sugestão de padrão de commit e fluxo de trabalho.

## Sumário
- [Conceitos](#conceitos)
- [Criando o primeiro repositório](#criando-o-repositório-e-fazendo-o-primeiro-push)
- [Padronizando commits](#padronizando-mensagens-de-commit)
- [Fluxo de trabalho](#fluxo-de-trabalho)
- [Resolvendo conflitos](#resolvendo-conflitos)
- [Vídeos](#vídeos)

## Via terminal
O uso do terminal para comandos do git é recomendado pois nos garante maior controle sobre as operações.

## Conceitos
Para iniciantes não familiarizados com os conceitos e nomenclaturas do `git`, é recomendável que leia antes as informações disponíveis [neste repositório](https://gist.github.com/victorsenam/8580499).

## Criando o repositório e fazendo o primeiro push

Acesse a pasta do seu projeto, independente se já contém arquivos ou não e execute o comando para iniciar o repositório na sua máquina(caso a pasta de seu projeto tenha sido clonada de um repositório preexistente, este comando se faz desnecessário):

```
$ git init
```

> Ao rodar o comando `$ git init`, será criado um arquivo na pasta do seu projeto chamado `.gitignore`, neste arquivo deverá ser incluído o nome de outros arquivos dentro do seu projeto que você deseja que sejam ignorados durante um `commit`, por exemplo a pasta  `node modules`. 

Caso você queira clonar um repositório preexistente utilize o comando:

```
$ git clone <link do seu repositório>
```

Após ter terminado todas as alterações necessárias, adione as mudanças que estão prontas para o commit com o comando:

```
$ git add .
```

> o comando `$ git add .` adicionará todos os arquivos que sofreram alterações, se você quiser adicionar arquivos específicos utilize o comando `$ git add <nome do arquivo>` .

Tendo todas as mudanças adicionadas e prontas para um commit, execute o commit com o comando:

```
$ git commit -m "<mensagem obrigatória>"
```

O commit cria um marco em sua linha do tempo, onde todas as alterações que foram adiconadas ao commit agora estão gravadas, caso você esteja em um repositório criado em  sua máquina, neste passo você deverá criar um repositório no [github](http://github.com/) e para fazer o link do seu repositório local com o remoto, executar o comando:

```
$ git remote add origin <link do seu repositório>
```

Finalmente chegou a hora de enviar seu código para o repositório remoto, com o comando:

```
$ git push origin master
```

**Agora seu código ja estará visível no github.**

## Padronizando mensagens de commit

A padronização das mensagens de commit organiza e facilita a revisão do código e orienta durante a resolução de possíveis conflitos quando se trabalha em time.

> O padrão sugerido usa como referência os descritos pelo [commitizen](https://github.com/commitizen/cz-cli).


* `feat:<mensagem>` - Usado para descrever a adição de uma nova funcionalidade no código.
* `fix:<mensagem>` - Usado para quando um bug é removido do código.
* `docs:<mensagem>` - Usado para mudanças somente na documentção do projeto.
* `refactor:<mensagem>` - Usado para quando a mudança se refere ao refatoramento.
* `perf:<mensagem>` - Usado para código de melhoria de performace.
* `chore:<mensagem>` - Usado para se referir a expansão de uma feature.

## Fluxo de trabalho

> Para um melhor e mais seguro fluxo de trabalho, os desenvolvedores sempre devem trabalhar em branches.

Após o clone do repositório, o desenvolvedor deverá criar uma branch usando os prefixos de commit para especificar em que está trabalhando:

```
$ git branch feat/<nome da feature>
```

Para entrar na branch que acabou de ser criada, insira o comando:

```
$ git checkout feat/<nome da feature>
```

O `push` do commit feito nesta branch é finalizado pelo comando:

```
$ git push origin feat/<nome da feature>
```

> Assim que a branch estiver pronta para o **merge**, o desenvolvedor deverá acessar o github e criar um **pull request**, assim o administrador do repositório poderá revisar o codigo e realizará o **merge** e **delete** da branch.

Caso seu repositório local esteja desatualizado em comparação ao repositório online, você pode atualizar o seu código local pelo comando:

```
$ git pull <nome da branch>
```

## Resolvendo conflitos
![conflito-icon](https://github.com/rnanc/Tutorial_Git/blob/master/icons8-conflito-48.png)

Conflitos no código podem aparecer durante o `merge` de uma branch ou mesmo se duas pessoas estão trabalhando na mesma branch, aqui irei sugerir formas de como esses conflitos podem ser tratados.

Se você está trabalhando com mais de uma pessoa na mesma branch ou por algum motivo tem uma versão desatualizada do projeto, o comando `push` acusará conflito e para tratar este erro é bem simples, rode no seu terminal o comando `$ git pull <nome da branch>`, isso atualizará seu projeto e se houver conflitos seu editor de texto acusará onde está e pedirá para que você os resolva antes de executar o `push` novamente.

Agora se o conflito foi detectado durante a criação de um `pull request` de uma branch com a branch `master`, existem duas ações que você poderá tomar:

* Durante a criação de uma `pull request` o conflito será detectado, porém isso não lhe impedirá de cria-la mesmo assim, você pode prosseguir com a criação e o conflito será encaminhado para o administrador do repositório resolver.

* Se no caso você mesmo gostaria de resolver o conflito ou você é o administrador do repositório e foi encaminhado uma branch com conflito, o comando a seguir   é:
  - Vá até a branch master pelo comando `$ git checkout master` dentro da master, o seu objetivo é buscar as alterações que estão conflitando com o seu código, então execute o comando `$ git pull`, após isso volte a sua branch de trabalho fazendo novamente um checkout `$ git checkout <branch com conflito>`, agora nós traremos o conteúdo da branch master para dentro da sua com o comando `$ git merge master`, o próprio terminal deve lhe dizer em qual arquivo o conflito foi detectado, agora basta abri-lo no editor de texto, tratar o conflito e fazer um `commit` na sua branch, assim o `pull request` deve ser automaticamente atualizada e não terá mais conflito.

## Vídeos

* [Tutorial Básico de Git](https://www.youtube.com/watch?v=2alg7MQ6_sI&t)
* [Biblioteca de Padronização de Commit](https://www.youtube.com/watch?v=erInHkjxkL8&t)
