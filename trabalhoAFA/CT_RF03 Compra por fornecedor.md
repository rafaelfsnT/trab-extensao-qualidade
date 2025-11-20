### Caso de Teste 01: Compra concluída com sucesso
| ID       | Descrição                                                        |
| :------- | :---------------------------------------------------------------- |
|C03-CT01	 | Compra lançada, estoque atualizado e caixa alimentado.|

| **Pré-condições**                                             |
| :------------------------------------------------------------ |
|Fornecedor cadastrado.|
|Produto cadastrado.|

| **Passos**                                                        |
| :------------------------------------------------------------ |
DADO que o usuário cria nova compra
E adiciona produtos
QUANDO finalizar compra
ENTÃO estoque deve ser alimentado.

| **Critérios de Aceitação**                                             |
| :------------------------------------------------------------ |
|Compra CONFIRMADA.|
| Teste evidenciado e aprovado|
| https://jam.dev/c/67730b93-1f20-4555-a455-c46fa58ccc44 |

### Caso de Teste 02: Fornecedor cadastrado com sucesso
| ID       | Descrição                                                        |
| :------- | :---------------------------------------------------------------- |
|C03-CT02	 | Fornecedor cadastado no sistema, e redirecionado para a tela de fornecedores.|

| **Pré-condições**                                             |
| :------------------------------------------------------------ |
|Nenhuma.|

| **Passos**                                                        |
| :------------------------------------------------------------ |
DADO que usuário acessa a tela criar fornecedores
E preencher os dados necessários para cadastros
QUANDO clicar em **Salvar**
ENTÃO o sistema deve cadastrar um novo fornecedor.

| **Critérios de Aceitação**                                             |
| :------------------------------------------------------------ |
| Teste evidenciado e reprovado, deu erro no campo de CEP, mesmo colocando um CEP válido|
| https://jam.dev/c/e0191c25-8700-427c-ba42-36021ed146fc |

### Caso de Teste 03: Fornecedor não infomado.
| ID       | Descrição                                                        |
| :------- | :---------------------------------------------------------------- |
|C03-CT02	 | Deve impedir compra sem fornecedor.|

| **Pré-condições**                                             |
| :------------------------------------------------------------ |
|Nenhuma.|

| **Passos**                                                        |
| :------------------------------------------------------------ |
DADO que usuário tenta criar compra sem fornecedor
QUANDO clicar em **Salvar**
ENTÃO sistema deve bloquear.

| **Critérios de Aceitação**                                             |
| :------------------------------------------------------------ |
|Mensagem “Fornecedor obrigatório”.|
| Teste evidenciado e aprovado|
| https://jam.dev/c/c73f6654-fd76-4d2f-a941-1530834e1008 |

### Caso de Teste 04: Tipo de documento sem preencher
| ID       | Descrição                                                        |
| :------- | :---------------------------------------------------------------- |
|C03-CT03	 | Sistema deve recusar finalização de compra sem um tipo de documento.|

| **Pré-condições**                                             |
| :------------------------------------------------------------ |
|Estar finalizando uma compra.|

| **Passos**                                             |
| :------------------------------------------------------------ |
DADO que o usuário cria uma nova compra
E chega para finalizar uma compra
E deixa sem um tipo de documento ao finalizar
QUANDO selecionar a clicar em **Salvar**
ENTÃO deve exibir uma mensagem de erro.

| **Critérios de Aceitação**                                             |
| :------------------------------------------------------------ |
|Mensagem de alerta: É necessário informar o tipo de documento.|
| Teste realizado e evidenciado|
| https://jam.dev/c/654a3236-024a-4189-abef-a2bddae3be0d |