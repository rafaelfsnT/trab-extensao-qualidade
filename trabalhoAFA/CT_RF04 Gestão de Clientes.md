### Caso de Teste 01: Cadastro de cliente PF com sucesso
| ID       | Descrição                                                        |
| :------- | :---------------------------------------------------------------- |
|C04-CT01	 | Cadastro básico deve ser salvo corretamente.|

| **Pré-condições**                                             |
| :------------------------------------------------------------ |
|Nenhuma.|

| **Passos**                                             |
| :------------------------------------------------------------ |
DADO que usuário clica em “Novo”
E preenche os campos obrigatórios
QUANDO clicar em Salvar
ENTÃO cliente deve aparecer na lista.

| **Critérios de Aceitação**                                             |
| :------------------------------------------------------------ |
|Cadastro salvo.|
| Teste evidenciado e aprovado|
| https://jam.dev/c/b0862efa-25d3-4ae4-ad07-f8e36fd18b40 |

### Caso de Teste 02: Tentativa de salvar cliente sem campos obrigatórios
| ID       | Descrição                                                        |
| :------- | :---------------------------------------------------------------- |
|C04-CT02	 | Sistema deve impedir cadastro incompleto.|

| **Pré-condições**                                             |
| :------------------------------------------------------------ |
|Nenhuma.|

| **Passos**                                                        |
| :------------------------------------------------------------ |
DADO que o usuário deixa Nome ou CEP vazio
QUANDO tentar salvar
ENTÃO deve exibir alerta.

| **Critérios de Aceitação**                                             |
| :------------------------------------------------------------ |
|Cadastro bloqueado.|
|Teste evidenciado e aprovado|
| https://jam.dev/c/cd220250-3ee4-45a9-94af-59817d94235c |

### Caso de Teste 03: Exclusão de Cliente cadastrado
| ID       | Descrição                                                        |
| :------- | :---------------------------------------------------------------- |
|C04-CT03	 | Sistema deleta e redireciona para a tela de clientes.|

| **Pré-condições**                                             |
| :------------------------------------------------------------ |
|Cliente cadastrado no sistema.|

| **Passos**                                             |
| :------------------------------------------------------------ |
DADO que o usuário acessa a tela de cliente
E selecionamos o cliente para ser excluído
QUANDO clica em excluir
ENTÃO o sistema exclui o cliente selecionado.

| **Critérios de Aceitação**                                             |
| :-------------
|----------------------------------------------- |
|Alerta exibido.|
|Teste evidenciado e aprovado|
| https://jam.dev/c/ef17c97f-e465-4c35-b9bc-e75df6083911 |

### Caso de Teste 04: Habilitar limite para o cliente
| ID       | Descrição                                                        |
| :------- | :---------------------------------------------------------------- |
|C04-CT03	 | Sistema verifica e redireciona para a tela de Clientes.|

| **Pré-condições**                                             |
| :------------------------------------------------------------ |
|Cliente com cadastrado.|

| **Passos**                                             |
| :------------------------------------------------------------ |
DADO que o usuário está na tela de clientes
E seleciona o usuário que deseja habilitar o limite
E clica no ícone de configurações
E habilita as opções ***Dados Financeiros*** e ***Dependentes***
QUANDO a clica em salvar
ENTÃO o sistema pede para colocar as credencias e colocar um nome.

| **Critérios de Aceitação**                                             |
| :-------------
|----------------------------------------------- |
|Alterações salva.|
|Campos financeiros agora aparecem.|
|Teste evidenciado e aprovado|
| https://jam.dev/c/a4f209b3-fab5-40e8-8289-6df0c893276a |

### Caso de Teste 05: Realizar um venda a prazo sem limite de crédito
| ID       | Descrição                                                        |
| :------- | :---------------------------------------------------------------- |
|C04-CT04	 | Sistema alerta e não realiza a venda para o cliente.|

| **Pré-condições**                                             |
| :------------------------------------------------------------ |
|Cliente cadastrado com limite inferior que o valor da venda.|

| **Passos**                                             |
| :------------------------------------------------------------ |
DADO que usuário acessa aba Vendas
E clica em ***Novo***
E preenche todos os campos
E seleciona cliente com limite baixo
QUANDO vai para finalizar a compra e coloca a prazo
ENTÃO o sistema mostra um alerta informando que o cliente tem um limite inferior

| **Critérios de Aceitação**                                             |
| :------------------------------------------------------------ |
|Cliente aparece listado.|
|Teste evidenciado e aprovado|
| https://jam.dev/c/f6e927a6-dec9-40a8-b88c-0bb3b494d7a6 |
