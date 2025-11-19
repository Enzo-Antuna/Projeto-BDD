A história de usuário que escolhi foi:

Como um usuário do sistema S.O.S,
Eu quero poder me cadastrar na plataforma
Para que eu possa solicitar ajuda ou oferecer assistência a outros usuários.
A seguir, apresento os cenários de uso em Gherkin, a implementação de um dos testes e o link para o repositório com o projeto BDD.

Cenários de Uso (Gherkin):

# language: pt

Funcionalidade: Cadastro de Usuário
  Como um novo usuário
  Eu quero me cadastrar no sistema S.O.S
  Para que eu possa acessar a plataforma

Cenário: Cadastro com sucesso
  Dado que eu estou na página de cadastro
  Quando eu preencho o campo "nome" com "João da Silva"
  E preencho o campo "email" com "joao.silva@teste.com"
  E preencho o campo "senha" com "senha123"
  E clico no botão "Cadastrar"
  Então eu devo ser redirecionado para a página de login
  E uma mensagem de "Cadastro realizado com sucesso!" deve ser exibida

Cenário: Tentativa de cadastro com e-mail já existente
  Dado que o e-mail "usuario.existente@teste.com" já está cadastrado
  E eu estou na página de cadastro
  Quando eu preencho o campo "nome" com "Maria Santos"
  E preencho o campo "email" com "usuario.existente@teste.com"
  E preencho o campo "senha" com "outrasenha456"
  E clico no botão "Cadastrar"
  Então eu devo continuar na página de cadastro
  E uma mensagem de erro "Este e-mail já está em uso." deve ser exibida

Cenário: Tentativa de cadastro com campos obrigatórios em branco
  Dado que eu estou na página de cadastro
  Quando eu clico no botão "Cadastrar" sem preencher nenhum campo
  Então eu devo continuar na página de cadastro
  E mensagens de erro devem ser exibidas para os campos "nome", "email" e "senha"
