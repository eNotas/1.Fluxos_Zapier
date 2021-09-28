# Jurídico

Este bloco contem os fluxos que envolvem informações do Jurídico.

### 1. Alerta Jurídico - banco de dados (PJ)

A cada novo card criado no pipe: **eNotas - Banco de dados admisão (PJ)**, uma mensagem é enviada no Slack no canal: **alertas_jurídico**.

![Fluxo_17](https://github.com/eNotas/1.Fluxos_Zapier/blob/main/imagens/Fluxo_17.jpg)

**Atualizado em**: 28/09/2021

### 2. Alerta Jurídico - Novo Card Contratos Fornecedores

A cada novo card criado no pipe: **eNotas - Contrato fornecedores**, uma mensagem é enviada no Slack no canal: **alertas_jurídico**.

![Fluxo_18](https://github.com/eNotas/1.Fluxos_Zapier/blob/main/imagens/Fluxo_18.jpg)

**Atualizado em**: 28/09/2021

### 3. Avisar jurídico de cancelamento

A cada card movido no pipe: **eNotas - Cancelamento de Conta GW e Emissor Business**, o fluxo será disparado.

Cada ação levará a um caminho diferente A, B ou C, como mostrado abaixo:

![Fluxo_32](https://github.com/eNotas/1.Fluxos_Zapier/blob/main/imagens/Fluxo_32.jpg)

Se o campo "**Current Phase Name**" estiver preenchido com **"Jurídico"** no card, o fluxo seguirá o caminho A. Em seguida uma mensagem será enviada para o Slack no canal: "**alertas_jurídico**".

![Fluxo_32.1](https://github.com/eNotas/1.Fluxos_Zapier/blob/main/imagens/Fluxo_32.1.jpg)

Se o campo "**Current Phase Name**" estiver preenchido com **"Alteração de Plano"** no card, o fluxo seguirá o caminho B. Em seguida uma mensagem será enviada para o Slack no canal: "**alertas_jurídico**".

![Fluxo_32.2](https://github.com/eNotas/1.Fluxos_Zapier/blob/main/imagens/Fluxo_32.2.jpg)

Se o campo "**Current Phase Name**" estiver preenchido com **"Churn Finalizado"** no card, o fluxo seguirá o caminho C. Em seguida uma mensagem será enviada para o Slack no canal: "**alertas_jurídico**"

![Fluxo_32.3](https://github.com/eNotas/1.Fluxos_Zapier/blob/main/imagens/Fluxo_32.3.jpg)

Obs: Qualquer outra informação preenchida no campo **"Curren Phase Name"** diferente de: **"Jurídico"**, **"Alteração de Plano"** e **"Churn Finalizado"**, o fluxo será interrompido.

**Atualizado em**: 28/09/2021

### 4. Enviar cliente ganho Hubspot para jurídico

A cada novo negócio no pipeline: **"Closer"** no estágio **"Negócio ganho"**, um card é criado no pipe: **eNotas - Gestão de Contrato Comercial**.

![Fluxo_22](https://github.com/eNotas/1.Fluxos_Zapier/blob/main/imagens/Fluxo_22.jpg)

**Atualizado em**: 28/09/2021

### 5. Envio assinatura Chris: Admissões PJ

A cada card finalizado no pipe: **"eNotas - Banco de dados admissão (PJ)"**, uma mensagem é enviada no Slack no canal: **"juridico-assinatura"**.

![Fluxo_19](https://github.com/eNotas/1.Fluxos_Zapier/blob/main/imagens/Fluxo_19.jpg)

**Atualizado em**: 28/09/2021

### 6. Envio assinatura Chris: Alterações PJ

A cada card finalizado no pipe: **"eNotas - [SERVIÇO] DP - Promoções, Aumentos e Alterações de Função (PJ)"**, uma mensagem é enviada no Slack no canal: **"juridico-assinatura"**.

Obs: O e-mail do pipefy usado neste fluxo é "guilherme@enotas.com.br", caso este e-mail venha a ser desativado, o fluxo será interrompido.

![Fluxo_20](https://github.com/eNotas/1.Fluxos_Zapier/blob/main/imagens/Fluxo_20.jpg)

**Atualizado em**: 28/09/2021

### 7. Envio assinatura Chris: contrato de fornecedores

A cada card finalizado no pipe: **"eNotas - Contrato Fornecedores"**, uma mensagem é enviada no Slack no canal: **"juridico-assinatura"**.

![Fluxo_21](https://github.com/eNotas/1.Fluxos_Zapier/blob/main/imagens/Fluxo_21.jpg)

**Atualizado em**: 28/09/2021
