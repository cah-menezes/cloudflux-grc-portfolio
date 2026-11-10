# 🤝 10 · Gestão de Risco de Terceiros (TPRM)

![ISO 27001](https://img.shields.io/badge/ISO_27001-A.5.19_a_A.5.23-4A90D9?style=flat)
![NIST SP 800-161](https://img.shields.io/badge/NIST-SP_800--161-E74C3C?style=flat)
![LGPD](https://img.shields.io/badge/LGPD-Lei_13.709%2F2018-E74C3C?style=flat)

> A Nexaflow tinha ISO 27001, DPO e criptografia. Mas o certificado não cobria quem ia mexer nos dados da CloudFlux.

| | |
|---|---|
| 🗂️ **Tipo** | Projeto simulado |
| 📚 **Referências** | ISO/IEC 27001:2022 Anexo A (A.5.19 a A.5.23, relações com fornecedores) · NIST SP 800-161 (risco na cadeia de suprimentos) · LGPD art. 46 e seguintes · Resolução CD/ANPD nº 15/2024 |
| 📦 **Entregáveis** | Relatório de avaliação de risco de terceiros: classificação, questionário, lacunas, parecer, cláusulas contratuais e matriz de rastreabilidade |
| 🎯 **Público do documento** | Board, gestão de TI e Jurídico da CloudFlux |
| 🔒 **Classificação do documento** | Confidencial *(documento fictício)* |

> ⚠️ **Projeto de simulação.** CloudFlux, Nexaflow Sistemas, as pessoas citadas, as respostas do questionário e os dois pacotes de evidências são **fictícios**. Não representam nenhuma empresa real.

**Fornecedor:** Nexaflow Sistemas (ERP Financeiro) · **Elaborado por:** Carolina Menezes, Analista de GRC — CloudFlux · **Data:** 10/11/2026

---

## 🏢 Cenário

Com a [PSI (Projeto 09)](../09-politica-seguranca-informacao/) aprovada e publicada, a CloudFlux passou a exigir **avaliação de segurança antes de contratar fornecedores** com acesso a dados ou sistemas da empresa. O problema: esse processo nunca tinha sido formalizado.

Ao mesmo tempo, a gestão financeira em planilha não aguentava mais o crescimento. A área financeira pressionava por um ERP robusto, e a **Nexaflow Sistemas**, ERP SaaS de Campinas/SP com 13 anos de mercado, chegou como favorita depois de uma rodada de RFP interna. A integração seria via API REST, processando dados financeiros e de clientes (nome, CNPJ, valores de contrato) e, numa fase futura, dados de colaboradores pelo módulo de RH.

🚨 **O gatilho:** antes de assinar o contrato, o time de GRC precisava conduzir a **primeira avaliação formal de risco de fornecedor** da CloudFlux e emitir um parecer que fundamentasse a decisão.

📌 **Papel:** analista de GRC (nível júnior), responsável por toda a avaliação, da classificação do fornecedor até a minuta de cláusulas.

📌 **Escopo:** classificação de criticidade, due diligence de segurança, análise de lacunas, parecer de risco e cláusulas contratuais mínimas de segurança.

📌 **Fora do escopo:** risco financeiro ou reputacional do fornecedor, implementação técnica da integração, revisão jurídica completa do contrato e monitoramento pós-contratação.

---

## 🗓️ Como a avaliação foi conduzida

| Etapa | O que foi feito |
|---|---|
| 1 · Classificação | Critérios de criticidade aplicados à Nexaflow, que definiram a profundidade da avaliação |
| 2 · Questionário | Due diligence de segurança em 8 domínios, enviado ao fornecedor |
| 3 · Evidências | Pedido de comprovação das respostas. Os documentos chegaram em dois blocos: um aberto e outro sob **NDA** |
| 4 · Lacunas | Cruzamento entre o que o fornecedor disse e o que os documentos provam |
| 5 · Negociação | Cláusulas propostas e negociadas diretamente com o fornecedor |
| 6 · Parecer | Decisão fundamentada, com condições |
| 7 · Rastreabilidade | Matriz ligando cada lacuna ao seu tratamento, status e risco residual |


---

## 🎚️ 1. Classificação de Criticidade do Fornecedor

Para determinar o nível de diligência exigido na avaliação da Nexaflow, foram aplicados três critérios de classificação:

| Critério | Avaliação | Justificativa |
|---|:---:|---|
| Tipo de dado | 🔴 Crítico | A Nexaflow processará dados financeiros, de clientes (nome, CNPJ, valores de contrato) e estratégicos da CloudFlux |
| Tipo de acesso | 🔴 Crítico | O acesso não se limita à visualização: envolve processamento, armazenamento e integração via API REST |
| Impacto operacional | 🔴 Crítico | Uma falha ou indisponibilidade do fornecedor impacta diretamente a operação financeira da CloudFlux, com risco de perda de dados, atrasos e descontinuidade de processos críticos |

A classificação final corresponde ao **maior nível** entre os três critérios, avaliados pela escala abaixo.

| Critério | 🔴 Crítico | 🟠 Alto | 🟡 Médio | ⚪ Baixo |
|---|---|---|---|---|
| Tipo de dado | Dados financeiros, de clientes ou pessoais em volume | Dados internos sensíveis | Dados internos de baixo impacto | Sem acesso a dados |
| Tipo de acesso | Processamento, armazenamento e integração com sistemas | Leitura de dados em produção | Acesso pontual e supervisionado | Sem acesso lógico |
| Impacto da falha | Interrompe a operação financeira | Degrada processos importantes | Atraso tolerável | Sem impacto relevante |

**Classificação final: 🔴 Crítico.** Por ser fornecedor crítico, a Nexaflow está sujeita ao processo completo de due diligence de segurança antes da contratação, incluindo questionário detalhado por domínio, análise de gaps, parecer de risco fundamentado e formalização de cláusulas contratuais de segurança.

🔄 **Fase futura (módulo de RH):** quando a CloudFlux ativar o módulo de RH, a Nexaflow passará a tratar dados pessoais de colaboradores, o que eleva a sensibilidade dos dados tratados. Nesse caso, o fornecedor deve ser reavaliado.

---

## 📝 2. Questionário de Due Diligence

Oito domínios. Cada um traz as perguntas, as respostas do fornecedor e **por que aquela pergunta importa**. Clique em cada domínio para abrir.

<details>
<summary>🏛️ Domínio 1 · Governança de Segurança</summary>

**A empresa possui Política de Segurança da Informação formalmente documentada? Qual a data da última revisão e quem é o responsável pela aprovação?**

> Sim. Temos Política de Segurança da Informação formalmente documentada, publicada internamente e revisada anualmente. A última revisão foi em março de 2026, com aprovação da Diretoria Executiva.

**Quais certificações de segurança da informação a empresa possui? Qual a data de validade/renovação e qual é o escopo coberto pela certificação?**

> A Nexaflow é certificada ISO/IEC 27001:2022, com validade até setembro de 2027. O escopo cobre o ciclo de desenvolvimento e manutenção do produto, na nossa sede em Campinas.

**A empresa possui um responsável formal pela segurança da informação? Qual o cargo/função?**

> Sim. Temos um Gerente de Segurança da Informação, que reporta à Diretoria de Tecnologia.

💡 **Por que importa:** sem política aprovada, escopo claro de certificação e um responsável definido, não há base para cobrar controles do fornecedor (A.5.19).

</details>

<details>
<summary>🔐 Domínio 2 · Gestão de Acesso</summary>

**Como é feita a gestão de acessos (IAM) hoje? A empresa adota princípios de RBAC e privilégio mínimo?**

> Sim. Trabalhamos com RBAC e privilégio mínimo. Dentro do ERP, o administrador do cliente define perfis e permissões por módulo e por função.

**O MFA é obrigatório para todos os usuários ou é opcional? Caso obrigatório, é possível comprovar por meio de print ou documento da configuração?**

> O MFA está disponível para todos os usuários da plataforma e é ativado pelo administrador de cada cliente. Recomendamos fortemente a ativação. Sobre comprovação, posso enviar a documentação técnica da funcionalidade. O print da configuração depende do ambiente de cada cliente.

*Esclarecimento pedido sobre o MFA dos colaboradores internos do fornecedor:*

> Para o time de desenvolvimento, em Campinas, sim: o MFA é obrigatório nos acessos corporativos e aos ambientes de produção. Isso faz parte dos controles da nossa certificação ISO 27001. Para as demais áreas, como suporte e implantação, confirmação pendente com o time de segurança.

**Como é realizado o processo de revogação de acessos em caso de desligamento de colaborador? É possível apresentar evidência desse processo?**

> O desligamento é integrado ao fluxo do RH, e a revogação de acessos acontece em até 24 horas. Posso compartilhar a descrição do procedimento.

💡 **Por que importa:** o controle de acesso limita o estrago de uma credencial comprometida, e o MFA é a principal barreira contra o uso de senha roubada.

</details>

<details>
<summary>🔒 Domínio 3 · Proteção de Dados</summary>

**Os dados são criptografados em trânsito e em repouso? Quais protocolos/padrões são utilizados?**

> Em trânsito usamos TLS 1.2 ou superior. Em repouso, os bancos de dados principais são criptografados com AES-256.

**Onde os dados ficam armazenados? Em qual país/região estão os servidores?**

> Os dados ficam na AWS, na região de São Paulo, dentro do Brasil.

💡 **Por que importa:** criptografia protege os dados em caso de interceptação ou acesso indevido, e o local de armazenamento define a jurisdição e evita transferência internacional (A.5.23, serviços em nuvem).

</details>

<details>
<summary>🔗 Domínio 4 · Subprocessadores</summary>

**A empresa utiliza terceiros (subprocessadores) que terão acesso aos dados dos nossos clientes? Se sim, quais são e qual a finalidade do acesso?**

> Nossa infraestrutura principal roda na AWS. Além dela, contamos com parceiros especializados em atividades de suporte técnico, todos sob contrato.

**Esses subprocessadores seguem políticas e requisitos de segurança equivalentes aos da Nexaflow? Como isso é garantido e controlado?**

> Os contratos com parceiros incluem cláusulas de confidencialidade e requisitos de segurança. Fazemos a gestão desses contratos de forma centralizada.

**Em caso de mudança ou adição de um novo subprocessador, a Nexaflow notifica os clientes previamente?**

> Mantemos a lista de parceiros atualizada no nosso portal de transparência, e alterações relevantes são comunicadas por lá.

*Informação complementar, obtida por solicitação direta:*

> Além da AWS, há um parceiro terceirizado de suporte técnico que atua na camada de suporte e, quando necessário para resolver chamados, pode ter acesso aos ambientes de produção. O parceiro atua sob contrato com cláusulas de confidencialidade.

💡 **Por que importa:** cada subcontratado amplia a superfície de risco, e a CloudFlux responde pelo que o operador e seus subcontratados fazem com os dados (A.5.21 e A.5.22).

</details>

<details>
<summary>♻️ Domínio 5 · Continuidade / DR</summary>

**A empresa possui BCP e/ou Plano de DR formalmente documentado? Com que frequência é testado?**

> Sim. Temos BCP e plano de DR documentados, com testes periódicos conforme nosso cronograma interno.

**Quais são os valores declarados de RTO e RPO? É possível apresentar documentação de suporte?**

> Nossos valores declarados são RTO de 4 horas e RPO de 1 hora. A documentação de suporte pode ser compartilhada sob NDA.

💡 **Por que importa:** um plano que nunca é testado não prova que a recuperação funciona, e RTO e RPO definem quanto tempo e quantos dados a CloudFlux pode perder.

</details>

<details>
<summary>🚨 Domínio 6 · Gestão de Incidentes</summary>

**A empresa possui processo formal de resposta a incidentes de segurança? É possível apresentar evidências?**

> Sim. Temos processo formal de resposta a incidentes, e o procedimento pode ser compartilhado sob NDA.

**Em caso de vazamento de dados ou comprometimento da operação, em quanto tempo os clientes são notificados?**

> O SLA contratual padrão de notificação é de até 5 dias úteis. Esse prazo permite apurar o ocorrido e comunicar com informação consistente. Dependendo da gravidade, buscamos antecipar.

💡 **Por que importa:** o prazo de notificação do fornecedor consome a margem legal da CloudFlux, que, como controladora, tem 3 dias úteis para comunicar a ANPD.

</details>

<details>
<summary>🧪 Domínio 7 · Conformidade</summary>

**A empresa realiza testes de penetração (pentest) externos? Com qual frequência? Os resultados são compartilhados com clientes?**

> Realizamos pentest externo anualmente. Posso enviar a comprovação da realização e da vigência. Compartilhamos com os clientes o resumo executivo. O relatório completo é confidencial.

💡 **Por que importa:** sem achados por severidade e status de correção, não dá para avaliar o risco técnico real do fornecedor.

</details>

<details>
<summary>🛡️ Domínio 8 · LGPD / Privacidade</summary>

**A empresa possui DPO (Encarregado de Proteção de Dados) formalmente nomeado?**

> Sim, temos DPO formalmente nomeado.

**A empresa disponibiliza DPA como anexo contratual?**

> Sim, o DPA é um anexo contratual padrão. Posso enviar o modelo para análise prévia.

**Em caso de incidente envolvendo dados pessoais, em quanto tempo os clientes são notificados?**

> O prazo é o mesmo do SLA geral de incidentes: até 5 dias úteis.

💡 **Por que importa:** o DPA formaliza o papel de operador e as obrigações de proteção de dados, e é onde a CloudFlux garante, por contrato, o que a LGPD exige (A.5.20).

</details>

---

## 📎 Evidências recebidas

O fornecedor entregou os documentos em **dois blocos**. O segundo só foi liberado depois da assinatura do NDA. Ambos são simulados, e os detalhes que viraram lacunas estão escondidos dentro dos próprios documentos, como numa avaliação real.

| Bloco | Conteúdo | Arquivo |
|---|---|---|
| **Bloco 1** · documentos abertos e NDA | Certificado ISO 27001 · Procedimento de MFA interno · Guia de MFA para clientes · Procedimento de revogação de acessos · Modelo de DPA · Atestado e resumo executivo de pentest · Acordo de confidencialidade (NDA) | [📄 Bloco 1 (PDF)](Nexaflow_Pacote_Due_Diligence_PDF1_v6.pdf) |
| **Bloco 2** · confidencial, sob NDA | Plano de continuidade e DR com histórico de testes · Procedimento de resposta a incidentes · Política de acesso e relatório de aderência ao MFA | [📄 Bloco 2 (PDF)](Nexaflow_Pacote_Due_Diligence_PDF2_Bloco2.pdf) |

---

## 🔍 3. Análise de Lacunas

A análise foi conduzida com base nas respostas ao questionário e nos documentos recebidos nos dois blocos.

| # | Lacuna identificada | Severidade | Descrição |
|:---:|---|:---:|---|
| 1 | ISO e MFA sem cobertura em suporte e implantação | 🔴 Crítico | A certificação ISO/IEC 27001:2022 cobre apenas a Unidade de Desenvolvimento de Campinas. O Relatório de Aderência ao MFA (Bloco 2, Doc 3) atesta 100% de aderência, mas tem como fonte exclusiva o diretório dessa unidade (154 usuários), e a obrigatoriedade do MFA para suporte e implantação está com confirmação pendente. Esses times acessam diretamente os ambientes dos clientes. |
| 2 | MFA opcional para usuários do cliente | 🟡 Médio | O MFA é opcional no ambiente do cliente, e cabe ao administrador da CloudFlux ativá-lo e torná-lo obrigatório. A configuração padrão foge do princípio de segurança por padrão para um sistema que processa dados financeiros. O risco não está na Nexaflow, e sim na configuração do ambiente, que a CloudFlux controla; por isso é tratado por **ação interna**, e não por cláusula contratual. |
| 3 | SLA de incidente incompatível com a LGPD | 🔴 Crítico | O DPA (cláusula 6) e o procedimento de incidentes definem 5 dias úteis, contados após a confirmação, como SLA padrão. A Resolução CD/ANPD nº 15/2024 exige que o controlador (CloudFlux) comunique a ANPD em até 3 dias úteis a partir do conhecimento do incidente. O prazo da Nexaflow não deixa margem operacional suficiente para a CloudFlux investigar e cumprir sua obrigação legal. |
| 4 | Evidência de pentest insuficiente | 🟠 Alto | Apenas o sumário executivo genérico é compartilhado, sem breakdown de severidades nem evidência de remediação. O relatório completo é classificado como confidencial pela Nexaflow. |
| 5 | Suboperador não divulgado | 🟠 Alto | O parceiro de suporte técnico terceirizado não foi mencionado espontaneamente, sendo revelado apenas quando questionado diretamente. Documentos internos (Bloco 2, Doc 2) confirmam que esse parceiro pode ser acionado em incidentes e ter acesso a ambientes de produção, caracterizando-o como suboperador sob a LGPD. |
| 6 | Teste de DR desatualizado e sem periodicidade definida | 🔴 Crítico | O histórico de testes (Bloco 2, Doc 1) mostra que o último teste formal de recuperação foi em maio/2025, há cerca de 18 meses, fora do ciclo anual esperado pelo mercado e pelas boas práticas de continuidade (ISO 22301). O plano foi revisado em fevereiro/2026, depois desse teste, e não foi testado desde então. Além disso, o plano não define a periodicidade dos testes e cita apenas um "cronograma definido pelo Comitê de Continuidade". **Risco:** não há evidência de que o RTO de 4 horas e o RPO de 1 hora declarados são atingíveis hoje. |
| 7 | DPA padrão com garantias fracas | 🟠 Alto | Além do prazo de notificação, a auditoria se limita a relatórios e certificações mediante solicitação (cláusula 8 do DPA), a lista de suboperadores fica em portal, sem aviso prévio nem direito de objeção (cláusula 5), e a eliminação de dados não exige comprovação (cláusula 9). |

### 📊 Placar

| 🔴 Crítico | 🟠 Alto | 🟡 Médio |
|:---:|:---:|:---:|
| **3** | **3** | **1** |

---

## ⚖️ 4. Parecer de Risco

### Decisão: ✅ aprovar com ressalvas

A Nexaflow apresenta controles documentados dentro do escopo da sua certificação ISO 27001 (desenvolvimento, em Campinas), como política de segurança revisada anualmente, criptografia em trânsito e em repouso, MFA obrigatório para o time de desenvolvimento e DPO nomeado. No entanto, a avaliação identificou **três lacunas de severidade crítica**, que exigem mitigação contratual antes da assinatura.

As lacunas críticas (escopo da certificação e cobertura de MFA que não alcançam suporte e implantação, SLA de notificação de incidente incompatível com a LGPD e teste de DR desatualizado) representam riscos diretos de segurança de acesso, conformidade regulatória e continuidade operacional, que não podem ser aceitos sem contrapartidas formais.

A contratação é recomendada condicionada à formalização, no Anexo de Segurança, das cláusulas definidas na Seção 5, já aceitas pela Nexaflow em negociação. A reavaliação do fornecedor deve ocorrer em **12 meses** ou na ocorrência de incidente de segurança relevante.

Como o último teste de DR da Nexaflow ocorreu há cerca de 18 meses, a simples exigência de testes anuais daqui em diante não elimina o risco atual. Por isso, a realização de um teste inicial, com resultado dentro dos valores declarados, é **condição prévia ao início da operação**, e não apenas obrigação contratual futura.

O prazo de 90 dias para adequação do MFA mantém a CloudFlux exposta durante o período. Por isso, foram definidos controles compensatórios (acesso temporário mediante aprovação e registro das sessões) até a adequação completa.

🏠 **Ação interna da CloudFlux:** ativar MFA obrigatório para todos os usuários do ERP desde o primeiro dia de uso, antes do início da operação.

---

## 📜 5. Cláusulas Contratuais Mínimas de Segurança

As cláusulas abaixo foram definidas a partir da análise de lacunas e compõem a minuta do Anexo de Segurança, insumo para o Jurídico. Todas foram apresentadas e aceitas pela Nexaflow em negociação.

**Cláusula 1 · Notificação de incidente.** A Nexaflow deve comunicar a CloudFlux em até 24 horas após a confirmação de incidente crítico que envolva dados da CloudFlux. Relatório completo com natureza dos dados, impacto e medidas adotadas deve ser entregue em até 5 dias úteis. Os termos "confirmação" e "incidente crítico" serão definidos em glossário no próprio Anexo de Segurança.

**Cláusula 2 · Testes de BCP/DR.** A Nexaflow deve realizar um teste inicial de recuperação de desastre, em ambiente isolado equivalente à produção, antes da migração de dados da CloudFlux para a plataforma, com entrega do relatório de resultados (RTO e RPO medidos, falhas identificadas e plano de ação) em até 15 dias. O início da operação fica condicionado a RTO e RPO medidos dentro dos valores declarados (4 horas e 1 hora). Após o teste inicial, o teste passa a ser anual, com relatório em até 45 dias após cada realização.

**Cláusula 3 · MFA para suporte e implantação.** MFA obrigatório para todo profissional de suporte e implantação, incluindo o parceiro de suporte técnico, com acesso a ambientes de clientes. Prazo de adequação de 90 dias após a assinatura do contrato. Evidência de aderência enviada à CloudFlux semestralmente, com cobertura de todos os times e do parceiro, e não só da Unidade de Desenvolvimento.

Durante o prazo de adequação, aplicam-se controles compensatórios:
- Acesso ao ambiente da CloudFlux somente mediante chamado aberto ou aprovação prévia da CloudFlux, de forma temporária e com prazo definido;
- Registro das sessões de acesso, com os logs disponibilizados à CloudFlux mediante solicitação;
- Proibição de acessos permanentes ou compartilhados por profissionais sem MFA.

**Cláusula 4 · Disclosure de suboperadores.** A Nexaflow deve manter e compartilhar lista atualizada de todos os suboperadores com acesso a dados da CloudFlux, contendo nome, finalidade, tipo de acesso e localização. Deve apresentar extrato das cláusulas de proteção de dados dos contratos com cada suboperador como comprovação de obrigações equivalentes à LGPD.

**Cláusula 5 · Evidência de pentest.** A Nexaflow deve compartilhar anualmente resumo ampliado do pentest externo, contendo contagem de achados por severidade e status de remediação de cada item. O resumo deve ser atualizado junto com o ciclo anual de pentest, sob NDA.

**Cláusula 6 · Direito de auditoria.** A CloudFlux, por si ou por auditor independente, pode auditar os controles que protegem seus dados uma vez por ano e após qualquer incidente crítico, com aviso prévio de 30 dias e escopo limitado a esses controles. Relatórios independentes vigentes que cubram o escopo do serviço, inclusive suporte e implantação, podem substituir parcialmente a auditoria.

**Cláusula 7 · Mudança de suboperadores.** A Nexaflow notifica a CloudFlux por e-mail, ao contato designado, com 30 dias de antecedência, sobre a inclusão ou a troca de suboperador com acesso a dados da CloudFlux. A comunicação apenas no portal não basta. A CloudFlux pode apresentar objeção fundamentada e, sem solução, rescindir o contrato sem multa.

**Cláusula 8 · Eliminação de dados.** No encerramento do contrato, a Nexaflow devolve os dados em formato estruturado e os elimina em até 90 dias, conforme o DPA. Em até 30 dias após a eliminação, entrega certificado de eliminação, incluindo dados em poder de suboperadores.

---

## 🧭 6. Matriz de Rastreabilidade

Todas as sete lacunas têm tratamento definido. As cláusulas contratuais foram aceitas pela Nexaflow e aguardam formalização no Anexo de Segurança; a lacuna 2 é tratada por ação interna da CloudFlux.

| # | Lacuna | Severidade | Tratamento | Status | Risco residual |
|:---:|---|:---:|---|---|---|
| 1 | ISO e MFA sem cobertura em suporte e implantação | 🔴 Crítico | Cláusula 3 (MFA) e Cláusula 6 (auditoria) | Cláusulas 3 e 6 e controles compensatórios aceitos | Médio nos 90 dias de adequação |
| 2 | MFA opcional para usuários do cliente | 🟡 Médio | Ação interna da CloudFlux: MFA obrigatório desde o primeiro dia | A executar pela CloudFlux | Baixo |
| 3 | SLA de incidente incompatível com a LGPD | 🔴 Crítico | Cláusula 1 (24h após confirmação) | Aceita; depende do glossário | Baixo a médio |
| 4 | Evidência de pentest insuficiente | 🟠 Alto | Cláusula 5 (resumo ampliado) | Aceita | Baixo |
| 5 | Suboperador não divulgado | 🟠 Alto | Cláusula 4 (lista e extrato) e Cláusula 7 (aviso de mudança) | Cláusulas 4 e 7 aceitas | Baixo |
| 6 | Teste de DR desatualizado e sem periodicidade definida | 🔴 Crítico | Cláusula 2 (teste inicial e anual) e condição prévia ao início da operação | Teste inicial e anual aceitos | Alto até o teste inicial |
| 7 | DPA padrão com garantias fracas | 🟠 Alto | Cláusulas 6, 7 e 8 | Cláusulas 6, 7 e 8 aceitas | Médio até a assinatura |

---

## ✅ O que este projeto demonstra

- **Diligência proporcional ao risco:** classificar o fornecedor primeiro, para decidir quanto aprofundar a avaliação.
- Entender que **ter a certificação** e **saber o escopo da certificação** são coisas diferentes. A ISO 27001 da Nexaflow existia, mas não cobria quem acessaria os ambientes da CloudFlux.
- Cruzar **resposta** com **evidência**: o relatório de MFA mostrava 100% de aderência, mas a fonte era só a unidade certificada.
- Conectar o prazo do fornecedor à **obrigação legal do controlador**: 5 dias úteis de SLA contra 3 dias úteis para comunicar a ANPD.
- Separar o que é **risco do fornecedor** do que é **configuração da própria CloudFlux**: o MFA opcional virou ação interna, e não cláusula.
- Tratar a lacuna do DR como **condição prévia ao início da operação**, e não como obrigação futura, porque exigir testes anuais dali em diante não resolve o risco de hoje.
- **Rastreabilidade:** cada lacuna ligada ao seu tratamento, status e risco residual, sem deixar ponta solta.

## 🔜 Próximo nível

- 📝 **Formalização com o Jurídico:** as cláusulas foram aceitas na negociação, mas ainda precisam entrar no Anexo de Segurança e ser assinadas.
- 🔁 **Monitoramento pós-contratação e offboarding:** este projeto cobre a avaliação, a decisão e a formalização. O acompanhamento contínuo do fornecedor e o encerramento do contrato ficaram de fora.
- 📅 **Gatilhos de reavaliação:** ativação do módulo de RH, incidente relevante ou 12 meses.
- 🏠 **Ação interna pendente:** ativar o MFA obrigatório para os usuários do ERP antes do início da operação.
- 📚 **Política de terceiros recorrente:** transformar este fluxo em procedimento padrão, com critérios de classificação e questionário reaproveitáveis para os próximos fornecedores.

## 🧵 Na série CloudFlux

- 🔗 A **avaliação de terceiros** era o risco R08 da [Matriz de Risco (Projeto 01)](../01-matriz-de-risco/), tratado como "aceitar e monitorar".
- 🕵️‍♀️ A [Auditoria de Controles (Projeto 02)](../02-auditoria-de-controles/) reprovou esse controle na RNC 06: homologação fora da rotina de compras e contratos sem cláusulas de segurança e LGPD. Este projeto é a **primeira avaliação formal de terceiro** da CloudFlux.
- ⚖️ O **controlador x operador**, deixado como próximo nível no [Mapeamento de Dados e RIPD (Projeto 08)](../08-lgpd-mapeamento-ripd/), aparece aqui na prática: a CloudFlux como controladora e a Nexaflow como operador de dados.
- 📄 A [PSI (Projeto 09)](../09-politica-seguranca-informacao/) é o documento-mãe. Este projeto é a política colocada para funcionar com o primeiro fornecedor avaliado.
