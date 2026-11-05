# 📄 09 · Política de Segurança da Informação (PSI)

![ISO 27001](https://img.shields.io/badge/ISO_27001-Segurança_da_Informação-4A90D9?style=flat)
![NIST CSF](https://img.shields.io/badge/NIST-Cybersecurity_Framework-E74C3C?style=flat)

> A CloudFlux tinha oito projetos de GRC no bolso e nenhuma política formal publicada. Hora de colocar no papel.

| | |
|---|---|
| 🗂️ **Tipo** | Projeto simulado |
| 📚 **Referências** | ISO/IEC 27001 (seção 5.2 — política de segurança) · NIST Cybersecurity Framework |
| 📦 **Entregáveis** | Política de Segurança da Informação v1.0 |
| 🎯 **Público do documento** | Todos os colaboradores, prestadores de serviço e terceirizados da CloudFlux |

---

## 🏢 Cenário

A **CloudFlux** chegou em 2026 com oito projetos de GRC concluídos — matriz de risco, auditoria, change management, gestão de incidente, IAM e LGPD. Maturidade real. Mas nenhuma política formal publicada.

Cada controle havia sido implementado, cada risco mapeado, mas sem um documento-mãe que formalizasse os princípios e as responsabilidades de segurança da informação da empresa.

🚨 **O gatilho:** o conselho aprovou em outubro a criação de um Programa de Segurança da Informação. A primeira entrega: a PSI, versão 1.0, para aprovação da diretoria.

📌 **Papel:** analista de GRC responsável por redigir o documento do zero.

---

## 📋 O documento

A PSI v1.0 cobre sete seções obrigatórias:

| Seção | Conteúdo |
|---|---|
| 1 · Objetivo e Escopo | O que a política formaliza, a quem se aplica e quais sistemas e dados abrange |
| 2 · Definições | Glossário dos termos usados no documento (CID, menor privilégio, LGPD, GRC, Política) |
| 3 · Princípios | Confidencialidade, Integridade, Disponibilidade, Menor privilégio, Conformidade com a LGPD, Resiliência e Responsabilidade compartilhada |
| 4 · Papéis e Responsabilidades | Alta Direção, TI e GRC, Jurídico, RH, Responsável de Segurança da Informação e Colaboradores |
| 5 · Diretrizes Gerais | Oito diretrizes de comportamento esperado de todos que se relacionam com a CloudFlux |
| 6 · Consequências por Descumprimento | Três níveis (advertência informal, formal e desligamento/medidas legais) com caráter orientativo |
| 7 · Vigência e Revisão | Vigência a partir de 13/10/2026, revisão anual ou por mudança relevante |

📄 [Acesse a PSI completa](./politica-seguranca-informacao-v1.0.pdf)

---

## ✅ O que este projeto demonstra

- Compreensão de que **ter o controle** e **ter o documento que exige o controle** são coisas diferentes — e que a segunda é o que sustenta a primeira juridicamente.
- Capacidade de redigir um **documento formal de governança** do zero, com linguagem aplicável e coerência interna.
- Entendimento de que política não é só sobre o que fazer, mas sobre **quem responde pelo quê** — a seção de papéis é onde a governança ganha dono.
- Distinção entre **política-mãe** (PSI) e **políticas derivadas** (classificação de dados, controle de acesso, senhas) — a PSI abre o guarda-chuva, não detalha cada tema.

## 🔜 Próximo nível

- 📂 **Política de Classificação de Dados:** derivada natural desta PSI, define como a CloudFlux categoriza e trata informações conforme sensibilidade.
- 🔊 **Programa de conscientização:** a seção 5 cita treinamentos como diretriz obrigatória — transformar isso em programa estruturado é o próximo passo lógico.
- ✍️ **Tom de voz:** a v1.0 usa linguagem formal genérica, apropriada para o documento inaugural. A v1.1 pode ancorar mais no contexto específico da CloudFlux como SaaS B2B.

## 🧵 Na série CloudFlux

- 📊 Os controles formalizados nesta política têm raiz nos oito projetos anteriores: o princípio de menor privilégio vem do [Keycloak (Projeto 05)](../05-gestao-de-acesso-keycloak/), a conformidade com a LGPD do [mapeamento de dados (Projeto 08)](../08-lgpd-mapeamento-ripd/), e a resiliência do incidente que a CloudFlux quase não conteve no [Projeto 04](../04-gestao-de-incidente-jira/).
- 🏗️ Esta PSI é o **documento-mãe do Programa de Segurança da Informação** da CloudFlux — tudo que veio antes era controle sem política; a partir daqui, a política existe para sustentar os controles.
