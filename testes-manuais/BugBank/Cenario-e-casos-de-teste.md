## Cenários e Casos de Teste

Responsável: Eduardo Antero

Data: 21/01/2016

<a id="index"></a>
## Sumário

<details>
    <summary><a href="#c01">Cenário 01: Onboarding e Abertura de Conta Digital</a></summary>
    <ul>
        <li><a href="#c01ct1">Caso de Teste 01: Cadastro de conta bem sucedido com saldo</a></li>
        <li><a href="#c01ct2">Caso de Teste 02: Cadastro de conta bem sucedido sem saldo</li>
        <li><a href="#c01ct3">Caso de Teste 03: Cadastrar usuário sem preencher campo nome</li>
        <li><a href="#c01ct4">Caso de Teste 04: Cadastrar usuário sem preencher campo email</li>
        <li><a href="#c01ct5">Caso de Teste 05: Cadastrar usuário sem preencher campo senha</li>
        <li><a href="#c01ct6">Caso de Teste 06: Cadastrar usuário sem confirmar senha</li>
        <li><a href="#c01ct7">Caso de Teste 07: Cadastrar usuário com senhas divergentes</li>
        <li><a href="#c01ct8">Caso de Teste 08: Cadastrar usuário já cadastrado</li>
  </ul>
</details>

<details>
    <summary><a href="#c02">Cenário 02: Autenticação e Segurança de Acesso</a></summary>
    <ul>
        <li><a href="#c02ct1">Caso de Teste 01: Autenticação com dados de usuário e senha válidos </a></li>
        <li><a href="#c02ct2">Caso de Teste 02: Autenticação com dados de usuário inválido</a></li>
        <li><a href="#c02ct3">Caso de Teste 03: Autenticação com senha inválida</a></li>
        <li><a href="#c02ct4">Caso de Teste 04: Autenticação com dados de usuário não cadastrado</a></li>
        <li><a href="#c02ct5">Caso de Teste 05: Autenticação sem preencher os dados obrigatórios</a></li>
    </ul>

</details>

<details>
    <summary><a href="#c03">Cenário 03: Transações e Movimentações</a></summary>
    <ul>
        <li><a href="#c03ct1">Caso de Teste 01: Transferência bem sucedida</a></li>
        <li><a href="#c03ct2">Caso de Teste 02: Transferência de uma conta válida para conta inválida</li>
        <li><a href="#c03ct3">Caso de Teste 03: Transferência com saldo insulficiente</li>
        <li><a href="#c03ct4">Caso de Teste 04: Transferência sem preencher campo descrição</li>
        <li><a href="#c03ct5">Caso de Teste 05: Transferência sem preencher conta destino</li>
        <li><a href="#c03ct6">Caso de Teste 06: Transferência com número e digito da conta com letras</li>
        <li><a href="#c03ct7">Caso de Teste 07: Transferência de valor menor que zero </li>
        <li><a href="#c03ct8">Caso de Teste 08: Transferência de valor igual a zero </li>
    </ul>
</details>

<details>
    <summary><a href="#c04">Cenário 04: Auditoria de Saldo e Histórico Financeiro</a></summary>
    <ul>
        <li>Caso de Teste 01:</li>
    </ul>
</details>




<a id="c01"></a>
## Cenário 01: Cadastro de usuário
**Objetivo:** Validar o fluxo de registro de novos clientes, garantindo a persistência correta dos dados e validação de requisitos de senha.

<a id="c01ct1"></a>
### Caso de Teste 01: Cadastro de conta com saldo inicial
<table>
  <tr>
    <td width="30%"><b>ID:</b> C01-CT01</td>
    <td width="70%"><b>Objetivo:</b> Validar se o sistema cria corretamente uma nova conta atribuindo o saldo</td>
  </tr>
  <tr>
    <td colspan="2">
      <b>Pré-Condições:</b>
      <ul>
        <li>O usuário deve estar na tela inicial da aplicação (Home).</li>
        <li>O e-mail utilizado no teste não deve existir na base de dados.</li>
      </ul>
    </td>
  </tr>
  <tr>
    <td colspan="2">
      <p><b>Passos:</b></p>
      <div><b>DADO</b> que o usuário está na tela inicial e clica no botão "Registrar"</div>
      <div><b>E</b> preenche o campo "E-mail" com "eduardo@email.com"</div>
      <div><b>E</b> preenche o campo "Nome" com "Eduardo Antero"</div>
      <div><b>E</b> preenche o campo "Senha" com "Teste123"</div>
      <div><b>E</b> preenche o campo "Confirmação de senha" com "Teste123"</div>
      <div><b>E</b> ativa a opção "Criar conta com saldo" (Toggle Ativo)</div>
      <div><b>QUANDO</b> clica no botão "Cadastrar"</div>
      <div><b>ENTÃO</b> deve exibir mensagem de sucesso informando número da conta criada"</div>
    </td>
  </tr>
  <tr>
    <td colspan="2">
      <b>Critérios de Aceite:</b>
      <ul>
        <li>Exibição mensagem confirmando cadastro foi realizado e número da conta após o cadastro</li>
      </ul>
    </td>
  </tr>
</table>

<a id="c01ct2"></a>
### Caso de Teste 02: Cadastro de conta bem sucedido sem saldo
<table>
  <tr>
    <td width="30%"><b>ID:</b> C01-CT02</td>
    <td width="70%"><b>Objetivo:</b> Validar se o sistema cria corretamente uma nova conta atribuindo R$ 0,00 de saldo</td>
  </tr>
  <tr>
    <td colspan="2">
      <b>Pré-Condições:</b>
      <ul>
        <li>O usuário deve estar na tela inicial da aplicação (Home).</li>
        <li>O e-mail utilizado no teste não deve existir na base de dados.</li>
      </ul>
    </td>
  </tr>
  <tr>
    <td colspan="2">
      <p><b>Passos:</b></p>
      <div><b>DADO</b> que o usuário está na tela inicial e clica no botão "Registrar"</div>
      <div><b>E</b> preenche o campo "E-mail" com "eduardo@email.com"</div>
      <div><b>E</b> preenche o campo "Nome" com "Eduardo Antero"</div>
      <div><b>E</b> preenche o campo "Senha" com "Teste123"</div>
      <div><b>E</b> preenche o campo "Confirmação de senha" com "Teste123"</div>
      <div><b>QUANDO</b> clica no botão "Cadastrar"</div>
      <div><b>ENTÃO</b> deve exibir mensagem de sucesso informando número da conta criada"</div>
    </td>
  </tr>
  <tr>
    <td colspan="2">
      <b>Critérios de Aceite:</b>
      <ul>
        <li>Exibição mensagem confirmando cadastro foi realizado e número da conta após o cadastro</li>
      </ul>
    </td>
  </tr>
</table>

<a id="c01ct3"></a>
### Caso de Teste 03: Cadastrar usuário sem preencher campo nome
<table>
  <tr>
    <td width="30%"><b>ID:</b> C01-CT03</td>
    <td width="70%"><b>Objetivo:</b> Validar se o sistema informa falta de preenchemento obrigatório do campo "Nome"</td>
  </tr>
  <tr>
    <td colspan="2">
      <b>Pré-Condições:</b>
      <ul>
        <li>O usuário deve estar na tela inicial da aplicação (Home).</li>
        <li>O e-mail utilizado no teste não deve existir na base de dados.</li>
      </ul>
    </td>
  </tr>
  <tr>
    <td colspan="2">
      <p><b>Passos:</b></p>
      <div><b>DADO</b> que o usuário está na tela inicial e clica no botão "Registrar"</div>
      <div><b>E</b> preenche o campo "E-mail" com "eduardo@email.com"</div>
      <div><b>E</b> preenche o campo "Senha" com "Teste123"</div>
      <div><b>E</b> preenche o campo "Confirmação de senha" com "Teste123"</div>
      <div><b>QUANDO</b> clica no botão "Cadastrar"</div>
      <div><b>ENTÃO</b> deve exibir mensagem informando "Nome não pode ser vazio"</div>
    </td>
  </tr>
  <tr>
    <td colspan="2">
      <b>Critérios de Aceite:</b>
      <ul>
        <li>Exibição mensagem de não preenchimento do campo nome</li>
      </ul>
    </td>
  </tr>
</table>

<a id="c01ct4"></a>
### Caso de Teste 04: Cadastrar usuário sem preencher campo email
<table>
  <tr>
    <td width="30%"><b>ID:</b> C01-CT04</td>
    <td width="70%"><b>Objetivo:</b> Validar se o sistema informa falta de preenchimento do campo obrigatório email</td>
  </tr>
  <tr>
    <td colspan="2">
      <b>Pré-Condições:</b>
      <ul>
        <li>O usuário deve estar na tela inicial da aplicação (Home)</li>
      </ul>
    </td>
  </tr>
  <tr>
    <td colspan="2">
      <p><b>Passos:</b></p>
      <div><b>DADO</b> que o usuário está na tela inicial e clica no botão "Registrar"</div>
      <div><b>E</b> preenche o campo "Nome" com "Eduardo Antero"</div>
      <div><b>E</b> preenche o campo "Senha" com "Teste123"</div>
      <div><b>E</b> preenche o campo "Confirmação de senha" com "Teste123"</div>
      <div><b>QUANDO</b> clica no botão "Cadastrar"</div>
      <div><b>ENTÃO</b> deve exibir mensagem informando "Email não pode ser vazio"</div>
    </td>
  </tr>
  <tr>
    <td colspan="2">
      <b>Critérios de Aceite:</b>
      <ul>
        <li>Exibição mensagem de não preenchimento do campo email</li>
      </ul>
    </td>
  </tr>
</table>

<a id="c01ct5"></a>
### Caso de Teste 05: Cadastrar usuário sem preencher campo senha
<table>
  <tr>
    <td width="30%"><b>ID:</b> C01-CT05</td>
    <td width="70%"><b>Objetivo:</b> Validar se o sistema informa falta de preenchimento do campo obrigatório senha</td>
  </tr>
  <tr>
    <td colspan="2">
      <b>Pré-Condições:</b>
      <ul>
        <li>O usuário deve estar na tela inicial da aplicação (Home)</li>
      </ul>
    </td>
  </tr>
  <tr>
    <td colspan="2">
      <p><b>Passos:</b></p>
      <div><b>DADO</b> que o usuário está na tela inicial e clica no botão "Registrar"</div>
      <div><b>E</b> preenche o campo "Nome" com "Eduardo Antero"</div>
      <div><b>E</b> preenche o campo "Email" com "eduardo@email.com"</div>
      <div><b>E</b> preenche o campo "Confirmação de senha" com "Teste123"</div>
      <div><b>QUANDO</b> clica no botão "Cadastrar"</div>
      <div><b>ENTÃO</b> deve exibir mensagem informando "Senha não pode ser vazio"</div>
    </td>
  </tr>
  <tr>
    <td colspan="2">
      <b>Critérios de Aceite:</b>
      <ul>
        <li>Exibição mensagem de não preenchimento do campo senha</li>
      </ul>
    </td>
  </tr>
</table>

<a id="c01ct6"></a>
### Caso de Teste 06: Cadastrar usuário sem confirmar senha

<table>
  <tr>
    <td width="30%"><b>ID:</b> C01-CT06</td>
    <td width="70%"><b>Objetivo:</b> Validar se o sistema informa falta de preenchimento do campo obrigatório de confirmação de senha</td>
  </tr>
  <tr>
    <td colspan="2">
      <b>Pré-Condições:</b>
      <ul>
        <li>O usuário deve estar na tela inicial da aplicação (Home).</li>
        <li>O e-mail utilizado no teste não deve existir na base de dados.</li>
      </ul>
    </td>
  </tr>
  <tr>
    <td colspan="2">
      <p><b>Passos:</b></p>
      <div><b>DADO</b> que o usuário está na tela inicial e clica no botão "Registrar"</div>
      <div><b>E</b> preenche o campo "E-mail" com "eduardo@email.com"</div>
      <div><b>E</b> preenche o campo "Nome" com "Eduardo Antero"</div>
      <div><b>E</b> preenche o campo "Senha" com "Teste123"</div>
      <div><b>QUANDO</b> clica no botão "Cadastrar"</div>
      <div><b>ENTÃO</b> deve exibir mensagem informando "Confirmar senha não pode ser vazio"</div>
    </td>
  </tr>
  <tr>
    <td colspan="2">
      <b>Critérios de Aceite:</b>
      <ul>
        <li>Exibição mensagem informando obrigatoriedade do preenchimento do campo de confirmação de senha</li>
      </ul>
    </td>
  </tr>
</table>


<a id="c01ct7"></a>
### Caso de Teste 07: Cadastrar usuário com senhas divergentes

<table>
  <tr>
    <td width="30%"><b>ID:</b> C01-CT07</td>
    <td width="70%"><b>Objetivo:</b> Validar se o sistema informa divergência nos campos de senha e confirmação de senha</td>
  </tr>
  <tr>
    <td colspan="2">
      <b>Pré-Condições:</b>
      <ul>
        <li>O usuário deve estar na tela inicial da aplicação (Home).</li>
        <li>O e-mail utilizado no teste não deve existir na base de dados.</li>
      </ul>
    </td>
  </tr>
  <tr>
    <td colspan="2">
      <p><b>Passos:</b></p>
      <div><b>DADO</b> que o usuário está na tela inicial e clica no botão "Registrar"</div>
      <div><b>E</b> preenche o campo "E-mail" com "eduardo@email.com"</div>
      <div><b>E</b> preenche o campo "Nome" com "Eduardo Antero"</div>
      <div><b>E</b> preenche o campo "Senha" com "Teste123"</div>
      <div><b>E</b> preenche o campo "Confirmação de senha" com "Teste321"</div>
      <div><b>QUANDO</b> clica no botão "Cadastrar"</div>
      <div><b>ENTÃO</b> deve exibir mensagem informando divergência na senha e confirmação de senha</div>
    </td>
  </tr>
  <tr>
    <td colspan="2">
      <b>Critérios de Aceite:</b>
      <ul>
        <li>Bloqueio da ação de cadastro</li>
        <li>Exibição mensagem informando divergência na senha e confirmação de senha</li>
      </ul>
    </td>
  </tr>
</table>


<a id="c01ct8"></a>
### Caso de Teste 08: Caso de Teste 08: Cadastrar usuário já cadastrado

<table>
  <tr>
    <td width="30%"><b>ID:</b> C01-CT08</td>
    <td width="70%"><b>Objetivo:</b> Validar se o sistema impede a duplicidade de e-mails na base de dados</td>
  </tr>
  <tr>
    <td colspan="2">
      <b>Pré-Condições:</b>
      <ul>
        <li>O usuário deve estar na tela inicial da aplicação (Home).</li>
      </ul>
    </td>
  </tr>
  <tr>
    <td colspan="2">
      <p><b>Passos:</b></p>
      <div><b>DADO</b> que o usuário está na tela inicial e clica no botão "Registrar"</div>
      <div><b>E</b> preenche o campo "E-mail" com "eduardo@email.com"</div>
      <div><b>E</b> preenche o campo "Nome" com "Eduardo Antero"</div>
      <div><b>E</b> preenche o campo "Senha" com "Teste123"</div>
      <div><b>E</b> preenche o campo "Confirmação de senha" com "Teste123"</div>
      <div><b>QUANDO</b> clica no botão "Cadastrar"</div>
      <div><b>ENTÃO</b> deve exibir mensagem informando que não é possível criar conta, pois já existe usuário cadastrado com os dados</div>
    </td>
  </tr>
  <tr>
    <td colspan="2">
      <b>Critérios de Aceite:</b>
      <ul>
        <li>Manter a integridade do banco de dados evitando registros duplicados</li>
      </ul>
    </td>
  </tr>
</table>


<a id="c02"></a>

<p><a href="#index">Voltar para o sumário</a></p>

## Cenário 02: Autenticação e Segurança de Acesso
**Objetivo:** Assegurar que apenas usuários registrados tenham acesso à conta e que tentativas inválidas sejam tratadas adequadamente.

<a id="c02ct1"></a>
### Caso de Teste 01: Autenticação com dados de usuário e senha válidos
<table>
  <tr>
    <td width="30%"><b>ID:</b> C02-CT01</td>
    <td width="70%"><b>Objetivo:</b> Validar se sistema realiza autenticação de usuário com dados válidos</td>
  </tr>
  <tr>
    <td colspan="2">
      <b>Pré-Condições:</b>
      <ul>
        <li>O usuário deve estar na tela inicial da aplicação</li>
        <li>O e-mail utilizado no teste deve existir na base de dados</li>
      </ul>
    </td>
  </tr>
  <tr>
    <td colspan="2">
      <p><b>Passos:</b></p>
      <div><b>DADO</b> que o usuário está na tela inicial
      <div><b>E</b> preenche o campo "E-mail" com "eduardo@email.com"</div>
      <div><b>E</b> preenche o campo "Senha" com "Teste123"</div>
      <div><b>QUANDO</b> clica no botão "Acessar"</div>
      <div><b>ENTÃO</b> deve exibir mensagem de autenticação bem-sucedida e redirecionados usuário para a home</div>
    </td>
  </tr>
  <tr>
    <td colspan="2">
      <b>Critérios de Aceite:</b>
      <ul>
        <li>Exibição mensagem confirmando que autenticação foi realizada com sucesso</li>
        <li>Redirencionar usuário para home page</li>
      </ul>
    </td>
  </tr>
</table>


Caso de Teste 02: Autenticação com dados de usuário inválido

<a id="c02ct2"></a>
### Caso de Teste 02: Autenticação com dados de usuário inválidos
<table>
  <tr>
    <td width="30%"><b>ID:</b> C02-CT02</td>
    <td width="70%"><b>Objetivo:</b> Validar se o sistema informa impossibilidade de autenticação com usuário inválido</td>
  </tr>
  <tr>
    <td colspan="2">
      <b>Pré-Condições:</b>
      <ul>
        <li>O usuário deve estar na tela inicial da aplicação</li>
      </ul>
    </td>
  </tr>
  <tr>
    <td colspan="2">
      <p><b>Passos:</b></p>
      <div><b>DADO</b> que o usuário está na tela inicial
      <div><b>E</b> preenche o campo "E-mail" com "eduardo@email.com"</div>
      <div><b>E</b> preenche o campo "Senha" com "Teste12"</div>
      <div><b>QUANDO</b> clica no botão "Acessar"</div>
      <div><b>ENTÃO</b> deve exibir mensagem informando  usuário ou senha inválido</div>
    </td>
  </tr>
  <tr>
    <td colspan="2">
      <b>Critérios de Aceite:</b>
      <ul>
        <li> Exibição de mensagem informando usuário ou senha inválidos</li>
        <li> Não autorização acesso com usuário inválido </li>
      </ul>
    </td>
  </tr>
</table>

<p><a href="#index">Voltar para o sumário</a></p>

<a id="c03"></a>
## Cenário 03: Transações e Movimentações
**Objetivo:** Garantir a integridade das transferências financeiras, cálculos de débito/crédito e bloqueios de saldo insuficiente.

<a id="c03ct1"></a>
### Caso de Teste 01:Transferência bem sucedida
<table>
  <tr>
    <td width="30%"><b>ID:</b> C03-CT01</td>
    <td width="70%"><b>Objetivo:</b> Validar se o sistema realiza a transferência entre contas válidas com sucesso</td>
  </tr>
  <tr>
    <td colspan="2">
      <b>Pré-Condições:</b>
      <ul>
        <li>O usuário deve estar autenticado e logado na página de transferência.</li>
      </ul>
    </td>
  </tr>
  <tr>
    <td colspan="2">
      <p><b>Passos:</b></p>
      <div><b>DADO</b> que o usuário está na página de transferência</div>
      <div><b>E</b> preenche o campo "Número da conta" com "123-4"</div>
      <div><b>E</b> preenche o campo "Valor da transferência" com "100"</div>
      <div><b>E</b> preenche o campo "Descrição" com "Teste transferência válida"</div>
      <div><b>QUANDO</b> clica no botão "Transferir agora"</div>
      <div><b>ENTÃO</b> deve exibir mensagem de sucesso informando "Transferência realizada com sucesso" <b>E</b> atualizar os saldos de origem e destino</div>
    </td>
  </tr>
  <tr>
    <td colspan="2">
      <b>Critérios de Aceite:</b>
      <ul>
        <li>Exibição mensagem confirmando transferência</li>
        <li>Debito na conta origem</li>
        <li>Crédito na conta destino</li>
      </ul>
    </td>
  </tr>
</table>

<a id="c03ct2"></a>
### Caso de Teste 02: Transferência de uma conta válida para conta inválida

<table>
  <tr>
    <td width="30%"><b>ID:</b> C03-CT02</td>
    <td width="70%"><b>Objetivo:</b> Validar se o sistema bloqueia transferir valores para conta inválida</td>
  </tr>
  <tr>
    <td colspan="2">
      <b>Pré-Condições:</b>
      <ul>
        <li>O usuário deve estar autenticado e logado na página de transferência.</li>
      </ul>
    </td>
  </tr>
  <tr>
    <td colspan="2">
      <p><b>Passos:</b></p>
      <div><b>DADO</b> que o usuário está na página de transferência</div>
      <div><b>E</b> preenche o campo "Número da conta" com "999-9"</div>
      <div><b>E</b> preenche o campo "Valor da transferência" com "100"</div>
      <div><b>E</b> preenche o campo "Descrição" com "Teste transferência inválida"</div>
      <div><b>QUANDO</b> clica no botão "Transferir agora"</div>
      <div><b>ENTÃO</b> deve exibir mensagem de sucesso informando "Conta inválida ou inexistente" </div>
    </td>
  </tr>
  <tr>
    <td colspan="2">
      <b>Critérios de Aceite:</b>
      <ul>
        <li>Exibição mensagem informando conta inválida ou inexistente</li>
        <li>Impedimento da transação financeira</li>
      </ul>
    </td>
  </tr>
</table>

<a id="c03ct3"></a>
### Caso de Teste 03: Transferência com saldo insuficiente

<table>
  <tr>
    <td width="30%"><b>ID:</b> C03-CT03</td>
    <td width="70%"><b>Objetivo:</b> Validar se o sistema não realiza transferência pela falta de saldo</td>
  </tr>
  <tr>
    <td colspan="2">
      <b>Pré-Condições:</b>
      <ul>
        <li>O usuário deve estar na autenticado e na página de transferência.</li>
      </ul>
    </td>
  </tr>
  <tr>
    <td colspan="2">
      <p><b>Passos:</b></p>
      <div><b>DADO</b> que o usuário está na página de transferência</div>
      <div><b>E</b> preenche o campo "Número da conta" com "123-4"</div>
      <div><b>E</b> preenche o campo "Valor da transferência" com "2000"</div>
      <div><b>E</b> preenche o campo "Descrição" com "Teste transferência sem saldo"</div>
      <div><b>QUANDO</b> clica no botão "Transferir agora"</div>
      <div><b>ENTÃO</b> deve exibir mensagem informando "Saldo insuficiente" </div>
    </td>
  </tr>
  <tr>
    <td colspan="2">
      <b>Critérios de Aceite:</b>
      <ul>
        <li>Bloqueio da transação</li>
        <li>Manutenção do saldo atual</li>
        <li>Mensagem de erro contextualizada</li>
      </ul>
    </td>
  </tr>
</table>

<a id="c03ct4"></a>
### Caso de Teste 04: Transferência sem preencher campo descrição

<table>
  <tr>
    <td width="30%"><b>ID:</b> C03-CT04</td>
    <td width="70%"><b>Objetivo:</b> Validar a obrigatoriedade do campo descrição no formulário de transferência</td>
  </tr>
  <tr>
    <td colspan="2">
      <b>Pré-Condições:</b>
      <ul>
        <li>O usuário deve estar na autenticado e na página de transferência.</li>
      </ul>
    </td>
  </tr>
  <tr>
    <td colspan="2">
      <p><b>Passos:</b></p>
      <div><b>DADO</b> que o usuário está na página de transferência</div>
      <div><b>E</b> preenche o campo "Número da conta" com "999-9"</div>
      <div><b>E</b> preenche o campo "Valor da transferência" com "100"</div>
      <div><b>QUANDO</b> clica no botão "Transferir agora"</div>
      <div><b>ENTÃO</b>  sistema não deve realizar transferência <b>E</b> informar falta de preenchimento do campo descrição </div>
    </td>
  </tr>
  <tr>
    <td colspan="2">
      <b>Critérios de Aceite:</b>
      <ul>
        <li>Exibição mensagem informando falta do preenchimento da descrição da transferência</li>
      </ul>
    </td>
  </tr>
</table>

<a id="c03ct5"></a>
### Caso de Teste 05: Transferência sem preencher conta destino

<table>
  <tr>
    <td width="30%"><b>ID:</b> C03-CT05</td>
    <td width="70%"><b>Objetivo:</b> Validar impedimento de envio de valores sem definição de destinatário</td>
  </tr>
  <tr>
    <td colspan="2">
      <b>Pré-Condições:</b>
      <ul>
        <li>O usuário deve estar na autenticado e na página de transferência.</li>
      </ul>
    </td>
  </tr>
  <tr>
    <td colspan="2">
      <p><b>Passos:</b></p>
      <div><b>DADO</b> que o usuário está na página de transferência</div>
      <div><b>E</b> preenche o campo "Valor da transferência" com "2000"</div>
      <div><b>E</b> preenche o campo "Descrição" com "Teste transferência sem destinatário"</div>
      <div><b>QUANDO</b> clica no botão "Transferir agora"</div>
      <div><b>ENTÃO</b> deve exibir mensagem informando falta do preenchimento de conta destino</div>
    </td>
  </tr>
  <tr>
    <td colspan="2">
      <b>Critérios de Aceite:</b>
      <ul>
        <li>Exibição mensagem informando falta de conta destino</li>
      </ul>
    </td>
  </tr>
</table>

<a id="c03ct6"></a>
### Caso de Teste 06: Transferência com número e digito da conta com letras

<table>
  <tr>
    <td width="30%"><b>ID:</b> C03-CT06</td>
    <td width="70%"><b>Objetivo:</b> Validar se o sistema aceita apenas caracteres numéricos no campo da conta</td>
  </tr>
  <tr>
    <td colspan="2">
      <b>Pré-Condições:</b>
      <ul>
        <li>O usuário deve estar na autenticado e na página de transferência.</li>
      </ul>
    </td>
  </tr>
  <tr>
    <td colspan="2">
      <p><b>Passos:</b></p>
      <div><b>DADO</b> que o usuário está na página de transferência</div>
      <div><b>E</b> preenche o campo "Número da conta" com "1a23-a"</div>
      <div><b>E</b> preenche o campo "Valor da transferência" com "20"</div>
      <div><b>E</b> preenche o campo "Descrição" com "Teste transferência</div>
      <div><b>QUANDO</b> clica no botão "Transferir agora"</div>
      <div><b>ENTÃO</b> deve exibir mensagem informando dados da conta destinatário devem conter apenas números </div>
    </td>
  </tr>
  <tr>
    <td colspan="2">
      <b>Critérios de Aceite:</b>
      <ul>
        <li>Exibição mensagem informando conta destinário devem conter apenas números</li>
        <li>Validação de campo (máscara ou erro de formato) impedindo caracteres não numéricos</li>
      </ul>
    </td>
  </tr>
</table>

<a id="c03ct7"></a>
### Caso de Teste 07: Transferência de valor menor que zero 

<table>
  <tr>
    <td width="30%"><b>ID:</b> C03-CT07</td>
    <td width="70%"><b>Objetivo:</b> Validar impedimento de transferência com valores menores que zero</td>
  </tr>
  <tr>
    <td colspan="2">
      <b>Pré-Condições:</b>
      <ul>
        <li>O usuário deve estar na autenticado e na página de transferência.</li>
      </ul>
    </td>
  </tr>
  <tr>
    <td colspan="2">
      <p><b>Passos:</b></p>
      <div><b>DADO</b> que o usuário está na página de transferência</div>
      <div><b>E</b> preenche o campo "Número da conta" com "999-9"</div>
      <div><b>E</b> preenche o campo "Valor da transferência" com "-1"</div>
      <div><b>E</b> preenche o campo "Descrição" com "Teste transferência saldo negativo</div>
      <div><b>QUANDO</b> clica no botão "Transferir agora"</div>
      <div><b>ENTÃO</b> deve exibir mensagem  informando transferência não pode ser igual ou menor que zero</div>
    </td>
  </tr>
  <tr>
    <td colspan="2">
      <b>Critérios de Aceite:</b>
      <ul>
        <li>Bloqueio de valores negativos no processamento da transação</li>
        <li>Exibição mensagem informando que valor de transferência não pode ser igual ou menor que zero </li>
      </ul>
    </td>
  </tr>
</table>

<a id="c03ct8"></a>
### Caso de Teste 08: Transferência de valor igual a zero 

<table>
  <tr>
    <td width="30%"><b>ID:</b> C03-CT08</td>
    <td width="70%"><b>Objetivo:</b> Validar impedimento de transferência com valor igual a zero</td>
  </tr>
  <tr>
    <td colspan="2">
      <b>Pré-Condições:</b>
      <ul>
        <li>O usuário deve estar na autenticado e na página de transferência.</li>
      </ul>
    </td>
  </tr>
  <tr>
    <td colspan="2">
      <p><b>Passos:</b></p>
      <div><b>DADO</b> que o usuário está na página de transferência</div>
      <div><b>E</b> preenche o campo "Número da conta" com "999-9"</div>
      <div><b>E</b> preenche o campo "Valor da transferência" com "0"</div>
      <div><b>E</b> preenche o campo "Descrição" com "Teste transferência saldo 0</div>
      <div><b>QUANDO</b> clica no botão "Transferir agora"</div>
      <div><b>ENTÃO</b> deve exibir mensagem  informando transferência não pode ser igual ou menor que zero</div>
    </td>
  </tr>
  <tr>
    <td colspan="2">
      <b>Critérios de Aceite:</b>
      <ul>
        <li>Exibição mensagem informando que valor de transferência não pode ser igual ou menor que zero </li>
      </ul>
    </td>
  </tr>
</table>

<a id="c04"></a>

<p><a href="#index">Voltar para o sumário</a></p>

## Cenário 04: Auditoria de Saldo e Histórico Financeiro
**Objetivo:** Verificar a consistência visual e matemática do extrato, assegurando que o *Local Storage* reflete as transações realizadas.

### Caso de Teste 01:

<p><a href="#index">Voltar para o sumário</a></p>