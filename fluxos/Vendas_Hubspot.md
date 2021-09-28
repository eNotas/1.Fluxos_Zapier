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

[[Comercial] Pipefy (cliente preencheu o form Novo usuário) > Hubspot](#2-comercial-pipefy-cliente-preencheu-o-form-novo-usuário--hubspot),  [Pipefy (Checklist Onboarding) > Hubspot PRINCIPAL - Novo Usuário](#12-pipefy-checklist-onboarding--hubspot-principal---novo-usuário) e [Pipefy (Checklist Onboarding) > Hubspot PRINCIPAL - Renegociação](#13-pipefy-checklist-onboarding--hubspot-principal---renegociação).

**Atualizado em** 28/09/2021

### 2. [Comercial] Pipefy (cliente preencheu o form Novo usuário) > Hubspot

A cada novo card de cliente no pipe: **eNotas - Não usar [Comercial] Auxiliar Novo Usuário**, o fluxo atualiza cada informação do deal no Hubspot, além disso ele envia mensagem no slack no canal faturas_hubspot.

Este é um dos fluxos que serão interrompidos caso o campo **CNPJ Busca no Pipefy** não esteja preenchido e de forma correta, pois o fluxo busca o CNPJ correspondente na planilha intermediária preenchida no [Fluxo 1](#1-comercial-auxiliar-na-automação-do-fluxo-novo-usuário---criar-linha-em-planilha-quando-deal-muda-para-aceite-verbal).

![Fluxo_1-2](https://github.com/eNotas/1.Fluxos_Zapier/blob/main/imagens/Fluxo_1-2.jpg)

**Atualizado em** 28/09/2021

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

**Atualizado em** 28/09/2021

### 4. [Comercial] Pipefy (cliente preencheu o form Renegociação) > Hubspot

A cada novo card de cliente no pipe: **eNotas - Não Usar [Comercial] Auxiliar Renegociação / Casos atípicos**, o fluxo atualiza cada informação do deal no Hubspot. Além disso, ele envia mensagem no slack no canal faturas_hubspot.

Este é um dos fluxos que serão interrompidos caso o campo **CNPJ Busca no Pipefy** não esteja preenchido e de forma correta, pois o fluxo busca o CNPJ correspondente na planilha intermediária preenchida no [Fluxo 3](#3-comercial-auxiliar-na-automação-do-fluxo-renegociação---criar-linha-em-planilha-quando-deal-muda-para-aceite-verbal).

![Fluxo_3-4](https://github.com/eNotas/1.Fluxos_Zapier/blob/main/imagens/Fluxo_3-4.jpg)

**Atualizado em** 28/09/2021

### 5. [Comercial] Cliente ganho Hubspot (Sales Pipeline) > Cria card [Financeiro] Novo usuário

A cada novo negócio no pipeline de **closer** com estágio **"negócio ganho"**, este fluxo é disparado. As informações do cliente são enviadas para o pipe: **eNotas - [Financeiro] Novo Usuário** e então um novo card é criado.

![Fluxo_6](https://github.com/eNotas/1.Fluxos_Zapier/blob/main/imagens/Fluxo_6.jpg)

**Atualizado em** 28/09/2021

### 6. [Comercial] Cliente ganho Hubspot (Renegociação Pipeline) > Cria card [Financeiro] Upgrade/Downgrade

A cada novo negócio no pipeline de **renegociação / casos atípicos** com estágio **"negócio ganho"** este fluxo é disparado. Em seguida será aplicado um filtro: caso o campo "Ação Renegociação / Casos atípicos" for igual a "Downgrade GW / Emissor Business" ou vazio o fluxo será interrompido.

Os Campos de interesse são:

* Valor CNPJ excedente - Ajuste Comercial;
* Valor nota excedente - Ajuste Comercial.

As informações do cliente são enviadas para o pipe: **eNotas - [Financeiro] Upgrade / Downgrade** e então um novo card é criado.

![Fluxo_7](https://github.com/eNotas/1.Fluxos_Zapier/blob/main/imagens/Fluxo_7.jpg)

**Atualizado em** 28/09/2021

### 7. [Comercial] Cliente ganho Hubspot (Sales Pipeline) > Cria card [Financeiro] Novo Usuário Migração de produto/Cross sell/Segunda conta

A cada novo negócio no pipeline **renegociação / casos atípicos** com estágio **"negócio ganho"** este fluxo será disparado. Em seguida será aplicado um filtro: caso o campo "Ação Renegociação / Casos atípicos" for diferente de **"Migração de produto"** ou **"Cross sell"** ou **"Segunda conta GW/Emissor Business"** o fluxo será interrompido.

Os Campos de interesse são:

* Valor CNPJ excedente - Ajuste Comercial;
* Valor nota excedente - Ajuste Comercial.

As informações do cliente são enviadas para o pipe: **eNotas - [Financeiro] Novo usuário** e então um novo card é criado.

![Fluxo_8](https://github.com/eNotas/1.Fluxos_Zapier/blob/main/imagens/Fluxo_8.jpg) 

**Atualizado em** 28/09/2021

### 8. **[Financeiro] Alteração dados cadastrais > Hubspot Jurídico**

A cada card movido no pipe: **eNotas - [Financeiro] Alteração de dados/plano/faturamento ou importação de vendas**, o fluxo cria associação do contato criado ou atualizado ao negócio no Hubspot. Caso a fase atual seja diferente de **"cadastrados"** e o campo "Necessita de revisão do Contrato" for diferente de **"sim"**, o fluxo será interrompido.

![Fluxo_9](https://github.com/eNotas/1.Fluxos_Zapier/blob/main/imagens/Fluxo_9.jpg) 

**Atualizado em** 28/09/2021

### 	9. **[Suporte/Financeiro] Renegociação/Casos atípicos > Hubspot Renegociação/Casos atípicos**

A cada card movido no pipe: **eNotas - [Suporte / Financeiro] Renegociação / casos atípicos GW/Emissor Business** o fluxo é disparado. Caso a fase atual seja diferente de "Hubspot", o fluxo será interrompido.

O Fluxo cria ou atualiza contato no Hubspot preenchendo os seguintes campos:

- email da empresa já cadastrada;
- Cargo do contato;
- Pessoa do contato;
- Telefone;
- Lifecycle stage;
- Razão social da empresa já cadastrada.

Em seguida cria um negócio a partir do contato criado na etapa anterior e cria uma associação destes. Por fim uma notificação é enviada ao slack no canal: **renegociaçõeshubspot**

![Fluxo_10](https://github.com/eNotas/1.Fluxos_Zapier/blob/main/imagens/Fluxo_10.jpg) 

**Atualizado em** 28/09/2021

### 10. **[Comercial] Cliente ganho Hubspot (Renegociação Pipeline) > Suporte**

A cada novo negócio do pipeline **Renegociação/Casos atípicos** em estágio "**Negócio Ganho**" um email é enviado para "suporte@enotas.com.br".

![Fluxo_13](https://github.com/eNotas/1.Fluxos_Zapier/blob/main/imagens/Fluxo_13.jpg) 

**Atualizado em** 28/09/2021

### 11. **Enviar novos contatos Call Page para o Hubspot (new call)**

A cada evento "nova ligação" no Callpage cria um contato no Hubspot.

![Fluxo_14](https://github.com/eNotas/1.Fluxos_Zapier/blob/main/imagens/Fluxo_14.jpg)

**Atualizado em** 28/09/2021

### 12. **Pipefy (Checklist Onboarding) > Hubspot PRINCIPAL - Novo Usuário**

A cada novo card no pipe: **eNotas - Não usar [Comercial] Auxiliar Checklist Onboarding** o fluxo é disparado. O fluxo procura o deal ID no Hubspot e atualiza o negócio com as informações caso encontrado.

![Fluxo_27](https://github.com/eNotas/1.Fluxos_Zapier/blob/main/imagens/Fluxo_27.jpg)

**Atualizado em** 28/09/2021

### 13. Pipefy (Checklist Onboarding) > Hubspot PRINCIPAL - Renegociação

A cada novo card no pipe: **eNotas - Não usar [Comercial] Auxiliar Checklist Onboarding** o fluxo é disparado. O fluxo procura o deal ID no Hubspot e atualiza o negócio com as informações caso encontrado.

![Fluxo_33](https://github.com/eNotas/1.Fluxos_Zapier/blob/main/imagens/Fluxo_33.jpg)

**Atualizado em** 28/09/2021
