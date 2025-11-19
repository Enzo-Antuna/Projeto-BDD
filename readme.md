# **Funcionalidade**: Cadastro de Usuário no Sistema S.O.S Escola

## 1. História de Usuário

> **Como** um usuário do sistema S.O.S Escola,
>
> **Eu quero** poder me cadastrar na plataforma
>
> **Para** que eu possa solicitar ajuda ou oferecer assistência a outros usuários.

---

## 2. Critérios de Aceite (Cenários Gherkin)

A seguir, estão os cenários de teste que descrevem o comportamento esperado da funcionalidade de cadastro.

### Cenário 1: Cadastro com Sucesso

```gherkin
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
```

### Cenário 2: Tentativa de Cadastro com E-mail Já Existente

```gherkin
Cenário: Tentativa de cadastro com e-mail já existente
  Dado que o e-mail "usuario.existente@teste.com" já está cadastrado
  E eu estou na página de cadastro
  Quando eu preencho o campo "nome" com "Maria Santos"
  E preencho o campo "email" com "usuario.existente@teste.com"
  E preencho o campo "senha" com "outrasenha456"
  E clico no botão "Cadastrar"
  Então eu devo continuar na página de cadastro
  E uma mensagem de erro "Este e-mail já está em uso." deve ser exibida
  ```

### Cenário 3: Tentativa de Cadastro com Campos Obrigatórios em Branco
```gherkin
Cenário: Tentativa de cadastro com campos obrigatórios em branco
  Dado que eu estou na página de cadastro
  Quando eu clico no botão "Cadastrar" sem preencher nenhum campo
  Então eu devo continuar na página de cadastro
  E mensagens de erro devem ser exibidas para os campos "nome", "email" e "senha"
```

### Testes: 

[Testes BDD](https://github.com/Enzo-Antuna/Projeto-BDD/blob/main/bdd.java)
