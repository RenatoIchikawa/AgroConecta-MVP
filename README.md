# 🌱 AgroConecta — Plataforma Inteligente para Agricultura Familiar

> **Eficiência energética, logística rural e assistência agronômica auditável para pequenos produtores, cooperativas e prefeituras.**

![ODS 2](https://img.shields.io/badge/ODS_2-Fome_Zero_e_Agricultura_Sustentável-DDA63A?style=for-the-badge)
![ODS 13](https://img.shields.io/badge/ODS_13-Ação_Contra_a_Mudança_do_Clima-3F7E44?style=for-the-badge)
![LGPD](https://img.shields.io/badge/Compliance-LGPD_Privacy_by_Design-059669?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-MVP_Operacional-10B981?style=for-the-badge)

---

## 📋 Sobre o Projeto

O **AgroConecta** é uma plataforma **AgriTech e GovTech** desenvolvida na **FIAP** para solucionar os principais gargalos operacionais da agricultura familiar brasileira:

1. **Assimetria de Informação Comercial:** Pequenos produtores dependem de atravessadores por falta de acesso consolidado às cotações diárias de centrais de abastecimento (`CEAGESP` e `CONAB`).
2. **Ineficiência Energética no Campo:** Sistemas de irrigação e bombeamento operam sem monitoramento de umidade do solo ou aproveitamento de tarifas horárias reduzidas (`ANEEL`).
3. **Perdas Logísticas Pós-Colheita:** Falta de consolidação de cargas compartilhadas entre produtores cooperados e editais públicos (`PNAE` e `PAA`).
4. **Risco de Desinformação Técnica:** Ferramentas genéricas de IA sofrem com alucinações, podendo recomendar dosagens ou manejos incorretos que comprometem a lavoura.
5. **Privacidade e Proteção de Dados (LGPD):** Necessidade de proteger dados sensíveis do produtor rural (`CPF`, telefone, localização) desde a coleta.

---

## 🎯 Alinhamento com os Objetivos de Desenvolvimento Sustentável (ONU)

* **ODS 2 — Fome Zero e Agricultura Sustentável:** Redução de perdas pós-colheita, aumento da margem líquida do pequeno produtor e fortalecimento do abastecimento alimentar regional.
* **ODS 13 — Ação Contra a Mudança Global do Clima:** Otimização do consumo energético na irrigação (`kWh`), uso racional de defensivos agrícolas e redução de emissões de `CO₂` por meio de rotas logísticas consolidadas.

---

## 🖥️ Funcionalidades da Plataforma Web (`index.html`)

A interface web foi construída como uma aplicação **Single-File** responsiva, leve e sem necessidade de etapas complexas de compilação (*zero-build*), reunindo:

* **Painel Operacional Integrado:**
  * **Telemetria IoT em Tempo Real:** Simulação interativa de sensores físicos (`ESP32`) monitorando umidade do solo, consumo de bombeamento e microclima (*Eco-Irrigação*, *Alerta Solo Seco* e *Geração Solar*).
  * **Cotações Agrícolas Automatizadas (RPA):** Tabela filtrável com cotações de hortaliças, raízes e grãos sincronizadas de fontes oficiais (`CEAGESP` / `CONAB`).
  * **Inteligência Regional (Databricks Lakehouse):** Indicadores comparativos de economia energética e aproveitamento de frete compartilhado por polo agrícola.
* **Assistente Técnico Agrícola (IA Generativa RAG Auditável):**
  * Consultas fundamentadas exclusivamente em resoluções da **ANEEL** e manuais da **EMBRAPA / MAPA**.
  * **Medidor de Groundedness Score:** Exibe o índice de fidelidade à fonte oficial (limiar mínimo de `85,0%`) e bloqueia consultas fora do escopo (*"Não consta"*).
  * **Proteção LGPD Nativa:** Detecta e mascara automaticamente `CPF` e `telefone` digitados pelo usuário antes de qualquer processamento.
* **Diagnóstico Fitossanitário por Imagem (Visão Computacional):**
  * Inspeção visual interativa de amostras foliares (*Requeima*, *Minadora-das-folhas*, *Deficiência de Nitrogênio* e *Folha Saudável*) com alternância de *Bounding Boxes* e laudo agronômico.
* **Arquitetura dos 7 Pilares & Pitch Deck Executivo:**
  * Vitrine técnica das 7 disciplinas integradas com modal de demonstração em vídeo.
  * Apresentador interativo de **10 slides** com suporte a teclado (`←` / `→`), gestos *touch* e modo tela cheia.

---

## 🏗️ Arquitetura e Integração das 7 Disciplinas

| # | Disciplina | Papel no Ecossistema AgroConecta | Stack & Entregáveis |
| :- | :--- | :--- | :--- |
| **01** | **Generative AI for Engineering** | Assistente técnico rural auditável com bloqueio anti-alucinação e redação LGPD. | `FastAPI`, `Ollama` (`Llama 3.2 1B`), `intfloat/multilingual-e5-small`, RAG sobre base ANEEL/EMBRAPA (`87%` acurácia). |
| **02** | **Big Data Architecture & Data Integration** | Pipeline analítico para cruzamento de dados climáticos, energéticos e de mercado. | `Databricks Lakehouse` em arquitetura Medallion (`Bronze`, `Silver` e `Gold`). |
| **03** | **Business Intelligence & Startup Development** | Viabilidade econômica, modelagem financeira e dashboards de decisão. | Modelo **B2B2C** para cooperativas e prefeituras (`PNAE`/`PAA`) com **break-even no 4º mês**. |
| **04** | **Applied Computer Vision** | Detecção precoce de pragas, doenças e carências nutricionais em folhas. | Redes neurais convolucionais / `YOLOv8` com detecção por *bounding boxes*. |
| **05** | **Robotic Process Automation (RPA)** | Extração automatizada de preços agrícolas públicos e editais municipais. | Robôs RPA integrados aos portais `CEAGESP` e `CONAB`. |
| **06** | **Secure DevOps Tools & Cloud Computing** | Infraestrutura segura em nuvem, observabilidade e automação de deploy. | Esteiras `CI/CD`, criptografia `TLS 1.3`, controle de acesso e governança LGPD. |
| **07** | **Project-Based Maker Lab (IoT)** | Monitoramento físico de solo, temperatura e consumo elétrico na irrigação. | Microcontroladores `ESP32`, sensores capacitivos de umidade e automação de bombeamento. |

---

## 🛠️ Tecnologias Utilizadas na Interface Web

* **HTML5 Semântico**
* **Tailwind CSS** (via CDN com paleta customizada Agro-Tech e tipografia `Inter` + `Plus Jakarta Sans`)
* **Lucide Icons** (iconografia vetorial leve)
* **JavaScript Vanilla (ES6+)** (gerenciamento de estado, filtros dinâmicos, regex LGPD, SVG vetorial de diagnóstico e navegação do Pitch Deck)

---

## 🚀 Como Executar o Projeto

## Opção 1: Acesso Direto Online (Recomendado)

A plataforma está publicada e acessível diretamente pelo navegador, sem necessidade de instalação:

URL Pública: https://renatoichikawa.github.io/AgroConecta-MVP/

## Opção 2: Executar Localmente no Computador

### Pré-requisitos
Nenhum servidor complexo ou instalação de dependências (`Node.js` ou `npm`) é obrigatória para executar a aplicação web. Você precisa apenas de:
* Um navegador web moderno (**Google Chrome**, **Microsoft Edge**, **Firefox** ou **Safari**).
* *(Opcional)* **VS Code** com a extensão **Live Server** ou **Python 3** para servir localmente via HTTP.

### Passo a Passo para Rodar Localmente

1. **Clone este repositório (ou baixe e extraia os arquivos):**
   ```bash
   git clone https://github.com/seu-usuario/AgroConecta.git
   cd AgroConecta
   ```

2. **Abra a aplicação:**
   * **Opção 1 (Direto no navegador):** Dê um duplo clique no arquivo `index.html`.
   * **Opção 2 (Via servidor local Python):**
     ```bash
     python -m http.server 8000
     ```
     Em seguida, acesse `http://localhost:8000` no navegador.
   * **Opção 3 (VS Code):** Clique com o botão direito em `index.html` e selecione **"Open with Live Server"**.

## 📁 Estrutura de Arquivos

```text
AgroConecta/
├── index.html      # Aplicação web completa (Interface, Painel Operacional, Chat RAG, Visão Computacional e Pitch Deck)
└── README.md       # Documentação técnica e guia de execução do projeto
```

---

## 👥 Equipe Desenvolvedora — FIAP

* **Bernardo Rocha**
* **Eric Rodrigues**
* **Renato Izumi**

---

## 📄 Licença e Governança

Projeto desenvolvido para fins acadêmicos e de inovação tecnológica na **FIAP**, estruturado sob boas práticas de **Privacy by Design** e em conformidade com a **Lei Geral de Proteção de Dados (Lei nº 13.709/2018)**.
