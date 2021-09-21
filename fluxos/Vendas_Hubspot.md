# Vendas Hubspot

Este bloco contem os fluxos que envolvem origem ou destino no Hubspot.

[TOC]

### 1. [Comercial] Auxiliar na automação do fluxo Novo usuário - criar linha em planilha quando deal muda para Aceite Verbal

A partir de cada novo negócio no pipeline de closer com estágio **"aceite verbal"** este fluxo é disparado. 

Os campos enviados são:

* Deal ID;
* Deal name;
* CNPJ Busca no Pipefy;
* Deal owner.

Obs: O campo **CNPJ Busca no Pipefy** precisa estar preenchido e de forma correta, caso contrário irá travar as seguintes automações: 

[[Comercial] Pipefy (cliente preencheu o form Novo usuário) > Hubspot](#2. [Comercial] Pipefy (cliente preencheu o form Novo usuário) > Hubspot) e *Pipefy (Checklist Onboarding) > Hubspot PRINCIPAL - Novo Usuário*.

### 2. [Comercial] Pipefy (cliente preencheu o form Novo usuário) > Hubspot

A partir de cada novo card de cliente no pipefy, o fluxo atualiza cada informação do deal no Hubspot.

Este é um dos fluxos que serão interrompidos caso o campo **CNPJ Busca no Pipefy** não esteja preenchido e de forma correta, pois o fluxo busca o CNPJ correspondente na planilha intermediária preenchida no [Fluxo 1](#1. [Comercial] Auxiliar na automação do fluxo Novo usuário - criar linha em planilha quando deal muda para Aceite Verbal).



![](G:\Drives compartilhados\DADOS E PERFOMANCE\DADOS E PERFOMANCE\2021\Repositorio_Github\1.Fluxos_Zapier\imagens\Fluxo_1-2.jpg)



### 3. [Comercial] Auxiliar na automação do fluxo renegociação - criar linha em planilha quando deal muda para Aceite Verbal





