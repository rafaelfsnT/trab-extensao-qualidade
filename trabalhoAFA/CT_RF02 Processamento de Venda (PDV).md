### Caso de Teste 01: Venda completa com sucesso
| ID       | Descrição                                                        |
| :------- | :---------------------------------------------------------------- |
|C02-CT01	 | Venda registrada, estoque reduzido e caixa alimentado.|

| **Pré-condições**                                             |
| :------------------------------------------------------------ |
|Cliente, funcionário e produtos cadastrados.|
|Produto com estoque suficiente.|

| **Passos**                                                        |
| :------------------------------------------------------------ |
DADO que o usuário clica em **Novo** na tela de vendas
E escolhe cliente, funcionário e data
E insere produtos
QUANDO finalizar e salvar
ENTÃO a venda deve aparecer no Livro Caixa.

| **Critérios de Aceitação**                                         |
| :------------------------------------------------------------ |
|Estoque atualizado.|
|Caixa alimentado.|
|Teste realizado e evidenciado|
|https://jam.dev/c/f6c968ce-3d9f-4646-8192-b54a685e5da3|

### Caso de Teste 02: Produto sem estoque
| ID       | Descrição                                                        |
| :------- | :---------------------------------------------------------------- |
|C02-CT02	 | Sistema deve impedir venda sem estoque.|

| **Pré-condições**                                             |
| :------------------------------------------------------------ |
|Produto com quantidade = 10.|

| **Passos**                                                        |
| :------------------------------------------------------------ |
DADO que o usuário tenta incluir o produto
QUANDO selecionar quantidade
ENTÃO deve exibir mensagem “Estoque insuficiente”.

| **Critérios de Aceitação**                                             |
| :------------------------------------------------------------ |
|Produto não deve entrar na venda.|
|Teste realizado e reprovado: Produto sem estoque e venda foi finalizada normalmente|
|https://jam.dev/c/15494647-8e71-4e1d-9ffb-33276af7010f|


### Caso de Teste 03: Finalizar venda sem selecionar tipo de documento
| ID       | Descrição                                                        |
| :------- | :---------------------------------------------------------------- |
|C02-CT03	 | Sistema deve impedir finalização sem forma de pagamento.|

| **Pré-condições**                                             |
| :------------------------------------------------------------ |
|Venda pronta para finalizar.|

| **Passos**                                                        |
| :------------------------------------------------------------ |
DADO que o usuário está na tela final
QUANDO clicar em “Salvar” sem escolher tipo de documento
ENTÃO deve exibir erro.

| **Critérios de Aceitação**                                             |
| :------------------------------------------------------------ |
|Finalização bloqueada.|
|Teste evidenciado e aprovado|
|https://jam.dev/c/08df020a-9370-41e4-b60f-bcf1f3aa792f|

### Caso de Teste 04: Cadastrar uma venda sem selecionar um usuário
| ID       | Descrição                                                        |
| :------- | :---------------------------------------------------------------- |
|C02-CT04	 | Sistema deve impedir cadastramento sem usuário.|

| **Pré-condições**                                             |
| :------------------------------------------------------------ |
|Campo cliente vazio.|

| **Passos**                                                        |
| :------------------------------------------------------------ |
DADO que o usuário está na tela de vendas
E clica em novo
E deixa o campo cliente
QUANDO clicar em ***Salvar***
ENTÃO o sistema exibe um erro informando que precisa colocar um cliente.

| **Critérios de Aceitação**                                             |
| :------------------------------------------------------------ |
|Cadastramento bloqueado.|
|Teste evidenciado e aprovado|
| https://jam.dev/c/69bc1e56-57a3-4942-a7b6-2db1cc5ca640 |