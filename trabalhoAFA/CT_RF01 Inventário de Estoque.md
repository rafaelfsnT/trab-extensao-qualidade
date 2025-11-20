### Caso de Teste 01: Importar XML corretamente e gerar compra
| ID       | Descrição                                                       |
| ------- | ---------------------------------------------------------------- |
|C01-CT01	 | Importação de XML válido alimenta estoque corretamente.         |

| **Pré-condições**                                             |
| :------------------------------------------------------------ |
| - XML válido.                                       |
| - Produtos existentes na nota.                      |

| **Passos**                                                                 |
| :------------------------------------------------------------ |
DADO que o usuário acessa Pedidos > Importar XML de Compra
E preenche CFOP, Grupo e ST Entrada
E importa um XML válido
QUANDO clicar em “Gerar Compra” e depois “Finalizar”
ENTÃO o estoque deve ser atualizado e a compra aparecer como “CONFIRMADA”.

| **Critérios de aceitação**                                      |
| :------------------------------------------------------------ |
|Compra confirmada.|
|Produtos lançados no estoque.|
|Teste realizado e evidenciado|
|https://jam.dev/c/79c08b18-9f7d-47e1-a786-c1af12fde73d|

### Caso de Teste 02: Falta de preenchimento obrigatório
| ID       | Descrição                                                        |
| ------- | ---------------------------------------------------------------- |
|C01-CT03	 | Bloqueio da importação sem CFOP ou Grupo.|

| **Pré-condições**                                             |
| :------------------------------------------------------------ |
| - Nenhuma.|

| **Passos**                                                        |
| :------------------------------------------------------------ |
DADO que o usuário está na tela
E deixa CFOP ou Grupo em branco
QUANDO tentar importar XML
ENTÃO deve exibir mensagens de “campo obrigatório”.

| **Critérios de aceitação**                                      |
| :------------------------------------------------------------ |
|Campos obrigatórios validados.|
|Testes realizados e evidenciados|
|https://jam.dev/c/9ee01632-3e9f-4eec-a9f2-389ee946267a|

### Caso de Teste 03: Importar XML inválido
| ID       | Descrição                                                        |
| ------- | ---------------------------------------------------------------- |
|C01-CT02	 | Sistema deve recusar XML inválido.|

| **Pré-condições**                                             |
| :------------------------------------------------------------ |
| - XML com estrutura incorreta.|

| **Passos**                                                        |
| :------------------------------------------------------------ |
DADO que o usuário acessa a tela de importação de XML
E seleciona um XML corrompido
QUANDO clicar em “Importar XML”
ENTÃO deve aparecer erro e bloqueio da ação.

| **Critérios de aceitação**                                      |
| :------------------------------------------------------------ |
|Mensagem clara de erro.|
|Não deve permitir gerar compra.|
|Teste realizado e evidenciado|
|https://jam.dev/c/48b775ed-aa66-4854-9125-0d002863235d|


### Caso de Teste 04: Gerar compra mas não confirmar entrada
| ID       | Descrição                                                        |
| ------- | ---------------------------------------------------------------- |
|C01-CT04	| Compra deve permanecer pendente sem confirmação.|

| **Pré-condições**                                             |
| :------------------------------------------------------------ |
| - XML válido importado.|

| **Passos**                                                        |
| :------------------------------------------------------------ |
DADO que o usuário gera a compra
QUANDO sair da tela sem mudar o status para CONFIRMADA
ENTÃO a compra deve ficar com status “PENDENTE” e sem afetar o estoque.

| **Critérios de aceitação**                                      |
| :------------------------------------------------------------ |
|Estoque não alterado.|
|Teste realizado e evidenciado|
|https://jam.dev/c/ac82ea17-9bed-4435-bb18-b57dffccb29b|
