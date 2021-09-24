# Vendas Hubspot

Este bloco contem os fluxos que envolvem origem ou destino no Hubspot.

### 1. [Comercial] Auxiliar na automação do fluxo Novo usuário - criar linha em planilha quando deal muda para Aceite Verbal

A cada novo negócio no pipeline de **closer** com estágio **"aceite verbal"** este fluxo é disparado. 

Os campos enviados são:

* Deal ID;
* Deal name;
* CNPJ Busca no Pipefy;
* Deal owner.

Obs: O campo **CNPJ Busca no Pipefy** precisa estar preenchido e de forma correta, caso contrário irá travar as seguintes automações: 

[[Comercial] Pipefy (cliente preencheu o form Novo usuário) > Hubspot](#2-comercial-pipefy-cliente-preencheu-o-form-novo-usuário--hubspot) e *Pipefy (Checklist Onboarding) > Hubspot PRINCIPAL - Novo Usuário*.

### 2. [Comercial] Pipefy (cliente preencheu o form Novo usuário) > Hubspot

A cada novo card de cliente no pipe: **eNotas - Não usar [Comercial] Auxiliar Novo Usuário**, o fluxo atualiza cada informação do deal no Hubspot.

Este é um dos fluxos que serão interrompidos caso o campo **CNPJ Busca no Pipefy** não esteja preenchido e de forma correta, pois o fluxo busca o CNPJ correspondente na planilha intermediária preenchida no [Fluxo 1](#1-comercial-auxiliar-na-automação-do-fluxo-novo-usuário---criar-linha-em-planilha-quando-deal-muda-para-aceite-verbal).

![Fluxo_1-2](https://github.com/eNotas/1.Fluxos_Zapier/blob/main/imagens/Fluxo_1-2.jpg)

### 3. [Comercial] Auxiliar na automação do fluxo renegociação - criar linha em planilha quando deal muda para Aceite Verbal

A cada novo negócio no pipeline de **renegociação / valores** **atípicos** com estágio **"jurídico"** este fluxo é disparado. 

Os campos enviados são:

* Deal ID;
* Deal name;
* CNPJ Busca no Pipefy;
* Deal owner;
* Ação - Renegociação Casos/Casos Atípicos.

Obs: O campo **CNPJ Busca no Pipefy** precisa estar preenchido e de forma correta, caso contrário irá travar a seguinte automação: 

[Comercial] Pipefy (cliente preencheu o form renegociação) > Hubspot.

### 4. [Comercial] Pipefy (cliente preencheu o form Renegociação) > Hubspot

A cada novo card de cliente no pipe: **eNotas - Não Usar [Comercial] Auxiliar Renegociação / Casos atípicos**, o fluxo atualiza cada informação do deal no Hubspot.

Este é um dos fluxos que serão interrompidos caso o campo **CNPJ Busca no Pipefy** não esteja preenchido e de forma correta, pois o fluxo busca o CNPJ correspondente na planilha intermediária preenchida no [Fluxo 3](#1-comercial-auxiliar-na-automação-do-fluxo-novo-usuário---criar-linha-em-planilha-quando-deal-muda-para-aceite-verbal).

![Fluxo_3-4](https://github.com/eNotas/1.Fluxos_Zapier/blob/main/imagens/Fluxo_3-4.jpg)

### 5. [Comercial] Cliente ganho Hubspot (Sales Pipeline) > Cria card [Financeiro] Novo usuário

A cada novo negócio no pipeline de **closer** com estágio **"negócio ganho"**, este fluxo é disparado. As informações do cliente são enviadas para o pipe: **eNotas - [Financeiro] Novo Usuário** e então um novo card é criado.

![Fluxo_6](https://github.com/eNotas/1.Fluxos_Zapier/blob/main/imagens/Fluxo_6.jpg)

### 6. [Comercial] Cliente ganho Hubspot (Renegociação Pipeline) > Cria card [Financeiro] Upgrade/Downgrade

A cada novo negócio no pipeline de **renegociação / casos atípicos** com estágio **"negócio ganho"** este fluxo é disparado. Em seguida será aplicado um filtro: caso o campo "Ação Renegociação / Casos atípicos" for igual a "Downgrade GW / Emissor Business" ou vazio o fluxo será interrompido.

Os Campos de interesse são:

* Valor CNPJ excedente - Ajuste Comercial;
* Valor nota excedente - Ajuste Comercial.

As informações do cliente são enviadas para o pipe: **eNotas - [Financeiro] Upgrade / Downgrade** e então um novo card é criado.

![Fluxo_7](https://github.com/eNotas/1.Fluxos_Zapier/blob/main/imagens/Fluxo_7.jpg)

### 7. [Comercial] Cliente ganho Hubspot (Sales Pipeline) > Cria card [Financeiro] Novo Usuário Migração de produto/Cross sell/Segunda conta

A cada novo negócio no pipeline **renegociação / casos atípicos** com estágio **"negócio ganho"** este fluxo será disparado. Em seguida será aplicado um filtro: caso o campo "Ação Renegociação / Casos atípicos" for diferente de **"Migração de produto"** ou **"Cross sell"** ou **"Segunda conta GW/Emissor Business"** o fluxo será interrompido.

Os Campos de interesse são:

* Valor CNPJ excedente - Ajuste Comercial;
* Valor nota excedente - Ajuste Comercial.

As informações do cliente são enviadas para o pipe: **eNotas - [Financeiro] Novo usuário** e então um novo card é criado.

![Fluxo_8](https://github.com/eNotas/1.Fluxos_Zapier/blob/main/imagens/Fluxo_8.jpg) 

### 8. **[Financeiro] Alteração dados cadastrais > Hubspot Jurídico**

A cada card movido no pipe: **eNotas - [Financeiro] Alteração de dados/plano/faturamento ou importação de vendas**, o fluxo cria associação do contato criado ou atualizado ao negócio no Hubspot. Caso a fase atual seja diferente de **"cadastrados"** e o campo "Necessita de revisão do Contrato" for diferente de **"sim"**, o fluxo será interrompido.

![Fluxo_9](https://github.com/eNotas/1.Fluxos_Zapier/blob/main/imagens/Fluxo_9.jpg) 

