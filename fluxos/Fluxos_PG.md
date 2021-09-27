# Fluxos PG

Este bloco contem os fluxos que envolvem informações de pagamentos.

### 1. Criação card Trello Demanda de Equipamentos

A cada novo card criado no pipe: **eNotas - [SERVIÇO] RH - Abertura de Vaga**, um card é criado no Trello no Board **"Demandas Equipamentos"**, na lista **"Demanda"**.

Obs: A conta utilizada do pipefy é "eduarda@enotas.com.br". O funcionamento deste fluxo depende deste e-mail estar ativo, caso contrário o fluxo irá ser interrompido.

![Fluxo_26](https://github.com/eNotas/1.Fluxos_Zapier/blob/main/imagens/Fluxo_26.jpg)

**Atualizado em**: 27/09/2021

### 2. Atualização Trello Demanda de Equipamentos

A cada card movido no pipe: **eNotas - [SERVIÇO] RH - Abertura de Vaga**, um comentário é criado no Trello no Board **"Demandas Equipamentos"**, na lista **"Demanda**".

Obs: A conta utilizada do pipefy é "eduarda@enotas.com.br". O funcionamento deste fluxo depende deste e-mail estar ativo, caso contrário o fluxo irá ser interrompido. 

![Fluxo_23](https://github.com/eNotas/1.Fluxos_Zapier/blob/main/imagens/Fluxo_23.jpg)

**Atualizado em**: 27/09/2021

### 3. E-MAIL > Boletos e Notas

A cada nova pesquisa de e-mail correspondida com o assunto "**boleto fatura nota"** no Gmail, uma mensagem é enviada ao Slack no canal: **"boletos-notas"**.

Obs: A conta utilizada do slack é "@eduarda". O funcionamento deste fluxo depende desta conta estar ativa, caso contrário o fluxo irá ser interrompido. 

![Fluxo_24](https://github.com/eNotas/1.Fluxos_Zapier/blob/main/imagens/Fluxo_24.jpg)

**Atualizado em**: 27/09/2021

### 4. E-mail do Chris

A cada nova pesquisa de e-mail correspondida enviada por "christophe@enotas.com.br" no Gmail, uma mensagem é enviada ao Slack para o username "Duda".

![Fluxo_25](https://github.com/eNotas/1.Fluxos_Zapier/blob/main/imagens/Fluxo_25.jpg)

**Atualizado em**: 27/09/2021
