# Mastering LLM Security

Open courseware on LLM Security and AI Reliability — OWASP LLM Top 10, guardrails, monitoring, red teaming and governance · Gemini API · Python

![Python](https://img.shields.io/badge/Python-3.10+-blue?style=flat-square&logo=python)
![Gemini](https://img.shields.io/badge/Gemini_API-2.5+-orange?style=flat-square&logo=google)
![License](https://img.shields.io/badge/License-MIT-green?style=flat-square)
![FIAP](https://img.shields.io/badge/FIAP-MBA_IA-red?style=flat-square)

---

## O que você vai aprender

- Identificar os principais vetores de ataque contra LLMs (OWASP LLM Top 10)
- Implementar guardrails em múltiplas camadas: regex, política de escopo e LLM-as-Judge
- Gerar e interpretar logs estruturados de segurança em JSON
- Executar suítes de testes automatizados e calcular métricas (precisão, recall, F1)
- Aplicar técnicas de red teaming e evasão para testar seus próprios controles
- Conectar os conceitos ao mundo real: LGPD, EU AI Act, PL 2338/2023

## Pré-requisitos

| Tópico | Nível |
|---|---|
| Python | Intermediário |
| APIs REST / JSON | Básico |
| Conceitos de Machine Learning | Básico |
| Conta Google (AI Studio) | Necessário (gratuito) |

---

## Conteúdo

| # | Notebook | Tópicos | OWASP Ref |
|---|---|---|---|
| 01 | `Aula1_Security/llm_security_gemini_ptbr.ipynb` | Assistente vulnerável, prompt injection, extração de PII, guardrails em camadas, logging estruturado, métricas de segurança | LLM01, LLM06, LLM08 |

> Novas aulas serão adicionadas ao longo do semestre.

---

## Arquitetura dos Guardrails

```
┌─────────────────────────────────────────────────────────────┐
│                    APLICAÇÃO COM LLM                        │
│                                                             │
│  INPUT            GUARDRAILS              OUTPUT            │
│  ───────      ─────────────────      ────────────           │
│  Usuário  ──► Classificador    ──►   Gemini API  ──► Resp.  │
│           ──► Padrões banidos  ──►   (se seguro)            │
│           ──► Política escopo  ──►   Bloqueio    ──► Aviso  │
│                    │                      │                 │
│                    ▼                      ▼                 │
│               ┌─────────┐          ┌──────────┐            │
│               │  LOGS   │          │ MÉTRICAS │            │
│               │  JSON   │          │          │            │
│               └─────────┘          └──────────┘            │
└─────────────────────────────────────────────────────────────┘
```

---

## Mapeamento OWASP LLM Top 10 (2025)

| # | Vulnerabilidade | Coberta neste curso |
|---|---|---|
| LLM01 | Prompt Injection | ✅ Aula 1 |
| LLM02 | Insecure Output Handling | ✅ Aula 1 |
| LLM03 | Training Data Poisoning | ⚠️ Conceitual |
| LLM04 | Model Denial of Service | ⚠️ Conceitual |
| LLM05 | Supply Chain Vulnerabilities | 🔜 Em breve |
| LLM06 | Sensitive Information Disclosure | ✅ Aula 1 |
| LLM07 | Insecure Plugin Design | 🔜 Em breve |
| LLM08 | Excessive Agency | ✅ Aula 1 |
| LLM09 | Overreliance | ✅ Aula 1 |
| LLM10 | Model Theft | ⚠️ Conceitual |

---

## Como começar

**Opção 1 — Google Colab (recomendado)**

Abra qualquer notebook diretamente no GitHub e clique em **Open in Colab** no topo do arquivo.

**Opção 2 — Local**

```bash
git clone https://github.com/ahirtonlopes/Mastering-LLM-Security.git
cd Mastering-LLM-Security
python -m venv .venv && source .venv/bin/activate
pip install google-genai jupyter
jupyter notebook
```

**API Key (gratuita):**
1. Acesse [aistudio.google.com](https://aistudio.google.com)
2. Clique em **Get API key → Create API key**
3. No Colab: adicione como secret com o nome `GEMINI_API_KEY`

---

## Referências

- [OWASP Top 10 for LLM Applications 2025](https://owasp.org/www-project-top-10-for-large-language-model-applications/)
- [Google AI Safety](https://ai.google/responsibility/safety/)
- [NIST AI Risk Management Framework](https://www.nist.gov/system/files/documents/2023/01/26/AI%20RMF%201.0.pdf)
- [PL 2338/2023 — Marco Regulatório de IA no Brasil](https://www.camara.leg.br/proposicoesWeb/fichadetramitacao?idProposicao=2384425)

---

## Autor

**Prof. Dr. Ahirton Lopes** · [LinkedIn](https://linkedin.com/in/ahirtonlopes) · [Google Scholar](https://scholar.google.com/citations?user=1SQDVrwAAAAJ)

MBA em Inteligência Artificial — FIAP | Disciplina: Segurança e Confiabilidade em Sistemas de IA

Contribuições são bem-vindas — abra uma issue ou envie um pull request.

## Licença

[MIT](LICENSE)
