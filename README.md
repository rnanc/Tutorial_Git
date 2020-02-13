# Tutorial Git

Tutorial de uso básico do git com sugestão de padrão de commit e fluxo de trabalho.

## Via terminal
O uso do terminal para comandos do git é recomendado pois nos garante maior controle sobre as operações.

## Criando o repositório e fazendo o primeiro push

**Acesse a pasta do seu projeto, independente se já contém arquivos ou não e execute o comando para iniciar o repositório na sua máquina(caso a pasta de seu projeto tenha sido clonada de um repositório pré-existente, este comando se faz desnecessário):**

```
git init
```
**Após ter terminado todas as alterações necessárias, adione as mudanças que estão prontas para o commit com o comando:**

```
git add .
```

**Tendo todas as mudanças adicionadas e prontas para um commit, execute o commit com o comando:**

```
git commit -m "<mensagem obrigatória>"
```

**O commit cria um marco em sua linha do tempo, onde todas as alterações agora estão gravadas, caso você esteja em um repositório criado em  sua máquina, neste passo você deverá criar um repositório no [github](http://github.com/) e para fazer o link do seu repositório local com o remoto, executar o comando:**

```
git remote add origin <link do seu repositório>
```
**Finalmente chegou a hora de enviar seu código para o repositório remoto, com o comando:**

```
git push origin master
```
**Agora seu código ja estará visível no github.**

## Padronizando mensagens de commit

A padronização das mensagens de commit organiza e facilita a revisão do código e orienta durante a resolução de possíveis conflitos quando se trabalha em time.

> O padrão sugerido usa como referência os descritos pelo [commitizen](https://github.com/commitizen/cz-cli).

```
feat:<mensagem> - Usado para descrever a adição de uma nova funcionalidade no código.
fix:<mensagem> - Usado para quando um bug é removido do código.
docs:<mensagem> - Usado para mudanças somente na documentção do projeto.
refactor:<mensagem> - Usado para quando a mudança se refere ao refatoramento.
perf:<mensagem> - Usado para código de melhoria de performace.
chore:<mensagem> - Usado para se referir a expansão de uma feature.
```

End with an example of getting some data out of the system or using it for a little demo

## Running the tests

Explain how to run the automated tests for this system

### Break down into end to end tests

Explain what these tests test and why

```
Give an example
```

### And coding style tests

Explain what these tests test and why

```
Give an example
```

## Deployment

Add additional notes about how to deploy this on a live system

## Built With

* [Dropwizard](http://www.dropwizard.io/1.0.2/docs/) - The web framework used
* [Maven](https://maven.apache.org/) - Dependency Management
* [ROME](https://rometools.github.io/rome/) - Used to generate RSS Feeds

## Contributing

Please read [CONTRIBUTING.md](https://gist.github.com/PurpleBooth/b24679402957c63ec426) for details on our code of conduct, and the process for submitting pull requests to us.

## Versioning

We use [SemVer](http://semver.org/) for versioning. For the versions available, see the [tags on this repository](https://github.com/your/project/tags). 

## Authors

* **Billie Thompson** - *Initial work* - [PurpleBooth](https://github.com/PurpleBooth)

See also the list of [contributors](https://github.com/your/project/contributors) who participated in this project.

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

## Acknowledgments

* Hat tip to anyone whose code was used
* Inspiration
* etc
