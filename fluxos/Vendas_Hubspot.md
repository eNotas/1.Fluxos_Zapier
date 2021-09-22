# Vendas Hubspot

Este bloco contem os fluxos que envolvem origem ou destino no Hubspot.

### 1. [Comercial] Auxiliar na automação do fluxo Novo usuário - criar linha em planilha quando deal muda para Aceite Verbal

A partir de cada novo negócio no pipeline de closer com estágio **"aceite verbal"** este fluxo é disparado. 

Os campos enviados são:

* Deal ID;
* Deal name;
* CNPJ Busca no Pipefy;
* Deal owner.

Obs: O campo **CNPJ Busca no Pipefy** precisa estar preenchido e de forma correta, caso contrário irá travar as seguintes automações: 

[[Comercial] Pipefy (cliente preencheu o form Novo usuário) > Hubspot](#2-comercial-pipefy-cliente-preencheu-o-form-novo-usuário--hubspot) e *Pipefy (Checklist Onboarding) > Hubspot PRINCIPAL - Novo Usuário*.

### 2. [Comercial] Pipefy (cliente preencheu o form Novo usuário) > Hubspot

A partir de cada novo card de cliente no pipefy, o fluxo atualiza cada informação do deal no Hubspot.

Este é um dos fluxos que serão interrompidos caso o campo **CNPJ Busca no Pipefy** não esteja preenchido e de forma correta, pois o fluxo busca o CNPJ correspondente na planilha intermediária preenchida no [Fluxo 1](#1-comercial-auxiliar-na-automação-do-fluxo-novo-usuário---criar-linha-em-planilha-quando-deal-muda-para-aceite-verbal).

![Fluxo_1-2](https://github.com/eNotas/1.Fluxos_Zapier/blob/main/imagens/Fluxo_1-2.jpg)

### 3. [Comercial] Auxiliar na automação do fluxo renegociação - criar linha em planilha quando deal muda para Aceite Verbal





