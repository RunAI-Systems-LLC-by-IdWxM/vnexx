# vNEXX — Sistema de Automação Corporativa Multimodal / Multimodal Corporate Automation Platform

Este repositório contém a documentação técnica e arquitetural de referência para o **vNEXX**, conforme registrado sob o pedido nacional de patente de invenção.

---

## 🇧🇷 PORTUGUÊS

### 📑 Dados do Registro da Patente
* **Número do Processo:** BR 10 2025 019674 3
* **Natureza:** Patente de Invenção (PI)
* **Data do Depósito:** 15/09/2025
* **Número da Petição:** 870250083091
* **Depositante:** RUNAI SYSTEMS LIMITED LIABILITY COMPANY
* **Jurisdição do Depositante:** Nº 16192 Coastal Highway, Condado de Sussex, Lewes, Delaware, 19958 - Estados Unidos da América
* **EIN Number:** 61.2249605

### 📝 Resumo da Invenção
A presente invenção refere-se ao sistema vNEXX, uma plataforma modular de automação corporativa baseada em inteligência artificial, com foco em interação por voz em tempo real, segurança multifatorial e integração de dados heterogêneos. O login inicial é feito com senha, mas o sistema executa rotação automática diária de credenciais, eliminando a necessidade de novas senhas pelo usuário através da integração ao RunID. O TGhosT constitui o chatbot *off-label* do vNEXX; após a autenticação, cada cliente cria e personaliza seu próprio assistente, definindo cores, layout e comportamento, mantendo identidade própria, enquanto a identidade matriz permanece fixa no rodapé como *Powered by RunAI Systems LLC*. 

O sistema resolve a fragmentação entre ERP, BI, automação e identidade digital. A arquitetura é estruturada em camadas independentes e escaláveis, *multi-tenant*, com isolamento seguro. A entrada é multimodal (voz, texto, gestos), priorizando a voz como núcleo central da inovação. O motor de intenções interpreta objetivos em linguagem natural e converte-os em um grafo acíclico de tarefas (DAG). Os dados são ingeridos em tempo real e organizados em um *data lakehouse*, garantindo consistência e análises avançadas com simulações *what-if*.

### 🌐 Campo da Técnica e Problemas Resolvidos
A invenção situa-se no campo de sistemas de informação corporativos com interação humano-máquina por voz, orquestração transacional e segurança de identidade. Ela resolve:
1.  **Fragmentação operacional:** Elimina a dependência de tarefas repetitivas manuais entre sistemas isolados (ERP, CRM, BI).
2.  **Alta latência de dados:** Substitui o processamento em lote por um plano de dados unificado em tempo real.
3.  **Complexidade de interface:** Remove a necessidade de telas densas e treinamento técnico por meio de comandos de voz fluentes e agnósticos.
4.  **Vulnerabilidades de credenciais:** Mitiga o risco de senhas estáticas através de rotação automatizada em cofre de segredos.

---

### 🏗️ Arquitetura Detalhada do Sistema

#### 1. Camada de Identidade — RunID
* Mecanismo proprietário de autenticação contínua.
* Rotação automática diária de credenciais criptográficas.
* Múltiplos fatores baseados em hardware validado (número de série de celular, headset ou computador).
* Sessões assinadas de curta duração baseadas no princípio de privilégio mínimo.
* Logs de autenticação imutáveis com assinatura e *hash* de tempo.

#### 2. Camada Conversacional — TGhosT
* Interface primária focada em voz natural (aproximadamente 90% das interações ocorrem por fala fluente).
* Reconhecimento dinâmico adaptado a sotaques, contextos regionais e ajuste de tom do usuário.
* Extração de parâmetros e desambiguação sintática.
* Personalização completa de interface (*off-label*) por cliente com rodapé de origem institucional obrigatório.

#### 3. Camada de Orquestração
* Conversão de intenções textuais/vocais em Grafos Acíclicos Dirigidos (DAG).
* Executores especializados com escopo restrito e tokens efêmeros (*just-in-time*).
* Regras de quórum e validação de limites de risco/custo antes de ações críticas.
* Geração de protocolo com ID único e armazenamento em trilha de auditoria imutável.
* *Fallback* humano automático para cenários com nível de confiança abaixo do limiar parametrizado.

#### 4. Camada de Dados
* Ingestão contínua em tempo real (SQL, CDC e *streaming* de eventos).
* Arquitetura de *Data Lakehouse* com versionamento e particionamento temporal.
* Modelos preditivos integrados para análises estatísticas e simulações de cenário (*what-if*).

#### 5. Camada de Apresentação
* Painéis interativos dinâmicos com recursos de *drill-down* e relatórios exportáveis (PDF, Excel, Word).
* Layout adaptável por voz (ex: comandos para reposicionamento de menus e alteração de paletas).

---

### ⚙️ Fluxo de Execução End-to-End
1.  **Acesso:** Usuário autentica-se via RunID com MFA por hardware e recebe uma sessão assinada.
2.  **Intenção:** O usuário emite um comando livre (ex: *"Mostrar fluxo de caixa por unidade nos últimos 90 dias e sinalizar anomalias"*).
3.  **Interpretação:** O TGhosT extrai entidades e dimensões consultando o catálogo semântico.
4.  **Planejamento:** O sistema constrói o DAG correspondente à sequência de tarefas.
5.  **Execução:** Cada nó do grafo é processado via tokens efêmeros com checagem de privilégios.
6.  **Entrega:** O resultado é renderizado no painel visual ou sintetizado por voz, registrando o protocolo imutável na trilha de auditoria.

---

### 📜 Reivindicações da Patente (Corpo Oficial)

* **REIVINDICAÇÃO 1 (INDEPENDENTE):** Um sistema de automação corporativa multimodal, denominado vNEXX, caracterizado por integrar inteligência artificial, autenticação multifatorial, motor de intenções semânticas e orquestração de dados em tempo real, permitindo que operações corporativas sejam realizadas predominantemente por comandos de voz em linguagem natural, incluindo funções de ERP, BI, CRM, automação de processos e geração de relatórios.
* **REIVINDICAÇÃO 2 (INDEPENDENTE):** Um método de autenticação digital, denominado RunID, caracterizado por combinar fatores de validação baseados em dispositivos físicos registrados, incluindo número de série de celular, headset e computador, em conjunto com rotação automática de credenciais armazenadas em cofre de segredos, garantindo acesso contínuo e seguro ao sistema vNEXX.
* **REIVINDICAÇÃO 3 (INDEPENDENTE):** Um chatbot corporativo off-label, denominado TGhosT, caracterizado por permitir que cada cliente personalize identidade visual, cores, layout e comportamento, permanecendo fixo um selo institucional no rodapé para assegurar origem e conformidade, e por interagir em linguagem natural predominantemente por voz, adaptando-se a sotaques, idiomas e contextos regionais.
* **REIVINDICAÇÃO 4 (DEPENDENTE DA REIVINDICAÇÃO 1):** O sistema de acordo com a reivindicação 1, no qual os comandos de voz são convertidos em grafos de tarefas (DAG) validados por políticas de acesso, perfis de usuário e trilhas de auditoria imutáveis.
* **REIVINDICAÇÃO 5 (DEPENDENTE DA REIVINDICAÇÃO 1):** O sistema de acordo com a reivindicação 1, no qual dados ingeridos em tempo real são organizados em arquitetura de data lakehouse, suportando consultas SQL, CDC, streaming, análises preditivas e simulações.
* **REIVINDICAÇÃO 6 (DEPENDENTE DA REIVINDICAÇÃO 1):** O sistema de acordo com a reivindicação 1, no qual resultados são entregues em dashboards interativos, narrativas automáticas em voz ou relatórios exportáveis em PDF, Excel ou Word.
* **REIVINDICAÇÃO 7 (DEPENDENTE DA REIVINDICAÇÃO 3):** O chatbot TGhosT, de acordo com a reivindicação 3, configurado para confirmar custos e impactos antes de executar ações críticas, acionando fallback humano em caso de ambiguidade.
* **REIVINDICAÇÃO 8 (DEPENDENTE DA REIVINDICAÇÃO 1):** O sistema de acordo com a reivindicação 1, em que módulos adicionais podem ser ativados sob demanda, incluindo financeiro, multi-bancos, reconciliação, previsões, estoque, logística, manutenção, redes sociais, gestão pessoal e integração com IoT e robótica.
* **REIVINDICAÇÃO 9 (DEPENDENTE DA REIVINDICAÇÃO 2):** O método de autenticação RunID, de acordo com a reivindicação 2, configurado para operar em conformidade com legislações distintas de proteção de dados, incluindo LGPD, GDPR e CCPA, aplicadas dinamicamente conforme a jurisdição do usuário.
* **REIVINDICAÇÃO 10 (DEPENDENTE DA REIVINDICAÇÃO 1):** O sistema de acordo com a reivindicação 1, caracterizado por arquitetura multi-tenant, com isolamento seguro entre clientes, segregação de ambientes e escalabilidade contínua sem interrupção do serviço.

---
---

## 🇺🇸 ENGLISH

### 📑 Patent Registration Data
* **Process Number:** BR 10 2025 019674 3
* **Nature:** Invention Patent (PI)
* **Filing Date:** September 15, 2025
* **Petition Number:** 870250083091
* **Applicant:** RUNAI SYSTEMS LIMITED LIABILITY COMPANY
* **Applicant Jurisdiction:** No. 16192 Coastal Highway, Sussex County, Lewes, Delaware, 19958 - United States of America
* **EIN Number:** 61.2249605

### 📝 Patent Abstract
The present invention relates to the vNEXX system, an artificial intelligence-powered modular corporate automation platform focused on real-time voice interaction, multi-factor security, and heterogeneous data integration. Initial login uses a password, but the system executes automatic daily credential rotation, eliminating the user's need for subsequent passwords through integration with RunID. TGhosT constitutes the off-label chatbot of vNEXX; after authentication, each client can create and customize their own assistant, defining colors, layout, and behavior while maintaining their brand identity, whereas the master identity remains fixed in the footer as *Powered by RunAI Systems LLC*.

The system resolves the operational fragmentation between ERP, BI, automation, and digital identity. The architecture is structured into independent, scalable, and multi-tenant layers with secure isolation. Input is multimodal (voice, text, gestures), prioritizing voice as the core innovation. The intent engine interprets natural language goals and converts them into a Directed Acyclic Graph (DAG) of tasks. Data is ingested in real time and organized into a data lakehouse, ensuring consistency and enabling advanced analytics with what-if simulations.

### 🌐 Field of the Technique & Solved Problems
This invention lies within the field of corporate information systems featuring human-machine voice interaction, transactional orchestration, and identity security. It solves:
1.  **Operational Fragmentation:** Eliminates dependence on manual, repetitive tasks across siloed systems (ERP, CRM, BI).
2.  **High Data Latency:** Replaces batch processing with a unified, real-time data plane.
3.  **Interface Complexity:** Removes the need for dense screens and technical training through fluid, NLP voice commands.
4.  **Credential Vulnerabilities:** Mitigates static password risks through automated secrets vault rotation.

---

### 🏗️ Detailed System Architecture

#### 1. Identity Layer — RunID
* Proprietary continuous authentication mechanism.
* Automatic daily rotation of cryptographic credentials.
* Multi-factor authentication based on validated hardware (phone, headset, or computer serial numbers).
* Short-lived signed sessions adhering to the principle of least privilege.
* Immutable authentication logs with cryptographic time-hash signatures.

#### 2. Conversational Layer — TGhosT
* Primary interface centered on natural voice interaction (approx. 90% of interactions).
* Dynamic speech recognition adapting to accents, regional contexts, and user tone adjustments.
* Parameter extraction and syntactic disambiguation.
* Complete off-label interface customization per tenant with a mandatory institutional footer.

#### 3. Orchestration Layer
* Conversion of text/voice intents into Directed Acyclic Graphs (DAG).
* Specialized task executors using restricted-scope, ephemeral (just-in-time) tokens.
* Quorum rules and risk/cost boundary validations prior to critical automated actions.
* Protocol generation with a unique ID stored in an immutable audit trail.
* Automatic human fallback for scenarios falling below the confidence threshold.

#### 4. Data Layer
* Continuous real-time ingestion via SQL, CDC, and event streaming.
* Data Lakehouse architecture with time-partitioning and versioning.
* Integrated predictive models for statistical analysis and what-if scenario simulations.

#### 5. Presentation Layer
* Dynamic interactive dashboards with drill-down capabilities and exportable reports (PDF, Excel, Word).
* Voice-adaptable layouts (e.g., verbal commands to move menus or swap color palettes).

---

### ⚙️ End-to-End Execution Flow
1.  **Access:** The user logs in via RunID using hardware-bound MFA and receives a signed session token.
2.  **Intent:** The user gives a natural language command (e.g., *"Show cash flow per business unit over the last 90 days and highlight anomalies"*).
3.  **Interpretation:** TGhosT extracts entities and dimensions by querying the semantic catalog.
4.  **Planning:** The system builds a corresponding DAG to map the task execution path.
5.  **Execution:** Each graph node is processed using ephemeral tokens with strict privilege verification.
6.  **Delivery:** Results render on the visual dashboard or are synthesized via voice, logging the immutable execution protocol.

---

### 📜 Patent Claims (Official Body)

* **CLAIM 1 (INDEPENDENT):** A multimodal corporate automation system, denominated vNEXX, characterized by integrating artificial intelligence, multi-factor authentication, a semantic intent engine, and real-time data orchestration, allowing corporate operations to be performed predominantly through natural language voice commands, including ERP, BI, CRM, process automation, and report generation functionalities.
* **CLAIM 2 (INDEPENDENT):** A digital authentication method, denominated RunID, characterized by combining validation factors based on registered physical devices, including mobile phone, headset, and computer serial numbers, in conjunction with the automatic rotation of credentials stored within a secrets vault, ensuring continuous and secure access to the vNEXX system.
* **CLAIM 3 (INDEPENDENT):** An off-label corporate chatbot, denominated TGhosT, characterized by allowing each client to customize visual identity, colors, layout, and behavior, while keeping a fixed institutional footer badge to ensure origin and compliance, and by interacting in natural language predominantly through voice, adapting to accents, languages, and regional contexts.
* **CLAIM 4 (DEPENDENT ON CLAIM 1):** The system according to claim 1, wherein voice commands are converted into directed acyclic graphs (DAG) of tasks validated by access policies, user profiles, and immutable audit trails.
* **CLAIM 5 (DEPENDENT ON CLAIM 1):** The system according to claim 1, wherein data ingested in real time is organized into a data lakehouse architecture supporting SQL queries, CDC, streaming, predictive analytics, and simulations.
* **CLAIM 6 (DEPENDENT ON CLAIM 1):** The system according to claim 1, wherein results are delivered via interactive dashboards, automated voice narratives, or exportable reports in PDF, Excel, or Word formats.
* **CLAIM 7 (DEPENDENT ON CLAIM 3):** The chatbot TGhosT, according to claim 3, configured to confirm costs and impacts before executing critical actions, triggering a human fallback in case of ambiguity.
* **CLAIM 8 (DEPENDENT ON CLAIM 1):** The system according to claim 1, wherein additional modules can be activated on demand, including financial, multi-banking, reconciliation, forecasting, inventory, logistics, maintenance, social media automation, personal management, and IoT/robotics integration.
* **CLAIM 9 (DEPENDENT ON CLAIM 2):** The authentication method RunID, according to claim 2, configured to operate in compliance with distinct data protection legislations, including LGPD, GDPR, and CCPA, dynamically applied according to the user's jurisdiction.
* **CLAIM 10 (DEPENDENT ON CLAIM 1):** The system according to claim 1, characterized by a multi-tenant architecture with secure isolation between clients, environment segregation, and continuous scalability without service interruption.

---
<div align="center">
  <br>
  <b>Fundador & Inventor:</b> Wesley de Souza Macedo - IDWxM <br>
  <b>Site:</b> <a href="https://www.wesleysmacedo.com">www.wesleysmacedo.com</a> <br>
  <i>Inspirado em Kauê | Kauai | Liz</i>
  <br><br>
  <b>Powered by RunAI Systems Limited Liability Company.</b>
  <br><br>
</div>
