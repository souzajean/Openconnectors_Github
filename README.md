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
</p>
