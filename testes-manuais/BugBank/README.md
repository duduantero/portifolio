# 🏦 Projeto 01 - Bug Bank

> "O banco com bugs e falhas do seu jeito."

![Status do Projeto](https://img.shields.io/badge/Status-Concluído-brightgreen)
![Tipo de Teste](https://img.shields.io/badge/Teste-Manual-blue)
![Plataforma](https://img.shields.io/badge/Web-React-orange)

## 🔖 Sobre o Projeto

Este diretório contém a documentação e os artefatos de testes manuais realizados na aplicação **Bug Bank**. 

O **Bug Bank** é uma aplicação simulada que possui falhas intencionais e cenários específicos para prática de testes de software. O objetivo deste projeto foi mapear os requisitos, criar casos de teste e reportar os bugs encontrados.

* **Aplicação Alvo:** [BugBank UI - Jhonatas Matos](https://github.com/jhonatasmatos/bugbank-ui)

## 📋 Requisitos do Sistema

Abaixo estão listadas as regras de negócio e requisitos funcionais utilizados como base para a criação dos cenários de teste.
🔗 **Fonte Oficial:** *Para acessar os requisitos originais na aplicação, [Clique Aqui](https://bugbank.netlify.app/requirements).*

> **Nota:** A aplicação não conta com um banco de dados real; todas as informações são armazenadas em memória local (Local Storage).

### 🔐 1. Login
* Email e Senha são campos obrigatórios.
* Tentativa de acesso sem preencher campos obrigatórios deve exibir a mensagem "Usuário e senha precisam ser preenchidos".
* Não deve autorizar o acesso para usuários inválidos ou não cadastrados.
* Usuários válidos e cadastros são direcionados para a home.


### 📝 2. Cadastro
* Os campos Nome, Email, Senha e Confirmação de senha são de preenchimento obrigatório 
* Tentativa de cadastro sem preencher nome deve visualizar a mensagem "Nome não pode ser vazio" 
* Tentativa de cadastro sem preencher e-mail deve visualizar a mensagem "Email não pode ser vazio"
* Tentativa de cadastro sem preencher senha deve visualizar a mensagem "Senha não pode ser vazio" 
* Tentativa de cadastro sem preencher confirmação de senha deve visualizar a mensagem "Confirmar senha não pode ser vazio" 
* Deixar ativo a opção "Criar conta com saldo" deve criar conta com saldo de R$ 1.000,00 
* Deixar inativo a opção "Criar conta com saldo" deve criar conta com saldo de R$ 0,00 - Senha e confirmação de senha precisam ser iguais 
* Cadastrar conta com sucesso deve exibir número da conta criada


### 💸 3. Transferência
* Só é permitido transferência para contas válidas
* Só é permitido transferência quando saldo é igual ou maior que valor para transferir 
* Tentativa de transferência para conta inválida deve exibir mensagem de erro "Conta inválida ou inexistente"
* Número e digito da conta aceitam apenas números 
* Campo descrição é um campo de preenchimento obrigatório 
* Valor de transferência não pode ser igual ou menor que zero 
* Ao realizar transferência com sucesso deve ser debitado o valor da conta e exibir a mensagem de "Transferência realizada com sucesso" 
* Ao realizar uma transferência com sucesso deve ser redirecionado para o extrato


### 📄 4. Extrato
* Deve exibir o saldo disponível no momento 
* Cada transação deve exibir data que foi realizada, tipo da transação (Abertura de conta / Transferência enviada / Transferência recebida)
* Quando valor for de saída da conta deve estar em vermelho e iniciar com o sinal de menos/negativo (-)
* Quando valor for de entrada na conta deve estar em verde 
* Transações sem comentário devem exibir (-)


### ⚠️ Funcionalidades em Desenvolvimento (Fora do Escopo)
As seguintes funcionalidades constam na interface mas não possuem regras de negócio implementadas neste ciclo:
* Saque
* Pagamento

## 📂 Documentação e Artefatos

Aqui estão os entregáveis gerados durante o ciclo de testes:

* **[`Plano-de-Testes.md`](./Plano-de-Testes.md)**
    * *Estratégia, escopo, cronograma e ferramentas definidas.*
    
* **[`Cenarios-e-Casos-de-Teste.md`](./Cenario-e-casos-de-teste.md)**
    * *Matriz de testes cobrindo os requisitos funcionais e regras de negócio.*

* **[`Relatorio-de-Bugs.pdf`](./Relatorio-de-Bugs.pdf)**
    * *Evidências visuais e detalhadas dos defeitos encontrados.*

* **[`Resultados-de-teste.md`](./Resultados-de-teste.md)**
    * *Relatório final com métricas de execução, cobertura e parecer de qualidade.*

## 🛠️ Ferramentas Utilizadas

* **Gestão de Testes:** Jira 
* **Documentação:** Google Sheets
* **Captura de Evidências:** Ferramenta de Captura (Snipping Tool) nativa do Windows 11
* **Navegadores:** Google Chrome

## 🚀 Como Executar a Aplicação Localmente

Para reproduzir os testes, utilizei o repositório oficial do projeto. Siga os passos abaixo (necessário ter Node.js instalado):

1.  Clone o repositório original:
    ```bash
    git clone https://github.com/jhonatasmatos/bugbank-ui.git
    ```
2.  Acesse a pasta e instale as dependências:
    ```bash
    cd bugbank-ui
    npm install
    ```
3.  Execute o projeto:
    ```bash
    npm run dev
    ```
4.  Acesse `localhost:3000` no seu navegador.

## 👨‍💻 Créditos

* **Desenvolvedor da Aplicação:** [Jhonatas Matos](https://github.com/jhonatasmatos)
