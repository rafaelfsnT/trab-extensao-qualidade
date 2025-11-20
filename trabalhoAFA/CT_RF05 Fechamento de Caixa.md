### Caso de Teste 01: Fechar caixa com sucesso
| ID       | Descrição                                                        |
| :------- | :---------------------------------------------------------------- |
|C05-CT01	 | Caixa do dia fechado e registrado.|

| **Pré-condições**                                             |
| :------------------------------------------------------------ |
|Haver pelo menos uma venda no dia.|

| **Passos**                                             |
| :------------------------------------------------------------ |
DADO que o usuário abre o Livro Caixa
QUANDO clicar em “Fechar Caixa”
ENTÃO o caixa deve ser finalizado.

| **Critérios de Aceitação**                                             |
| :------------------------------------------------------------ |
|O dia fica bloqueado para novas movimentações.|
| Teste evidenciado e aprovado
| https://jam.dev/c/fb3ed20d-d5e5-422a-9634-af0ee95f6d53 |

### Caso de Teste 02: Tentar fechar caixa sem vendas no dia
| ID       | Descrição                                                        |
| :------- | :---------------------------------------------------------------- |
|C05-CT02	 | Sistema deve impedir fechamento vazio.|

| **Pré-condições**                                             |
| :------------------------------------------------------------ |
|Nenhuma venda registrada.|

| **Passos**                                             |
| :------------------------------------------------------------ |
DADO que usuário tenta fechar caixa
QUANDO clicar em Fechar
ENTÃO deve exibir alerta de **nenhuma movimentação**.

| **Critérios de Aceitação**                                             |
| :------------------------------------------------------------ |
|Bloqueio do fechamento.|
| Teste evidenciado e reprovado: Mesmo com um valor adicional, e sem vendas, ele me permite fechar o caixa |
| https://jam.dev/c/57b7fa33-a4e8-4652-a03e-0b16abae9b52 |

### Caso de Teste 03: Retirada de valor maior que o saldo atual
| ID       | Descrição                                                        |
| :------- | :---------------------------------------------------------------- |
|C05-CT04	 | Sistema deve bloquear retirada de valor maior que o saldo.|

| **Pré-condições**                                             |
| :------------------------------------------------------------ |
|Nenhuma.|

| **Passos**                                             |
| :------------------------------------------------------------ |
DADO que o usuário clica em retirar valores
E seleciona um valor maior que o saldo atual
QUANDO tentar salvar
ENTÃO deve exibir alerta de erro de valor nao pode ser maior que o saldo atual.

| **Critérios de Aceitação**                                             |
| :------------------------------------------------------------ |
|Retirada não registrada.|
| Teste evidenciado e aprovado | 
| https://jam.dev/c/0973366b-6630-40e0-ba08-c2a3ab28e696 |
