# Vendas Hotmart

Este bloco contem os fluxos que envolvem origem ou destino no Hotmart.

### 1. [Mkt e Onboarding] Vendas Hotmart 

A cada **compra aprovada, atrasada ou cancelamento de assinatura** Hotmart esse fluxo é disparado.

Cada ação hotmart levará a um caminho diferente A, B ou C, como mostrado abaixo:

![Fluxo_5](https://github.com/eNotas/1.Fluxos_Zapier/blob/main/imagens/Fluxo_5.jpg)

A cada compra aprovada, o fluxo seguirá o caminho A. Este fluxo cria ou atualiza contato no Hubspot, além de criar card no pipefy, no pipe **eNotas - CS - Onboarding**.

![Fluxo_5.1](https://github.com/eNotas/1.Fluxos_Zapier/blob/main/imagens/Fluxo_5.1.jpg)

A cada compra com status **"atrasado"**, que possua **recorrência 1**, o fluxo seguirá o caminho B. Como finalidade ele atualiza contato no hubspot e cria linha na planilha **"Pagamentos atrasados Hotmart"**, na aba **"Página 1"**.

![Fluxo_5.2](https://github.com/eNotas/1.Fluxos_Zapier/blob/main/imagens/Fluxo_5.2.jpg)

A cada compra atrasada que vira aprovada, que possua status **"aprovado"** e **"recorrência 1"**, o fluxo seguirá o caminho C. Como finalidade ele atualiza o status do contato no hubspot para **"Ativo"** e atualiza linha na planilha  **"Pagamentos atrasados Hotmart"** na aba **"Página 1"**.

![Fluxo_5.3](https://github.com/eNotas/1.Fluxos_Zapier/blob/main/imagens/Fluxo_5.3.jpg)

**Atualizado em** 27/09/2021

### 2. [Mkt] Integração Afiliados Pipefy-Hubspot 

A cada card movido no pipefy **eNotas - Programa de Afiliados Hotmart** para a fase **"Aprovada"**, o fluxo cria ou atualiza contato no Hubspot com as informações de nome e telefone do afiliado.

![Fluxo_15](https://github.com/eNotas/1.Fluxos_Zapier/blob/main/imagens/Fluxo_15.jpg)

**Atualizado em **27/09/2021



### 3. [Vendas Hotmart] Cancelados pelo Admin (Hotmart) 

A cada cancelamento do emissor feito pela Hotmart, o fluxo cria ou atualiza contato com o status da conta: **"Inativo"** e o status do cliente para **"Cancelado pelo Admin"**, além disso ele envia uma mensagem no canal **notif-cancelamento** do slack.

![Fluxo_11](https://github.com/eNotas/1.Fluxos_Zapier/blob/main/imagens/Fluxo_11.jpg)

### 4. [Vendas Hotmart] Cancelados pelo cliente (Hotmart) 

A cada cancelamento do emissor Hotmart feito pelo cliente, o fluxo cria ou atualiza contato com o status da conta: **"Inativo"** e o status do cliente para **"Cancelado pelo cliente"**, além disso ele envia uma mensagem no canal **notif-cancelamento** do slack.

![Fluxo_12](https://github.com/eNotas/1.Fluxos_Zapier/blob/main/imagens/Fluxo_12.jpg)
