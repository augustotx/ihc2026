##### Entrega 8 — Ciclo de vida e engenharia de usabilidade

**Data:** 10/11/2026 (Revisado em 21/11/2026)

**Status:** 🟩 completa

**Responsabilidade:** João Pedro Bazoli Palma e Augusto Pereira Teixeira

###### Objetivo da atividade

Converter o conhecimento acumulado sobre usuários, tarefas, plataforma e contexto de uso em **metas de usabilidade verificáveis**, fundamentando as decisões de design e estabelecendo o processo iterativo do projeto com base no **Ciclo de Engenharia de Usabilidade de Deborah Mayhew**.

---

###### Delimitação do sistema interativo

| Camada | O que pertence ao projeto | O que será avaliado em IHC |
| :--- | :--- | :--- |
| **Contribuição técnica do TCC** | Scripts de automação, execução em Linux com GNU Guix, medições de tempo/memória e base empírica de benchmarks. | O algoritmo e a performance do hardware não são avaliados em IHC. |
| **Camada de interação** | Interface web com catálogo, filtros, Dashboard comparativo (T01) e área de código/reprodutibilidade e exportação (T02). | Compreensão visual, facilidade de filtragem, rapidez na comparação, clareza na auditoria e sucesso na exportação. |
| **Integrações/dados simulados** | Base pré-processada em JSON/CSV com benchmarks reais consolidados. | Exportações geram arquivos reais dessa base; não há compilação/execução em tempo real na avaliação. |

---

###### 1. Características da plataforma

| Característica | Descrição | Consequência para IHC |
| :--- | :--- | :--- |
| **Software** | SPA no navegador web (HTML5, CSS3, JavaScript/TypeScript e biblioteca de gráficos). | Dispensar instalação e configuração local; exige carregamento rápido e transições instantâneas entre visões. |
| **Hardware** | Estações de trabalho desktop e notebooks (resoluções de 1366×768 a 4K). | Layout voltado à interação via mouse/trackpad e teclado físico, otimizado para telas largas que acomodem gráficos e tabelas simultaneamente. |
| **Capacidades** | Filtragem dinâmica de séries, alternância de escalas (linear/log) e cópia assistida de comandos/citações em um clique. | Respostas visuais imediatas sem recarregamento de página reduzem a carga de trabalho cognitivo e aceleram a decisão. |
| **Restrições** | A plataforma não compila nem executa códigos sob demanda; consome dados empíricos previamente homologados. | A interface deve comunicar com clareza que os dados decorrem de ensaios prévios auditados, evitando que o usuário confunda a ferramenta com um *playground* online. |
| **Conectividade** | Conexão de internet padrão; *assets* e datasets compactos. | O processamento e filtragem de visualizações operam no lado cliente (*client-side*) após o carregamento inicial. |
| **Segurança e Privacidade** | Sistema de consulta aberta e irrestrita. | O escopo do sistema não exige cadastro, autenticação nem tratamento intencional de dados pessoais ou sensíveis do usuário. |
| **Volume de dados** | Dezenas de problemas algorítmicos e centenas de medições por par de linguagens. | Demanda paginação, filtros contextuais por tipo de carga (`CPU-bound` vs. `Memory-bound`) e busca textual direta para evitar sobrecarga informacional. |
| **Tempo de processamento** | Renderização gráfica instantânea e download de arquivos leves (CSV/BibTeX). | Feedback visual imediato e perceptível em todas as ações (ex.: notificação inline de comando copiado). |
| **Papéis e permissões** | Papel único de consulta, exploração e exportação. | Eliminação de barreiras de entrada (ausência de telas de login ou cadastros administrativos dispensáveis). |

---

###### 2. Princípios gerais do projeto

###### 2.1 Princípios direcionados ao negócio e ao domínio

* **Rastreabilidade e Integridade Metodológica:** No domínio de benchmarking e computação experimental, números isolados não possuem valor científico sem a descrição exata das condições de contorno. A plataforma assume o compromisso de expor as especificações do ambiente físico (CPU, RAM, Kernel), as diretivas de compilação aplicadas e a versão dos pacotes utilizados (Entregas 1, 2 e 5).
* **Reprodutibilidade Experimental:** O sistema deve fornecer mecanismos declarativos que permitam ao pesquisador reproduzir com exatidão a bancada de testes em seu próprio ambiente, viabilizada pelo fornecimento do manifesto do GNU Guix e códigos-fonte originais (Entregas 2 e 6).
* **Paridade e Imparcialidade de Comparação:** Evitar a apresentação de linguagens como "universalmente superiores". A plataforma deve explicitar o caráter de *trade-off* inerente à engenharia de software (tempo vs. consumo de memória RAM), contextualizado pelo perfil algorítmico do teste.
* **Privacidade e Acesso Aberto (LGPD):** Em consonância com a Lei nº 13.709/2018, o sistema adota o princípio de minimização estrita: por não coletar credenciais nem dados pessoais, a plataforma elimina fricções e riscos desnecessários de privacidade.

###### 2.2 Princípios direcionados à interface

* **Acessibilidade Visual (WCAG 2.1 AA):** Garantir razão de contraste mínima de 4.5:1 para textos normais e 3:1 para elementos gráficos e componentes de interface. As distinções entre séries de dados não devem depender exclusivamente de cor, utilizando formas geométricas e rótulos contextuais para apoiar usuários com discromatopsias (protanopia, deuteranopia e tritanopia).
* **Minimização da Carga de Memória (Reconhecimento em vez de Memorização):** Exibir dados consolidados (médias de tempo e pico de memória) diretamente na tabela e gráfico, evitando que o usuário precise memorizar ou calcular mentalmente grandezas inversas entre telas distintas (Nielsen).
* **Visibilidade do Status e Feedback Imediato:** Toda ação de cópia assistida ou alternância de escala deve fornecer resposta visual instantânea na interface (como alterações cromáticas temporárias e notificações de sucesso), prevenindo incertezas sobre o estado da aplicação.
* **Consistência e Tipografia Especializada:** Adoção de hierarquia visual consistente com a família *Inter* para títulos, instruções e rótulos de interface, reservando a fonte monoespaçada *JetBrains Mono* estritamente para blocos de código, comandos de terminal e tabelas numéricas de alta precisão.

---

###### 3. Metas de usabilidade

###### 3.1 Qualitativas (Exigências de interação)

| Meta qualitativa | Tarefa associada | Evidência observável na interação | Justificativa no domínio |
| :--- | :---: | :--- | :--- |
| **Compreensão do *trade-off*** | P01 / T01 | O usuário consegue relacionar visualmente os eixos de tempo e memória no gráfico sem necessitar de explicações adicionais sobre o significado das grandezas. | Decisões técnicas demandam ponderar velocidade versus consumo de recursos de infraestrutura. |
| **Auditabilidade e transparência de bancada** | P02 / T02 | O usuário localiza e interpreta com facilidade as informações metodológicas do teste (hardware, kernel e flags), julgando sua adequação para citação científica. | No contexto acadêmico, dados sem parâmetros de bancada explícitos carecem de credibilidade metodológica. |
| **Clareza na parametrização de filtros** | P01 e P02 | O usuário identifica e manipula com autonomia os seletores de linguagens e escalas sem gerar confusão visual na densidade do gráfico. | Catálogos técnicos densos demandam isolamento rápido de séries de interesse. |

###### 3.2 Quantitativas (Indicadores operacionais)

| ID | Meta de Nielsen | Métrica operacional | Tarefa | Limiar planejado | Justificativa do limiar | Como medir |
| :-: | :--- | :--- | :-: | :-: | :--- | :--- |
| **MU01** | Baixa taxa de erros | Conclusão autônoma da identificação da linguagem mais rápida | T01 | **100% de sucesso** (sem intervenção) | T01 é a tarefa central de P01; qualquer falha na identificação básica de uma métrica invalida o objetivo primário da ferramenta. | Registro na planilha de observação do teste. |
| **MU02** | Eficiência | Tempo decorrido do catálogo até a resposta comparativa | T01 | **$\le$ 45 segundos** | Em reuniões de alinhamento técnico, o Tech Lead necessita de respostas rápidas; 45s representa uma redução drástica frente às pesquisas manuais em fóruns. | Cronômetro da seleção do algoritmo até a leitura do dado. |
| **MU03** | Baixa taxa de erros | Sucesso na cópia do script e auditoria do hardware | T02 | **100% de sucesso** (sem intervenção) | A falha em obter a receita de reprodutibilidade impede o pesquisador de replicar o experimento no laboratório. | Verificação de clique no botão *Copy* e abertura das especificações. |
| **MU04** | Eficiência | Tempo decorrido da tela inicial até a cópia da receita Guix | T02 | **$\le$ 60 segundos** | Tarefa exploratória envolvendo navegação de abas e inspeção textual; 60s é compatível com o tempo de leitura técnica concentrada. | Cronômetro do acesso inicial até a confirmação de cópia do script. |
| **MU05** | Satisfação | Facilidade percebida imediata (Escala de 1 a 5) | T01 e T02 | **Média $\ge$ 4.0** | Alinhado aos instrumentos padronizados das Entregas 12 e 14. Em uma escala de 1 a 5, nota $\ge$ 4.0 garante percepção positiva sem distorções de amostragem. | Pergunta padronizada aplicada imediatamente após cada tarefa. |

> **Nota metodológica sobre a amostragem:** Em conformidade com o planejamento de avaliação formativa com amostra pequena (*proxy* de 2 participantes), as metas de eficácia foram operacionalizadas como *conclusão autônoma sem ajuda externa* (100% dos participantes observados), eliminando limiares fracionários estatisticamente indistinguíveis (como 90% ou 95%).

###### 3.3 Priorização das metas de usabilidade (Critérios de Nielsen)

A priorização das cinco metas de usabilidade de Nielsen decorre da caracterização das personas (Rafael — P01 e Mariana — P02), da frequência eventual de uso da plataforma e dos riscos associados a decisões equivocadas:

1. **Eficiência (Prioridade Máxima):**
   * *Justificativa:* Os usuários-alvo (líderes técnicos e pesquisadores) são profissionais especializados que realizam análises sob forte pressão de prazos (sprints de entrega ou prazos de submissão de artigos). Uma vez na tela, a interface deve permitir isolar parâmetros e extrair dados em segundos, sem cliques excessivos ou etapas intermediárias desnecessárias.
2. **Baixa Taxa de Erros (Prioridade Alta):**
   * *Justificativa:* Decisões arquiteturais baseadas em leituras distorcidas de desempenho geram sobrecustos severos de infraestrutura ou rejeição de manuscritos científicos. A interface deve prevenir erros de interpretação através de escalas cartesianas bem identificadas e legendas consistentes.
3. **Facilidade de Aprendizado (Prioridade Média):**
   * *Justificativa:* Sendo uma plataforma web de acesso eventual e irrestrito (sem treinamentos ou manuais), a curva inicial de aprendizado deve ser próxima de zero para quem já domina conceitos de computação. A interface precisa apoiar-se em convenções consagradas da web e da visualização de dados.
4. **Satisfação do Usuário (Prioridade Média):**
   * *Justificativa:* Profissionais técnicos valorizam sistemas objetivos, de alto contraste visual e sem ruídos visuais. Uma experiência satisfatória consolida a ferramenta como referência confiável para consulta recorrente.
5. **Facilidade de Memorização (Prioridade Secundária):**
   * *Justificativa:* Embora as tarefas sejam executadas de maneira periódica (a cada novo projeto ou pesquisa), a simplicidade da arquitetura de informação (catálogo $\rightarrow$ visualizador $\rightarrow$ abas de código/hardware) e a baixa profundidade de navegação tornam a interface autoexplicativa, reduzindo a dependência de memória procedimental de longo prazo.

---

###### 4. Ciclo de engenharia de usabilidade (Aplicação de Mayhew)

O desenvolvimento do BMML adota o **Ciclo de Engenharia de Usabilidade de Deborah Mayhew**, estruturado em três fases fundamentais orientadas à iteração contínua:

1. **Fase 1 — Análise de Requisitos (Entregas 1 a 5 e 8):**
   * *Escopo e Atividades:* Mapeamento do perfil dos usuários (Personas P01 e P02 na Entrega 3), análise aprofundada das tarefas humanas de análise experimental (HTA, GOMS e CTT na Entrega 5), delimitação das capacidades/restrições da plataforma e definição formal das metas de usabilidade quantitativas e qualitativas (Entrega 8).
   * *Base do Ciclo:* Estabelece os critérios objetivos que serão utilizados como régua de aprovação ou rejeição nas fases subsequentes.
2. **Fase 2 — Projeto, Prototipação e Avaliações Formativas Sucessivas:**
   * **Nível 1: Projeto Essencial / Conceitual (Entrega 6):** Elaboração de protótipos de baixa fidelidade em papel (P01 a P04) e realização de *walkthrough* formativo para validar os fluxos macro de navegação e a metáfora conceitual da ferramenta.
     * *Retorno iterativo do nível:* Caso a avaliação do protótipo em papel revelasse falha estrutural (ex.: incapacidade de localizar o comparativo ou incompreensão do modelo mental), o fluxo retornaria imediatamente à reengenharia dos requisitos conceituais antes de qualquer avanço digital.
   * **Nível 2: Padrões de Telas e Diálogos (Entregas 7, 9 e 10):** Estabelecimento do modelo semiótico de comunicação, diagramas MoLIC de diálogo usuário-sistema (M01 e M02) e definição do guia de estilo (tema escuro, contraste WCAG AA, tipografia Inter/JetBrains Mono).
     * *Retorno iterativo do nível:* Se a modelagem MoLIC detectasse quebras de diálogo, mensagens ambíguas ou ausência de rotas de recuperação, o padrão de interação seria corrigido antes da confecção do protótipo detalhado.
   * **Nível 3: Projeto Detalhado (Entrega 11):** Construção do protótipo de telas navegável de alta fidelidade no Figma (telas F01 a F07), integrando componentes finais, tabelas dinâmicas, controles de eixos e paleta de cores.
3. **Fase 3 — Avaliações de Usabilidade e Refinamento de Engenharia (Entregas 12 a 14):**
   * **Inspeção Especialista (Entrega 13):** Aplicação sistemática das 10 Heurísticas de Nielsen sobre o protótipo digital para detecção preventiva de problemas ergonômicos e inconsistências operacionais.
   * **Observação de Usuários (Entrega 14):** Execução de testes empíricos com participantes *proxy* executando as tarefas neutras UT01 a UT04 sob o protocolo DECIDE, mensurando o atingimento das metas MU01 a MU05.
   * *Retorno iterativo da fase:* Caso métricas de eficiência ou taxa de erros sejam violadas nos testes práticos (como o atrito observado pelo esforço de cliques manuais na tarefa UT02), o ciclo determina o retorno ao nível correspondente de projeto detalhado (gerando as recomendações de inclusão de atalhos "Select All / Deselect All" na tabela de séries para a próxima iteração da interface).

---

###### Checklist

* [x] Princípios gerais divididos explicitamente em princípios de negócio/domínio e princípios de interface.
* [x] Priorização elaborada exclusivamente a partir das 5 metas de usabilidade de Nielsen (justificadas por personas e contexto).
* [x] Métricas quantitativas MU01 a MU05 associadas a metas de Nielsen, com limiares explicitamente justificados.
* [x] Escala de satisfação unificada em 1 a 5, compatibilizada com os instrumentos das Entregas 12 e 14.
* [x] Metas de eficácia operacionalizadas para pequenas amostras (100% de conclusão sem ajuda).
* [x] Meta de "Auditabilidade" delimitada à qualidade e clareza da interação na interface.
* [x] Segurança e privacidade formuladas sem afirmações de risco absoluto ("sem risco de vazamento").
* [x] Uso da fonte JetBrains Mono justificado estritamente para elementos de código e tabelas de dados.
* [x] Ciclo de Mayhew descrito detalhadamente em seus três níveis, com as etapas de retorno iterativo explicitadas.
* [x] Relação entre as entregas anteriores e as etapas do ciclo de engenharia de usabilidade formalizada.
