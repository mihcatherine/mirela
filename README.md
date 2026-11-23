# MAKARIA

Aplicativo de Gestão Financeira Pessoal desenvolvido por Mirela Catherine de Oliveira.

## Arquivos

- index.html
- app.js
- style.css
- logo.svg

## Publicação

Envie os quatro arquivos para a raiz do repositório do GitHub Pages.

## Appwrite

Endpoint: https://nyc.cloud.appwrite.io/v1
Project ID: 6b01e299000b19ac36ce
Database ID: 6b01e350001ca47807e5

Os Table IDs conhecidos já estão configurados no app.js. A tabela `cards` ainda precisa do Table ID real. Substitua `COLE_ID_CARDS` pelo ID da tabela de Cartões no Appwrite.

## Segurança

Com Row Security ativado, as tabelas devem permitir criação por usuários autenticados. O aplicativo atribui permissões de leitura, atualização e exclusão ao usuário da linha criada.

## Recursos

Dashboard, transações, orçamento, metas, contas, cartões, investimentos, contas a pagar, relatórios, calendário, categorias, salário, configurações, modo claro/escuro e cálculos automáticos.

## Identidade

O rodapé e a assinatura utilizam o nome completo: Mirela Catherine de Oliveira.

## Área de Renda — atualização
A aba de salário foi transformada em uma área de **Renda e Descontos**. O usuário informa apenas a Renda Principal e pode adicionar livremente Rendas Extras e Descontos/Encargos, usando valor fixo ou percentual da renda bruta.

Os itens personalizados são mantidos por usuário no navegador. A Renda Principal continua salva no Appwrite na tabela `settings`, sem alterar o esquema existente.


### Cálculo de renda personalizado

Na aba Renda, a Renda Bruta é a base dos cálculos. Cada Renda Extra ou Desconto pode ser cadastrado como Valor Fixo (R$) ou Percentual Da Renda Bruta (%). Quando percentual for escolhido, o Makaria mostra imediatamente o valor equivalente em reais.


### IDs das tabelas Appwrite

profiles: profiles
settings: 6b01e569002a228a1c5b
transactions: 6b01e6aa0036b4223488
goals: 6b01e8700035f839daea
accounts: 6b01fc9a00179915f55c
categories: 6b01fd500025ac427542
bills: 6b01fdb800341288b640
cards: 6b020079002ad9473ae5


## Versão 100% final — publicação

Esta versão contém os IDs das oito tabelas Appwrite configurados, isolamento por usuário nas tabelas que usam `user_id`, permissões de linha para o usuário autenticado e a aba de Renda com valor fixo ou percentual da Renda Bruta.

Antes da publicação definitiva, confirme no Appwrite que o Row Security está habilitado nas tabelas e que usuários autenticados possuem permissão de Create no nível da tabela; as permissões de Read/Update/Delete ficam por linha para o próprio usuário.


### IDs das tabelas — configuração fornecida
profiles - profiles
settings - 6b01e569002a228a1c5b
transactions - 6b01e6aa0036b4223488
goals - 6b01e6aa0036b4223488
accounts - 6b01fc9a00179915f55c
categories - 6b01fd500025ac427542
bills - 6b01fdb800341288b640
cards - 6b020079002ad9473ae5


### IDs das tabelas — configuração final confirmada
profiles - profiles
settings - 6b01e569002a228a1c5b
transactions - 6b01e6aa0036b4223488
goals - 6b01e8700035f839daea
accounts - 6b01fc9a00179915f55c
categories - 6b01fd500025ac427542
bills - 6b01fdb800341288b640
cards - 6b020079002ad9473ae5


## Auditoria da versão 100%

A versão de publicação utiliza Appwrite TablesDB diretamente no navegador autenticado. Todas as tabelas de dados do usuário recebem `user_id` no momento da criação e as consultas utilizam `Query.equal("user_id", user.$id)`. As linhas criadas recebem permissões de leitura, atualização e exclusão para o próprio usuário.

IDs confirmados:
- profiles: profiles
- settings: 6b01e569002a228a1c5b
- transactions: 6b01e6aa0036b4223488
- goals: 6b01e8700035f839daea
- accounts: 6b01fc9a00179915f55c
- categories: 6b01fd500025ac427542
- bills: 6b01fdb800341288b640
- cards: 6b020079002ad9473ae5
