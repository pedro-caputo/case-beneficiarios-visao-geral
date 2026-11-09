# Guia de Apresentação Executiva — Roteiro de 11 Slides & Defesa Técnica

> [!IMPORTANT]
> **Aviso Institucional:** Guia estruturado de apoio para apresentação executiva e entrevista técnica de estágio. Foco em comunicação clara, rigor conceitual e respostas defensáveis perante banca examinadora.

---

## 1. Roteiro Narrativo dos 11 Slides

A narrativa foi construída para demonstrar visão de ponta a ponta: do diagnóstico do problema de negócio até a validação empírica e análise crítica de arquitetura.

---

### Slide 1 — Abertura e Posicionamento
- **Mensagem Principal:** Como transformar um processo securitário manual, sobrecarregado e com 38% de atraso em uma operação digital, rastreável e governada.
- **Evidência:** Entrega integrada de protótipo executável em Python e arquitetura de referência em Microsoft Power Platform.
- **Transição Narrativa:** *"Para entender a oportunidade de transformação, precisamos primeiro olhar para os números reais da operação histórica."*
- **Ressalva Técnica:** Projeto educacional e independente; dados fictícios e telas da Power Platform conceituais.
- **Pergunta Típica da Banca:** *"Qual foi o seu papel e objetivo principal neste projeto?"*

---

### Slide 2 — Contexto e Indicadores Operacionais
- **Mensagem Principal:** A operação processa 1.000 solicitações mensais com 3 analistas, mas a convergência para uma caixa de e-mail compartilhada compromete o prazo de 5 dias em 38% dos casos.
- **Evidência:** 55% e-mail, 30% agências, 15% app; ~25% inadequações documentais na entrada; 313h20 de esforço humano mensal.
- **Transição Narrativa:** *"Esse cenário de atrasos não decorre de baixa produtividade individual, mas de três gargalos estruturais na jornada do processo."*
- **Ressalva Técnica:** O esforço humano ativo de 313,33 h não equivale ao tempo total de espera (*lead time*) do cliente.
- **Pergunta Típica da Banca:** *"Por que a equipe não consegue cumprir o SLA se possui 3 analistas dedicados?"*

---

### Slide 3 — Os Três Gargalos Principais
- **Mensagem Principal:** O processo sofre com entrada inadequada sem crítica na origem, triagem artesanal em caixa compartilhada e ausência de rastreabilidade de SLA.
- **Evidência:** Anexos ilegíveis e sem validação matemática de 100%; filas operacionais invisíveis; relógio de SLA correndo enquanto a seguradora aguarda o segurado.
- **Transição Narrativa:** *"Identificados esses gargalos, estabelecemos uma diretriz clara de engenharia antes de escrever qualquer linha de código."*
- **Ressalva Técnica:** Não é possível atribuir uma cota percentual exata dos 38% de atraso a cada gargalo individual sem telemetria prévia.
- **Pergunta Típica da Banca:** *"Qual desses três gargalos é o mais danoso para o cliente final?"*

---

### Slide 4 — Diretrizes da Solução
- **Mensagem Principal:** *“Antes de automatizar, é necessário estruturar, controlar e tornar o processo rastreável.”*
- **Evidência:** Validação preventiva (*Shift-Left*), triagem determinística, medição de tempo líquido de SLA e registro permanente em log auditável.
- **Transição Narrativa:** *"Com essas diretrizes, desenhamos o novo fluxo operacional TO-BE."*
- **Ressalva Técnica:** Automação sem padronização prévia apenas acelera a geração de inconsistências cadastrais.
- **Pergunta Típica da Banca:** *"O que você quer dizer com 'Shift-Left' em um processo de seguros?"*

---

### Slide 5 — Fluxo Operacional TO-BE
- **Mensagem Principal:** Uma jornada orquestrada em 11 etapas, segregando o fluxo em três caminhos determinísticos: Regular (STP assistido), Pendência (pausa de SLA) e Exceção humana.
- **Evidência:** Fluxograma com protocolo unificado, motor de regras em memória e persistência de eventos imutáveis.
- **Transição Narrativa:** *"Para provar que essa lógica funciona de forma prática e estável, construímos um protótipo funcional em Python."*
- **Ressalva Técnica:** O encerramento do SLA está atrelado à confirmação da alteração no cadastro; a notificação final é gerenciada de forma assíncrona.
- **Pergunta Típica da Banca:** *"Como o sistema garante que o cliente foi notificado caso ocorra uma falha técnica no servidor de e-mail?"*

---

### Slide 6 — Protótipo Funcional Python
- **Mensagem Principal:** Uma aplicação completa em Streamlit e SQLite que valida regras, gerencia filas, calcula SLA líquido e isola dados interativos de experimentos.
- **Evidência:** Demonstração da Nova Solicitação, Bancada do Analista com tomada de decisão fundamentada e 35 testes automatizados aprovados no Pytest.
- **Transição Narrativa:** *"Ao desenvolver o protótipo, ficou evidente que a tecnologia deve potencializar o analista, não tentar substituí-lo às cegas."*
- **Ressalva Técnica:** A efetivação cadastral foi simulada em banco relacional local, sem conexão direta com o mainframe de seguros legado.
- **Pergunta Típica da Banca:** *"Por que escolher Streamlit e SQLite para o protótipo em vez de um framework full-stack?"*

---

### Slide 7 — Automação vs Participação Humana (*Human-in-the-Loop*)
- **Mensagem Principal:** O analista humano é indispensável para deliberar sobre certidões limítrofes, exceções de negócio e confirmação de efetivação cadastral.
- **Evidência:** Bancada do Analista projetada com bloqueio de concorrência e obrigatoriedade de registro de justificativa.
- **Transição Narrativa:** *"Provado o conceito funcional em Python, como essa mesma lógica pode ser escalada em uma grande corporação financeira?"*
- **Ressalva Técnica:** Alterações de beneficiários possuem implicações legais sucessórias; automação 100% não assistida gera risco jurídico inaceitável.
- **Pergunta Típica da Banca:** *"Quais tarefas permanecem estritamente sob a responsabilidade do analista humano?"*

---

### Slide 8 — Alternativas de Implementação: Python vs Power Platform
- **Mensagem Principal:** Um mesmo TO-BE explorado em duas alternativas independentes: Python para validação experimental rápida e Power Platform para arquitetura corporativa governada.
- **Evidência:** Matriz comparativa: Pro-Code (SQLite, Streamlit, Pytest) vs Low-Code (Power Apps, Dataverse 19 tabelas, 9 fluxos Power Automate, SharePoint e Power BI).
- **Transição Narrativa:** *"Vamos analisar agora os resultados estatísticos obtidos no laboratório de simulação."*
- **Ressalva Técnica:** São soluções independentes; a Power Platform é uma especificação arquitetural documentada e mockups, não implantada em tenant real.
- **Pergunta Típica da Banca:** *"Se você tivesse que recomendar apenas uma alternativa para iniciar amanhã no banco, qual escolheria e por quê?"*

---

### Slide 9 — Resultados do Protótipo e Laboratório
- **Mensagem Principal:** Simulação em lote com 1.000 intenções sintéticas demonstrou que 75% dos casos são aptos para cadastro direto e 77 erros de entrada são bloqueados na raiz.
- **Evidência:** 750 aptas, 190 aguardando complemento com pausa de SLA, 60 exceções para a bancada; 0,221 segundo de execução algorítmica em CPU.
- **Transição Narrativa:** *"Esse volume de processamento direto tem impacto imediato no esforço exigido dos analistas."*
- **Ressalva Técnica:** O tempo de 0,221 s reflete processamento computacional da CPU sobre dados em memória, e não o tempo de ciclo percebido pelo segurado.
- **Pergunta Típica da Banca:** *"O que representam os 77 erros prevenidos e por que eles não somam 1.000 com as outras categorias?"*

---

### Slide 10 — Esforço Operacional e Premissas Metodológicas
- **Mensagem Principal:** Redução modelada de 87,2% no esforço humano ativo mensal (de 313,33 h para 40,25 h/mês), liberando mais de 270 horas para a célula.
- **Evidência:** Gráfico comparativo de barras; decomposição detalhada das horas residuais (60 exceções x 15 min + 750 cadastros x 2 min + 15 min de auditoria).
- **Transição Narrativa:** *"Para transformar essa projeção matemática em realidade corporativa, definimos um roteiro seguro de implantação."*
- **Ressalva Técnica:** Estimativa experimental da solução Python que exige validação empírica de tempos e métodos (*time study*) em ambiente de produção real.
- **Pergunta Típica da Banca:** *"Você garante que a equipe de 3 analistas passará a cumprir 100% dos prazos com essa redução de esforço?"*

---

### Slide 11 — Encerramento, Governança e Próximos Passos
- **Mensagem Principal:** A entrega consolida diagnóstico factual, validação empírica funcional e desenho de arquitetura corporativa, pavimentando um caminho seguro para implantação.
- **Evidência:** Mapeamento das 7 pendências corporativas (P01 a P07) e roteiro em 4 fases: Homologação de regras → PoC de integração → Shadow Run (10%) → Rollout gradual.
- **Transição Narrativa:** *"Estou à disposição para aprofundarmos em qualquer detalhe técnico, arquitetural ou de negócio."*
- **Ressalva Técnica:** Nenhuma implantação deve ocorrer sem a prévia resolução jurídica da política de lista integral vs parcial.
- **Pergunta Típica da Banca:** *"Qual é o principal aprendizado que você extraiu ao conduzir este estudo?"*

---

## 2. Seção de Perguntas Difíceis & Respostas Defensáveis

### P1. Por que propor duas arquiteturas tecnológicas em vez de apenas uma?
**Resposta:** *"Porque elas atendem a propósitos de engenharia distintos e complementares. A Alternativa A (Python) é um protótipo funcional executável cujo objetivo foi validar empiricamente as regras de negócio, a máquina de estados e o comportamento sob estresse de 1.000 casos em ambiente controlado com custo zero de infraestrutura. A Alternativa B (Power Platform) é uma arquitetura de referência corporativa desenhada para grandes instituições financeiras que já possuem ecossistema Microsoft 365, endereçando governança, matriz de segurança RBAC nativa no Entra ID, custódia no SharePoint e observabilidade no Power BI. São caminhos independentes que compartilham a mesma lógica funcional TO-BE."*

### P2. Por que usar o Microsoft Dataverse e não uma tabela em SharePoint ou banco SQL padrão?
**Resposta:** *"O SharePoint é um excelente repositório de documentos, mas não é um banco de dados relacional transacional. Ele carece de controle de concorrência otimista, não oferece integridade referencial rigorosa e não suporta modelo de dados complexo de 19 entidades com relações de um-para-muitos. O Dataverse provê segurança em nível de linha (*Row-Level Security*), integração nativa com o modelo de segurança do Entra ID, trilha nativa de auditoria de alterações e suporte transacional indispensável para operações financeiras."*

### P3. Por que manter a intervenção humana na efetivação do cadastro em vez de automatizar 100%?
**Resposta:** *"Por responsabilidade jurídica e prudência técnica. A alteração de beneficiários em apólices de seguro envolve direito securitário e sucessório. Uma alteração indevida gera risco de litígio judicial e indenização incorreta em caso de sinistro. Além disso, a seguradora opera com sistemas legados (mainframe) cuja conexão direta via API ou RPA exige homologações rigorosas de segurança. A abordagem de 'Cadastro Assistido' acelera o trabalho do analista, pré-valida todos os dados em tela e exige que o profissional confirme a alteração com chave de evidência, mantendo o humano no controle da decisão final."*

### P4. Como o relógio de SLA é pausado na prática e quando ele deve ser retomado?
**Resposta:** *"No modelo TO-BE, a emissão de uma notificação de pendência documental registra um evento de pausa com timestamp preciso. O tempo de atendimento regulatório é calculado de forma líquida, descontando as horas acumuladas em que a solicitação esteve no estado `Aguardando Complemento`. Como premissa provisória aprovada no case, a contagem é retomada no instante em que um novo documento vinculável ao protocolo é recebido no sistema. Isso impede que a inércia do cliente penalize injustamente os indicadores de eficiência da equipe da seguradora."*

### P5. Como evitar inconsistências quando o cliente envia documentos adicionais picados?
**Resposta:** *"Através do versionamento imutável de submissões. Cada envio de dados ou documentos gera uma revisão associada ao protocolo. O sistema não sobrescreve registros anteriores. Ao receber um novo documento, o motor de regras reavalia o checklist completo da solicitação. Se a documentação ainda estiver incompleta, o caso permanece em pendência ou é roteado para o analista com histórico integral das interações anteriores."*

### P6. Como garantir a rastreabilidade total do processo perante uma auditoria regulatória da SUSEP?
**Resposta:** *"Através de uma trilha de auditoria append-only imutável. No protótipo Python, implementamos a tabela `eventos_historico`, onde nenhum registro pode ser atualizado ou apagado, apenas inserido. Na arquitetura Power Platform, utilizamos a auditoria nativa do Dataverse combinada com a tabela transacional `bpf_historico_evento`. Cada transição de estado registra data/hora, identificador do usuário ou fluxo automático, estado anterior, estado novo e a justificativa associada."*

### P7. O que acontece se houver uma falha técnica na comunicação de conclusão ao cliente?
**Resposta:** *"O encerramento do SLA cadastral e o envio da notificação ao cliente foram arquiteturalmente desacoplados pelo padrão Outbox. O analista confirma a alteração no core e o protocolo é considerado 'Concluído' com SLA encerrado. A notificação entra em uma fila assíncrona de mensageria. Se o servidor de e-mail falhar, o serviço realiza novas tentativas automáticas (*retries* com backoff exponencial) e alerta os operadores sem reabrir ou distorcer o prazo cadastral do processo."*

### P8. O cadastro foi realmente automatizado nos sistemas centrais de seguros?
**Resposta:** *"Não de forma totalmente autônoma (*unattended*). O que foi implementado e demonstrado é o conceito de **Cadastro Assistido**. O motor de validação pré-processa as regras de negócio, assegura que o CPF é válido, que as quotas somam 100% e que os documentos estão legíveis, entregando ao analista uma tela consolidada pronta para conferência e gravação no sistema legado. Essa escolha reduz o tempo manual de digitação de 5 para 2 minutos por caso, sem criar dependência tecnológica prematura de integração de APIs com o core mainframe."*

### P9. A redução de esforço de 87,2% foi comprovada em ambiente real de produção?
**Resposta:** *"Não. Essa é uma projeção analítica resultante do cenário experimental simulado no protótipo Python, calculada sobre o lote de 1.000 intenções na semente `20261108`. O tempo unitário residual de 2 minutos para cadastro assistido e 15 minutos para exceções baseia-se em premissas factuais de engenharia de processos, mas deve ser obrigatoriamente validado através de um estudo de tempos e métodos (*time study*) durante uma operação piloto (*Shadow Run*) em ambiente corporativo."*

### P10. Como validar a solução com segurança antes de colocar em produção para 100% dos clientes?
**Resposta:** *"Recomenda-se uma operação piloto em formato de 'Shadow Run' (execução em paralelo), direcionando inicialmente 10% da volumetria real (ex: solicitações oriundas de uma diretoria regional específica de agências). Durante 30 dias, a equipe processa os casos paralelamente na nova plataforma, permitindo aferir os tempos reais de atendimento (TMA), ajustar os limiares de acurácia de OCR e calibrar a tolerância de documentos sem qualquer risco à continuidade da operação."*

### P11. Como você estima a escalabilidade da solução caso a demanda cresça mais que os 10% ao ano previstos?
**Resposta:** *"Na operação AS-IS, como cada solicitação exige cerca de 18,8 minutos de esforço humano direto, qualquer aumento de volume exige expansão linear da equipe de analistas. No modelo TO-BE, como 75% dos casos passam por triagem e conferência digital imediata, o esforço marginal por nova solicitação cai drasticamente. No protótipo Python, o motor de regras processou 1.000 registros em 0,221 segundo localmente. Na Power Platform, a arquitetura em nuvem desacoplada absorve picos sazonais sem sobrecarregar os analistas, permitindo que a mesma equipe de 3 profissionais absorva o dobro do volume mantendo o foco exclusivo nas exceções."*

### P12. Qual é a responsabilidade de cada ferramenta na arquitetura Microsoft Power Platform?
**Resposta:** *"Cada ferramenta cumpre um papel especializado na esteira:
- **Power Apps Model-Driven:** Interface corporativa ergonômica para a Bancada do Analista e supervisão de filas;
- **Microsoft Dataverse:** Camada relacional transacional de persistência, garantindo integridade de 19 tabelas, bloqueio otimista e RBAC;
- **Power Automate:** Orquestrador assíncrono de eventos, responsável pela ingestão, cálculo de regras, cronômetro de SLA e mensageria;
- **SharePoint Online:** Repositório seguro e de baixo custo para guarda de arquivos e certidões digitalizadas;
- **Power BI:** Camada de observabilidade e inteligência gerencial para acompanhamento de coortes e cumprimento de SLA."*

