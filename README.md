# Mastering LLM Security

Material aberto de **Segurança e Confiabilidade em Sistemas de IA**: OWASP Top 10 para LLMs, guardrails, monitoramento e red teaming, com a API do Gemini e Python.

![Python](https://img.shields.io/badge/Python-3.10+-blue?style=flat-square&logo=python)
![Gemini](https://img.shields.io/badge/Gemini_API-AI_Studio-orange?style=flat-square&logo=google)
![FIAP](https://img.shields.io/badge/FIAP-MBA_IA-red?style=flat-square)

---

## O que você vai aprender

- Identificar os principais vetores de ataque contra LLMs e agentes (OWASP Top 10 for LLM Applications, edição 2026)
- Construir guardrails em camadas: regex, política de escopo e LLM-as-Judge
- Proteger agentes com ferramentas: menor privilégio, limites, validação e aprovação humana (HITL)
- Registrar traces, observations e scores de segurança, com um rastreador local em Python puro
- Medir a defesa: taxa de detecção, falsos positivos, taxa de sucesso do ataque (ASR) e ablação por camada
- Aplicar IA responsável: saída estruturada, PII, viés e fundamentação, e avaliar a segurança de agentes
- Conectar os conceitos à regulação: LGPD, EU AI Act e PL 2338/2023

## Pré-requisitos

| Tópico | Nível |
|---|---|
| Python | Intermediário |
| APIs REST / JSON | Básico |
| Conceitos de Machine Learning | Básico |
| Conta Google (AI Studio) | Necessário (camada gratuita) |

---

## Conteúdo

| Aula | Tema | Notebook | Abrir no Colab |
|---|---|---|---|
| 1 | Defender um assistente: ataques, guardrails de entrada e saída, métricas e agente com HITL | [`Aula1_Security/llm_security_gemini_ptbr.ipynb`](Aula1_Security/llm_security_gemini_ptbr.ipynb) | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ahirtonlopes/Mastering-LLM-Security/blob/main/Aula1_Security/llm_security_gemini_ptbr.ipynb) |
| 2 | Observar e atacar a defesa: traces e scores, OWASP 2026 na prática e red teaming automatizado | [`Aula2_Security/llm_security_monitoring_ptbr.ipynb`](Aula2_Security/llm_security_monitoring_ptbr.ipynb) | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ahirtonlopes/Mastering-LLM-Security/blob/main/Aula2_Security/llm_security_monitoring_ptbr.ipynb) |
| 3 | IA Responsável e guardrails em agentes: saída estruturada, PII, viés, fundamentação, harness e contexto, Model Armor (opcional) e avaliação de segurança de agentes | [`Aula3_Security/responsible_ai_guardrails_ptbr.ipynb`](Aula3_Security/responsible_ai_guardrails_ptbr.ipynb) | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ahirtonlopes/Mastering-LLM-Security/blob/main/Aula3_Security/responsible_ai_guardrails_ptbr.ipynb) |

> A Aula 2 retoma o assistente da Aula 1 e a Aula 3 retoma o mesmo cenário (TechCorp). Rode as aulas em ordem. A Seção 7 da Aula 3 (Model Armor) é opcional e exige um projeto no Google Cloud. Novas aulas serão adicionadas ao longo do semestre.

---

## OWASP Top 10 for LLM Applications (2026)

| # | Vulnerabilidade | Onde aparece |
|---|---|---|
| LLM01 | Prompt Injection | Aulas 1 e 2 |
| LLM02 | Sensitive Information Disclosure | Aulas 1 e 2 |
| LLM03 | Excessive Agency | Aulas 1 (agente com HITL), 2 e 3 (harness) |
| LLM04 | Supply Chain | Aula 3 (conceitual) |
| LLM05 | Data and Model Poisoning | Aula 3 (conceitual) |
| LLM06 | Unbounded Consumption | Aula 3 (conceitual; limite de passos na Seção 6) |
| LLM07 | Misinformation | Aula 3 (fundamentação, Seção 4) |
| LLM08 | Hidden Context Exposure | Aulas 1, 2 e 3 |
| LLM09 | Vector and Embedding Weaknesses | Aula 3 (conceitual; contexto na Seção 6) |
| LLM10 | Improper Output Handling | Aula 3 (saída estruturada e validação, Seção 1) |

Lista conferida em [genai.owasp.org](https://genai.owasp.org) (edição publicada em 04/08/2026).

---

## Como começar

**Opção 1: Google Colab (recomendado).** Clique no botão "Open in Colab" da tabela acima.

**Opção 2: local**

```bash
git clone https://github.com/ahirtonlopes/Mastering-LLM-Security.git
cd Mastering-LLM-Security
python -m venv .venv && source .venv/bin/activate
pip install google-genai jupyter
jupyter notebook
```

**Chave de API (gratuita):**
1. Acesse [aistudio.google.com](https://aistudio.google.com)
2. Clique em **Get API key → Create API key**
3. No Colab: adicione como secret com o nome `GEMINI_API_KEY`

Nunca grave a chave dentro do notebook.

---

## Referências

- [OWASP GenAI Security Project](https://genai.owasp.org)
- [Google Secure AI Framework (SAIF)](https://saif.google)
- [NIST AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework)
- [PL 2338/2023 - Marco Regulatório de IA no Brasil](https://www.camara.leg.br/proposicoesWeb/fichadetramitacao?idProposicao=2384425)

---

## Autor

**Prof. Dr. Ahirton Lopes** · [LinkedIn](https://linkedin.com/in/ahirtonlopes) · [Google Scholar](https://scholar.google.com/citations?user=1SQDVrwAAAAJ)

MBA em Inteligência Artificial, FIAP | Disciplina: Segurança e Confiabilidade em Sistemas de IA

Contribuições são bem-vindas: abra uma issue ou envie um pull request.
