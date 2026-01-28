Plano de Teste


*Aplicação Alvo:** [BugBank UI - Jhonatas Matos](https://github.com/jhonatasmatos/bugbank-ui)
Resonsável: [Eduardo Antero](https://www.linkedin.com/in/eduardoantero/)

## 1. Introdução

Este documento formaliza a estratégia de testes, o escopo de atuação e o planejamento tático para a validação da qualidade da aplicação **Bug Bank**.

O Bug Bank é uma aplicação Web que simula o ambiente de um banco digital, permitindo a execução de transações financeiras e gestão de contas. Devido à natureza financeira do sistema (Core Banking), a garantia da integridade das transações e a segurança dos dados do usuário são prioridades críticas deste plano.

Este plano serve como guia para a equipe de Qualite Assurence e stakeholders, alinhando as expectativas sobre *o que* será testado, *como* será testado e *quais* critérios definem o sucesso da entrega.

## 2. Objetivos dos Testes

O objetivo primário deste ciclo de testes é mitigar riscos funcionais e garantir que as operações críticas do banco possam ser realizadas com sucesso pelo usuário final.

Os objetivos específicos incluem:

* **Validar o Core Banking:** Assegurar que fluxos críticos (Cadastro, Login e Transferência) funcionem conforme as regras de negócio, sem bloqueios.
* **Garantir a Integridade dos Dados:** Verificar se os saldos e extratos são calculados corretamente e persistem adequadamente no *Local Storage* após recarregamentos ou novas sessões.
* **Avaliar a Experiência do Usuário (UX):** Confirmar se os feedbacks visuais (mensagens de erro, cores de saldo, alertas de sucesso) estão claros e em conformidade com o design esperado.
* **Identificar e Documentar Falhas:** Mapear os bugs intencionais e não intencionais da aplicação, fornecendo evidências claras para correção (simulada) futura.

## 3.  🎯 Escopo dos Testes

 O foco deste ciclo de testes validar as principais funcionalidades críticas do sistema bancário ("Core Banking"), garantindo que as operações financeiras e de acesso são seguras e funcionais.

As seguintes funcionalidades serão testadas:

* **🔐 Autenticação (Login):** Validação de acesso com credenciais válidas, inválidas e tratamento de erros.
* **📝 Cadastro de Contas:** Verificação do fluxo de criação de novas contas, incluindo regras de senhas e dados obrigatórios.
* **💸 Transferências:** Testes de transferência entre contas (mesmo banco), validação de saldo insuficiente e input de valores inválidos.
* **📄 Extrato Bancário:** Conferência do histórico de transações e atualização do saldo em tempo real.

Funcionalidades que não serão testadas:
* Saque
* Pagamento
  
  > **Nota:** Funcionalidades Saque e Pagamentos não possuem regras de negocio, requisitos funcionais e ainda estão em desenvolvimento.


## 4. Abordagem de Teste

A abordagem de qualidade definida para o projeto concentra-se no **Nível de Teste de Sistema**, utilizando a técnica de **Caixa-Preta**. O objetivo é validar o comportamento externo da aplicação sem interagir com sua estrutura interna de código, garantindo que o produto final atenda aos requisitos especificados.

A estratégia apoia-se primariamente em **Testes Funcionais**, assegurando que todas as regras de negócio sejam cumpridas conforme o esperado. Para complementar a validação formal e identificar comportamentos imprevistos, serão executados **Testes Exploratórios** guiados por heurísticas de teste consolidadas.

Visando a robustez na entrada de dados, serão aplicados testes focados em **Ataques a Tipos de Dados** e validação de **Strings**. Estes cenários cobrirão situações críticas, como a inserção de nomes excessivamente longos, uso de caracteres especiais e acentuados, tratamento de espaços (*trimming*) no início ou fim dos campos, além da validação de unicidade para impedir registros duplicados.

Devido ao uso de Local Storage, a estratégia de testes incluirá a Limpeza de Cache/Storage entre ciclos de teste críticos ou a utilização de janelas anônimas (Incognito Mode) para garantir que cada teste comece com um estado limpo, evitando 'sujeira' de dados de testes anteriores.


## 5. Critérios de Teste

### 5.1. Critérios de Aceite (ou Entrada)
Para que a fase de execução de testes possa ser iniciada, os seguintes pré-requisitos devem ser atendidos:
* A aplicação deve estar acessível via navegador Chrome após a configuração do ambiente local.
* A aplicação deve carregar a página inicial (Login/Home) sem erros de console (JavaScript) que impeçam a visualização dos elementos básicos.
* O recurso de *Local Storage* do navegador deve estar habilitado e disponível para escrita/leitura.

### 5.2. Critérios de Suspensão e Retomada
A execução dos testes será suspensa caso ocorra alguma das situações abaixo, sendo retomada apenas após a correção ou contorno do problema:
* **Suspensão:** Identificação de falhas bloqueantes (Showstoppers) que impeçam o login ou a navegação entre as telas principais, impossibilitando a execução dos demais casos de teste.
* **Suspensão:** Inconsistência crítica no ambiente (ex: navegador travando persistentemente ao acessar a aplicação).
* **Retomada:** Os testes continuarão assim que o defeito bloqueante for corrigido ou um contorno (workaround) for estabelecido, permitindo o fluxo da navegação.

### 5.3. Critérios de Saída
A fase de testes será considerada concluída quando:
* 100% dos casos de teste planejados tiverem sido executados.
* Todos os bugs encontrados (intencionais ou não) estiverem devidamente documentados/reportados com evidências.
* Criação e entrega do relatório final de execução de testes.



## 6. 📦 Entregáveis

Os seguintes artefatos serão produzidos e versionados neste repositório ao final do ciclo de testes:

* **Plano de Testes:** Documento de estratégia.
* [**Cenários e Casos de Teste:**](./Cenario-e-casos-de-teste.md) Planilha/Documento contendo o passo a passo, massa de dados e resultados esperados.
* **Relatórios de Bugs:** Documentação técnica dos defeitos encontrados (evidências, severidade e passos para reprodução).
* **Relatórios de Sessão:** Documentação técnica obtida através de sessões de testes exploratórios.
* **Resultados de Teste:** Relatório sumarizado com métricas de execução e parecer final da qualidade.

## 7. ⚙️ Recursos

### 7.1. Ambiente de Teste
Configuração utilizada para a execução e validação dos cenários:

* **Hardware:** Desktop
* **Sistema Operacional:** Windows 11.
* **Navegador:** Google Chrome (Versão Atualizada - Última Stable).
* **URL da Aplicação:** `http://localhost:3000` (Ambiente Local).

### 7.2. Ferramentas de Teste
Softwares utilizados para apoio à gestão e execução:

* **Gestão e Reporte:** Jira Software/Zephyr
* **Documentação e Escrita:** Google Sheets
* **Captura de Evidências:** Snipping Tool (Ferramenta de Captura Windows).
*    Git

## 8. ⚠️ Riscos e Mitigação

Abaixo estão listados os riscos identificados para o projeto e as estratégias adotadas para minimizá-los:

| Risco Identificado | Estratégia de Mitigação |
| :--- | :--- |
| **Indisponibilidade da aplicação online** (Queda do servidor Netlify). | Configuração e execução do projeto em ambiente local (`localhost`) via Node.js. |
| **Ambiguidade ou mudança nos requisitos** durante a execução. | Validação das regras de negócio diretamente na documentação oficial antes da abertura de defeitos. |

## 9. 📅 Cronograma

O projeto está estimado para ser concluído em **11 dias**, conforme o cronograma abaixo:

| Fase | Duração | Atividades Principais |
| :--- | :---: | :--- |
| **1. Planejamento e Design** | 3 dias | • Análise de requisitos e regras.<br>• Modelagem dos Casos de Teste (Login, Cadastro, etc).<br>• Revisão dos roteiros. |
| **2. Execução e Gestão** | 5 dias | • Configuração do ambiente.<br>• Execução manual dos testes.<br>• Reporte de bugs no Jira. |
| **3. Encerramento** | 3 dias | • Validação dos resultados.<br>• Compilação de métricas.<br>• Elaboração do parecer de qualidade. |











