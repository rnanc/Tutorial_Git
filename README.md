# Tutorial Git

Tutorial de uso básico do git com sugestão de padrão de commit e fluxo de trabalho.

## Sumário
- [Criando o primeiro repositório](#criando-o-repositório-e-fazendo-o-primeiro-push)
- [Padronizando commits](#padronizando-mensagens-de-commit)
- [Fluxo de trabalho](#fluxo-de-trabalho)
- [Vídeos](#vídeos)

## Via terminal
O uso do terminal para comandos do git é recomendado pois nos garante maior controle sobre as operações.

## Criando o repositório e fazendo o primeiro push

Acesse a pasta do seu projeto, independente se já contém arquivos ou não e execute o comando para iniciar o repositório na sua máquina(caso a pasta de seu projeto tenha sido clonada de um repositório pré-existente, este comando se faz desnecessário):

```
$ git init
```
> Caso você queira clonar um repositório pré-existente utilize o comando:

```
$ git clone <link do seu repositório>
```

Após ter terminado todas as alterações necessárias, adione as mudanças que estão prontas para o commit com o comando:

```
$ git add .
```

Tendo todas as mudanças adicionadas e prontas para um commit, execute o commit com o comando:

```
$ git commit -m "<mensagem obrigatória>"
```

O commit cria um marco em sua linha do tempo, onde todas as alterações agora estão gravadas, caso você esteja em um repositório criado em  sua máquina, neste passo você deverá criar um repositório no [github](http://github.com/) e para fazer o link do seu repositório local com o remoto, executar o comando:

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


* feat:< mensagem >- Usado para descrever a adição de uma nova funcionalidade no código.
* fix:< mensagem > - Usado para quando um bug é removido do código.
* docs:< mensagem > - Usado para mudanças somente na documentção do projeto.
* refactor:< mensagem > - Usado para quando a mudança se refere ao refatoramento.
* perf:< mensagem > - Usado para código de melhoria de performace.
* chore:< mensagem > - Usado para se referir a expansão de uma feature.

## Fluxo de trabalho

> Para um melhor e mais seguro fluxo de trabalho, os desenvolvedores sempre devem trabalhar em branches.

Após o clone do repositório o desenvolvedor deverá criar uma branch usando os prefixos de commit para especificar em que está trabalhando:

```
$ git branch feat/<nome da feature>
```

O push do commit feito nesta branch é finalizado pelo comando:

```
$ git push origin feat/<nome da feature>
```

> Assim que a branch estiver pronta para o **merge**, o desenvolvedor deverá acessar o github e criar um **pull request**, assim o administrador do repositório poderá revisar o codigo e realizará o **merge** e **delete** da branch.

## Vídeos

* [Tutorial Básico de Git](https://www.youtube.com/watch?v=2alg7MQ6_sI&t=582s)
* [Biblioteca de Padronização de Commit](https://www.youtube.com/watch?v=erInHkjxkL8&t=1020s)
