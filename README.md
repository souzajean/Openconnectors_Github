# ☁️ SAP CPI: Integração Dinâmica com GitHub

> ** Este iFlow realiza a integração entre o SAP Cloud Integration e o GitHub por meio do SAP Open Connectors, permitindo a leitura de arquivos de um repositório público. O fluxo consome o conteúdo do arquivo README.md

<br> 

🔹 Funcionamento

O fluxo é iniciado por uma requisição HTTP (HTTPS Sender), que aciona o iFlow no SAP CPI. Em seguida, um componente Request Reply consome o conector do GitHub via SAP Open Connectors, realizando uma chamada ao endpoint responsável por recuperar o conteúdo do arquivo.

<p align="center">
  <!-- SAP BTP / CPI -->
  <img src="https://img.shields.io/badge/SAP-Integration_Suite-008FD3?style=for-the-badge&logo=sap&logoColor=white" alt="SAP BTP">
  <!-- GitHub -->
  <img src="https://img.shields.io/badge/GitHub-Remote_Repo-181717?style=for-the-badge&logo=github&logoColor=white" alt="GitHub">
  <!-- Open Connectors -->
  <img src="https://img.shields.io/badge/Open_Connectors-Connectivity-orange?style=for-the-badge" alt="Open Connectors">
  <!-- JSON / API -->
  <img src="https://img.shields.io/badge/JSON-Data_Format-black?style=for-the-badge&logo=json&logoColor=white" alt="JSON">
  <!-- HTTPS -->
  <img src="https://img.shields.io/badge/Security-HTTPS-green?style=for-the-badge&logo=google-cloud&logoColor=white" alt="HTTPS">
  <!-- OAuth 2.0 (Comum em Open Connectors) -->
  <img src="https://img.shields.io/badge/Auth-OAuth_2.0-blueviolet?style=for-the-badge" alt="OAuth 2.0">
  <!-- REST -->
  <img src="https://img.shields.io/badge/Architecture-REST_API-00ADEF?style=for-the-badge&logo=postman&logoColor=white" alt="REST">
</p>


<p align="center">
  <img src="imagens/capa-linkedin.png" alt="Fluxo Principal" width="100%">
</p>

---

---

## 📋 Índice

<details open>
<summary><strong>Clique para expandir/recolher</strong></summary>

1. [🎯 Visão Geral](#-visão-geral)
2. [⚙️ Arquitetura da Solução](#️-arquitetura-da-solução)
3. [🔧 Configuração Open Connectors](#-como-funciona)
4. [📡 Configuração do iFlow](#-configuração-do-iflow)
5. [📡 Testando com Postman](#-testando-com-postman)
6. [🔐 Segurança & Boas Práticas](#-segurança--boas-práticas)
7. [📦 Downloads](#-downloads)
8. [🤝 Contribuindo](#-contribuindo)

</details>

---

<br>

## 🎯 Visão Geral

Este iFlow implementa uma integração entre o GitHub e o SAP Cloud Integration, utilizando o SAP Open Connectors como camada de abstração para consumo de APIs.

---

## ⚙️ Arquitetura da Solução

![Fluxo](imagens/Screenshot_28.png)

## 🚀 Como Funciona

### 📥 Entrada da Requisição

```
POST /github

```


## 🔧 Configuração do iFlow

> **Package:** `ZPKG_IntegrationGitHub_OpenConnectors`  
> **iFlow:** `IFL_GITHUB_INTEGRATION`

<br>


### 🔹 1. Extend Non SAP Connectivity
![Fluxo](imagens/Screenshot_1.png)

Nome do Package:
```
Discover Connectors
```

<br>

### 🔹 2. Conectar com o SAP ID
![Fluxo](imagens/Screenshot_2.png)

<br>

### 🔹 3. Home Open Connectors
Procurar o GitHub
![Fluxo](imagens/Screenshot_3.png)

<br>

### 🔹 4. Na aba Connectors
Caso não apareça o GitHubs
![Fluxo](imagens/Screenshot_4.png)

<br>

### 🔹 5. Configurando  Open Connectors para  o GitHub
```
Name: **Openconnectors_Github**
Configuration 
GitHub Organization: nome_da_sua_organização
GitHub Repository: **Openconnectors_Github**
```

![Fluxo](imagens/Screenshot_5.png)

<br>

### 🔹 6. Criando o Repositorio no GitHub
![Fluxo](imagens/Screenshot_6.png)

<br>

### 🔹 7. Adicionando o Repositorio no GitHub
```
Openconnectors_Github
```
![Fluxo](imagens/Screenshot_7.png)

<br>

### 🔹 7. Adicionando o README no GitHub
![Fluxo](imagens/Screenshot_8.png)

<br>

### 🔹 8. Escrevendo no README no GitHub
![Fluxo](imagens/Screenshot_9.png)

<br>

### 🔹 10. OpenConnectors 
Vamos realizar o teste de conexão
![Fluxo](imagens/Screenshot_10.png)

<br>

### 🔹 11. OpenConnectors procurar files
Vamos expandir files
![Fluxo](imagens/Screenshot_11.png)

<br>

### 🔹 12. OpenConnectors 
Vamos anotar as credenciais para realizar o teste de conexão dentro do CPI
![Fluxo](imagens/Screenshot_12.png)

<br>

### 🔹 13. Credenciais do  OpenConnectors para o Github
Vamos usar as três conexões ("Authorization","Organization" e "Element" )
![Fluxo](imagens/Screenshot_13.png)

<br>

### 🔹 14. Com as Credenciais do  OpenConnectors para o Github anotadas
Três conexões ("Authorization","Organization" e "Element" )
![Fluxo](imagens/Screenshot_14.png)

<br>

### 🔹 15. Manage Security 
![Fluxo](imagens/Screenshot_15.png)

<br>

### 🔹 16. Adicionando o Manage Security
Vamos usar as três conexões ("**Authorization**","**Organization**" e "**Element**" )
![Fluxo](imagens/Screenshot_16.png)

<br>

### 🔹 17. Configuranando o Manage Security
Selecionar o Type: **OpenConnectors**
Vamos usar as três conexões ("**Authorization**","**Organization**" e "**Element**" )
![Fluxo](imagens/Screenshot_17.png)

<br>

### 🔹 18. Adicionando o Package
![Fluxo](imagens/Screenshot_18.png)

<br>

### 🔹 19. Criação do Package
![Fluxo](imagens/Screenshot_19.png)

Nome do Package:
```
ZPKG_IntegrationGitHub_OpenConnectors
```
![Fluxo](imagens/Screenshot_19.png)

<br> 

### 🔹 20. Adição do Artefato iFlow
![Fluxo](imagens/Screenshot_20.png)

<br>

### 🔹 21. Nome do iFlow:
```
IFL_IntegrationGitHub_OpenConnectors
```

![Fluxo](imagens/Screenshot_21.png)

<br>

### 🔹 22. Adicionando o Adapter
![Fluxo](imagens/Screenshot_22.png)

<br>

### 🔹 23. Configuração do Adapter HTTPS (Sender)


| Parâmetro    | Valor            |
|--------------|----------------- |
| Address      | /github          |
| Method       | GET              |
| Content-Type | application/json |

![Fluxo](imagens/Screenshot_23.png)

<br>


### 🔹 24. Adicionando o Request-Reply
![Fluxo](imagens/Screenshot_24.png)

<br>

### 🔹 25. Adicionando o Adapter 
**OpenConnectors**
![Fluxo](imagens/Screenshot_25.png)

<br>

### 🔹 26. Request-Reply – Consulta APIs Externas

### 🗺️ Maps API →

| Parâmetro                     | Valor                                                                       | 
| ----------------------------- | --------------------------------------------------------------------------- |
| Base URL                      | https://api.openconnectors.trial.us10.ext.hana.ondemand.com/elements/api-v2 |
| Credential Name               | OpenConnectors                                                              | 
| Resource                      | /files?path=README.md                                                       |
| Method                        | GET                                                                         |
| Request Format                | JSON                                                                        |
| Response Format               | JSON                                                                        |
| Query Parameters for Resource |                                                               |
| Timeoout (in ms)              | 60000                                                         |

![Fluxo](imagens/Screenshot_26.png)

<br>
 
### 🔹 27. Postman

## 📡 Testando com Postman

### 🎯 Payload
![Fluxo](imagens/Screenshot_27.png)

<br>





## 🔐 Segurança & Boas Práticas
⚠️ Importante: Este repositório é para fins educacionais e de demonstração.

### 🔒 Recomendações para Produção
