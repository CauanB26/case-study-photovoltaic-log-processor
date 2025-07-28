[PT-BR] Para a versão em português deste documento, role até o final da página.

---

# Optimized Report Generator for PV Plant Logs

![Python](https://img.shields.io/badge/Python-3.x-blue.svg?style=for-the-badge&logo=python)
![Tkinter](https://img.shields.io/badge/Tkinter-GUI-orange.svg?style=for-the-badge&logo=python)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Processing-green.svg?style=for-the-badge&logo=pandas)
![Threads](https://img.shields.io/badge/Architecture-Multi--Threading-informational.svg?style=for-the-badge)

> **⚠️ Confidentiality Note:** This is a case study of a proprietary project. Sensitive details such as IPs, FTP access credentials, and plant data have been omitted for security and confidentiality reasons.

---

### 🎯 Project Goal

The objective of this project was to develop a robust desktop application to completely automate the process of downloading, processing, and consolidating log data from photovoltaic plants. The tool was designed to replace a slow and error-prone manual process, serving as a centralized solution for report generation.

---

### 📈 The Scenario: A Daily Operational Challenge

The manual consolidation of log data from multiple photovoltaic plants was an inefficient and complex process. The task involved:

* **Manual connection** to multiple FTP servers.
* **Navigation through complex folder structures** to locate the correct files for a specific period.
* **Downloading hundreds of individual `.csv` files**.
* **Manual processing and consolidation** of the data, a repetitive task with a high risk of human error.

This workflow consumed significant time and made large-scale data analysis difficult.

---

### ✨ The Solution: A Desktop Application with Python

To solve this problem, I developed a complete application with a graphical user interface (GUI) that automates and optimizes the entire process. The tool was built with the following technical features:

* **✅ Complete Graphical User Interface with `Tkinter`:**
    * I developed a GUI that allows the user to build a report queue by intuitively selecting plants and time periods. It is possible to manage the queue, remove tasks, or clear the entire list before processing.

* **✅ Parallel Architecture with Multi-Threading:**
    * The application uses a pool of `threads` to process multiple plants simultaneously, which drastically accelerates the total processing time for a batch and keeps the graphical interface always responsive, displaying the status in real-time without ever freezing.

* **✅ Intelligent and "On-Demand" Download via FTP:**
    * The tool implements a recursive search logic to map the directory structure on the FTP server. It then filters and selectively downloads only the minimum set of log files required for the requested period, optimizing network usage.

* **✅ Data Treatment and Enrichment with `Pandas`:**
    * The core of the application not only downloads the data but also performs a deep treatment to ensure the quality of the final report:
        * **Cleaning and Correction:** Invalid or corrupt values are discarded. Numerical sensor data is treated so that negative values (physically impossible for many measurements) are set to zero, and decimal precision is standardized through rounding.
        * **Enrichment with Quality Metrics:** The final report is enriched with two crucial analysis columns: `Quality (%)`, which measures the presence of a datalogger signal over time, and `Integrity (%)`, which measures the percentage of sensor data that was effectively filled.

* **✅ Intelligent Failure Recovery:**
    * A feature that allows the user to select a previously processed batch. The program reads the log file from that execution, identifies all tasks that resulted in a "Critical Failure," and automatically adds them to the current queue for a new attempt.

---

### 🚀 Results and Impact

The implementation of this tool transformed a manual and time-consuming process into an automated, fast, and reliable workflow.

| Area | Before Automation | After Automation |
| :--- | :--- | :--- |
| **Process** | Manual, sequential, and dependent on third parties | Automated, parallel, and self-contained |
| **Execution Time**| **~3 days per plant** (including request and collection) | **~15 minutes for the complete batch** of all plants |
| **Data Quality** | Raw, noisy data with gaps | Treated, clean, continuous data enriched with metadata |
| **Reliability** | High risk of copy and consolidation errors | Generation of consistent reports with failure handling |

The main result was the transformation of an analysis cycle that took days into a process executed in minutes, delivering not only speed but also a higher quality data product.

---

### 💡 Skills and Competencies Demonstrated

* **Desktop Software Development:** Building a standalone application with `Tkinter`.
* **Concurrent Software Architecture:** Designing and implementing a multi-threaded system for parallel processing, using `threading` and `queue` for safe communication.
* **Network Communication:** Using the `ftplib` library to interact with FTP servers, navigate remote directories, and transfer files.
* **Data Engineering:** Implementing an ETL (Extract, Transform, Load) pipeline with `Pandas` and `NumPy` to read, clean, group, format, and enrich large volumes of time-series data.
* **UI/UX Design:** Creating a functional interface focused on user experience, including real-time feedback and error recovery features.


&nbsp;
&nbsp;

---
---
&nbsp;
&nbsp;

## **Versão em Português**

---


# Gerador de Relatórios Otimizado para Logs de UFV

![Python](https://img.shields.io/badge/Python-3.x-blue.svg?style=for-the-badge&logo=python)
![Tkinter](https://img.shields.io/badge/Tkinter-GUI-orange.svg?style=for-the-badge&logo=python)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Processing-green.svg?style=for-the-badge&logo=pandas)
![Threads](https://img.shields.io/badge/Architecture-Multi--Threading-informational.svg?style=for-the-badge)

> **⚠️ Nota de Confidencialidade:** Este é um case study de um projeto proprietário. Detalhes sensíveis como IPs, credenciais de acesso FTP e os dados das usinas foram omitidos por questões de segurança e confidencialidade.

---

### 🎯 Objetivo do Projeto

O objetivo deste projeto foi desenvolver uma aplicação de desktop robusta para automatizar completamente o processo de download, processamento e consolidação de dados de log de usinas fotovoltaicas. A ferramenta foi projetada para substituir um processo manual lento e propenso a erros, servindo como uma solução centralizada para a geração de relatórios.

---

### 📈 O Cenário: Um Desafio Operacional Diário

A consolidação manual de dados de log de múltiplas usinas fotovoltaicas era um processo ineficiente e complexo. A tarefa envolvia:

* **Conexão manual** a múltiplos servidores FTP.
* **Navegação em estruturas de pastas complexas** para localizar os arquivos corretos para um determinado período.
* **Download de centenas de arquivos** `.csv` individuais.
* **Processamento e consolidação manual** dos dados, uma tarefa repetitiva e com alto risco de erro humano.

Este fluxo de trabalho consumia um tempo significativo e dificultava a análise de dados em larga escala.

---

### ✨ A Solução: Uma Aplicação Desktop com Python

Para resolver este problema, desenvolvi uma aplicação completa com interface gráfica (GUI) que automatiza e otimiza todo o processo. A ferramenta foi construída com os seguintes recursos técnicos:

* **✅ Interface Gráfica Completa com `Tkinter`:**
    * Desenvolvi uma GUI que permite ao usuário construir uma fila de relatórios, selecionando usinas e períodos de forma intuitiva. É possível gerenciar a fila, remover tarefas ou limpar a lista antes do processamento.

* **✅ Arquitetura Paralela com Multi-Threading:**
    * A aplicação utiliza um pool de `threads` para processar várias usinas simultaneamente, o que acelera drasticamente o tempo total de processamento de um lote e mantém a interface gráfica sempre responsiva, exibindo o status em tempo real sem nunca congelar.

* **✅ Download Inteligente e "On-Demand" via FTP:**
    * A ferramenta implementa uma lógica de busca recursiva para mapear a estrutura de diretórios no servidor FTP. Ela então filtra e baixa seletivamente apenas o conjunto mínimo de arquivos de log necessários para o período solicitado, otimizando o uso da rede.

* **✅ Tratamento e Enriquecimento de Dados com `Pandas`:**
    * O núcleo da aplicação não apenas baixa os dados, mas realiza um tratamento profundo para garantir a qualidade do relatório final:
        * **Limpeza e Correção:** Valores inválidos ou corrompidos são descartados. Dados numéricos de sensores são tratados para que valores negativos (fisicamente impossíveis para muitas medições) sejam zerados, e a precisão decimal é padronizada através de arredondamento.
        * **Enriquecimento com Métricas de Qualidade:** O relatório final é enriquecido com duas colunas de análise cruciais: `Qualidade (%)`, que mede a presença de sinal do datalogger no tempo, e `Integridade (%)`, que mede a porcentagem de dados de sensores efetivamente preenchida.

* **✅ Recuperação Inteligente de Falhas:**
    * Uma funcionalidade que permite ao usuário selecionar um lote processado anteriormente. O programa lê o arquivo de log daquela execução, identifica todas as tarefas que resultaram em "Falha Crítica" e as adiciona automaticamente à fila atual para uma nova tentativa.

---

### 🚀 Resultados e Impacto

A implementação desta ferramenta transformou um processo manual e demorado em um fluxo de trabalho automatizado, rápido e confiável.

| Área | Antes da Automação | Depois da Automação |
| :--- | :--- | :--- |
| **Processo** | Manual, sequencial e dependente de terceiros | Automatizado, paralelo e autocontido |
| **Tempo de Execução**| **~3 dias por usina** (incluindo solicitação e coleta) | **~15 minutos para o lote completo** de todas as usinas |
| **Qualidade do Dado** | Dado bruto, ruidoso e com lacunas | Dado tratado, limpo, contínuo e enriquecido com metadados |
| **Confiabilidade** | Alto risco de erros de cópia e consolidação | Geração de relatórios consistentes com tratamento de falhas |

O principal resultado foi a transformação de um ciclo de análise que levava dias em um processo executado em minutos, entregando não apenas velocidade, mas um produto de dados de qualidade superior.

---

### 💡 Habilidades e Competências Demonstradas

* **Desenvolvimento de Software Desktop:** Construção de uma aplicação `standalone` com `Tkinter`.
* **Arquitetura de Software Concorrente:** Design e implementação de um sistema multi-threaded para processamento paralelo, utilizando `threading` e `queue` para comunicação segura.
* **Comunicação de Rede:** Uso da biblioteca `ftplib` para interagir com servidores FTP, navegar em diretórios remotos e transferir arquivos.
* **Engenharia de Dados:** Implementação de um pipeline de ETL (Extração, Transformação, Carga) com `Pandas` e `NumPy` para ler, limpar, agrupar, formatar e enriquecer grandes volumes de dados de séries temporais.
* **Design de UI/UX:** Criação de uma interface funcional com foco na experiência do usuário e funcionalidades para recuperação de erros.
