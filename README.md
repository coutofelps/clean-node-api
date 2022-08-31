## Sobre o Projeto

Esta aplicação será utilizada como back-end de toda a comunicação feita com a Serasa, com o intuito de centralizar todos estes endpoints e mantê-los devidamente testados e organizados. O projeto seguirá todos os padrões de TDD e é obrigatório que todos os testes tenham 100% cobertura.

Por que criamos um projeto do zero?
* É mais fácil criar algo novo do que reaproveitarmos nossos códigos antigos,
* Tudo aqui está sendo feito de acordo com o planejamento de nossa área de negócios em conjunto com nosso head de desenvolvimento, e isso nos força a trabalhar de acordo com todas as regras pré-definidas pelo time,
* Conseguimos utilizar novas tecnologias e isso facilita nosso trabalho, seja no desenvolvimento de ambientes, esteiras, stacks, etc :smile:

## Tecnologias

Esta seção contém todos os principais frameworks/bibliotecas usados para inicializar o projeto.

* Docker, como ferramenta de construção e manutenção de nossos ambientes,
* Express, como framework de aplicativos web em Node.js,
* Node.js, como interpretador V8 do Google e que permite a execução de códigos JavaScript fora de um navegador web.

## Começando

Aqui está um exemplo prático de como devemos iniciar a instalação de pré-requisitos e a inicialização propriamente dita do projeto em um servidor de desenvolvimento local.

### Pré-Requisitos

#### Docker
A instalação é muito simples, basta acessar o site e baixar o executável de acordo com seu sistema operacional. Feito isso, basta seguir os passos do instalador.

### Configuração e Inicialização do Projeto

_A aplicação já possui todas as configurações de ambiente construídas e devidamente testadas. O que precisamos agora é conhecer um pouco mais sobre os comandos do Docker e saber utilizá-los para manipulá-la:_

#### Criando uma imagem a partir do `Dockerfile`:
   ```js
   docker build -t serasanodejsapi/docker .
   ```
   
   1. `docker build` cria uma imagem a partir do Dockerfile,
   2. `-t` é um comando que indica que o nome da tag de nossa imagem vem a seguir,
   3. `serasanodejsapi/docker` é o nome que escolhi para a imagem,
   4. `.` onde o Dockerfile está localizado (nesse caso é um . pois o comando será executado no mesmo diretório que o Dockerfile se encontra).
   
#### Para verificar se a imagem foi devidamente criada, execute:
   ```js
   docker images
   ```
   
   1. `docker images` lista todas as imagens criadas em nosso ambiente atual.
   
#### Execute o comando abaixo para criar o container:
   ```js
   docker run -p 3000:3000 -d serasanodejsapi/docker
   ```
   
   1. `docker run` cria um container,
   2. `-p 3000:3000` libera a porta do container para que cada requisição acesse a porta 3000 e para que o container possa ouvir também na porta 3000,
   3. `d` _detach_, ou seja, o terminal fica livre e o processo roda em background, porém exibe também o ID do container,
   4. `serasanodejsapi/docker` nome da imagem que estamos utilizando para criar o container.
   
#### Para exibir as informações sobre todos os containers criados, execute:
   ```js
   docker ps
   ```
   
   1. `docker ps` exibe algumas informações sobre todos os containers de nosso ambiente.

#### Para parar a execução do container, execute:
   ```js
   docker stop ID
   ```
   
   1. `docker stop ID` para a execução de um container com um ID específico.
   
#### Para inicializar a execução do container, execute:
   ```js
   docker start ID
   ```
   
   1. `docker start ID` inicializa a execução de um container com um ID específico.
   
#### Para verificar os logs de um container específico, execute:
   ```js
   docker logs ID
   ```
   
   1. `docker logs ID` exibe os logs de um container com um ID específico.

## Roadmap

- [x] Criar ambiente Docker
- [x] Adicionar framework Express
- [x] Implementar arquivo .gitignore
- [x] Criar branches de desenvolvimento e homologação
- [x] Implementar estrutura de diretórios
- [x] Adicionar dependência Nodemon
- [ ] Implementar camada domain
- [ ] Implementar camada presentation

[Node.js]: https://img.shields.io/badge/-yellow-yellow
