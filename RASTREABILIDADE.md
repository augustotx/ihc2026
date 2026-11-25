##### Matriz de rastreabilidade de IHC — Equipe 04 (BMML)

Esta matriz documenta formalmente a evolução do projeto ao longo de todo o semestre, demonstrando a passagem da **contribuição técnica do TCC** para os **cenários de problema**, tarefas, modelos conceituais, protótipos e avaliações empíricas.

--------------------------------------------------------------------------------

###### 1. Derivação do escopo de IHC a partir do TCC

| Elemento | Registro da equipe | Evidência / Justificativa | Estado |
| :--- | :--- | :--- | :--- |
| **Tema do TCC** | Análise comparativa de desempenho e consumo de recursos entre linguagens de programação (C, Rust, Zig, Python, etc.) em ambiente determinístico. | Documento de proposta do TCC / Projeto BMML. | Definido |
| **Resultado técnico esperado** | Conjunto padronizado de benchmarks executados sob contêineres reprodutíveis (GNU Guix), gerando métricas de tempo de CPU e pico de memória RAM (RSS). | Scripts de calibração, datasets brutos em CSV e receitas de build. | Definido |
| **O TCC previa interface?** | Não (originalmente previa apenas scripts de automação CLI e geração estática de logs). | Escopo inicial estritamente focado em linha de comando e testes de bancada. | Definido |
| **Capacidade/contribuição central** | Coleta automatizada e rigorosa de métricas em condições físicas idênticas e isoladas, com reprodutibilidade garantida por software determinístico. | Artigos científicos sobre reprodutibilidade e ambiente GNU Guix. | Definido |
| **Possíveis beneficiários / stakeholders** | Desenvolvedores de software de sistemas, arquitetos de software (Tech Leads), pesquisadores acadêmicos e estudantes de computação. | Levantamento inicial de partes interessadas (Entrega 1). | F (Fato) |
| **Usuário escolhido para IHC** | **Rafael Mendes** (Tech Lead / Desenvolvedor experiente — Persona Primária P01) e **Mariana Costa** (Pesquisadora Acadêmica — Persona Secundária P02). | Justificado na Entrega 3: representam os dois polos centrais de uso dos dados (decisão corporativa e validação científica). | F (Fato) |
| **Objetivo principal do usuário** | Comparar o trade-off tempo vs. memória entre linguagens de forma confiável e auditar o ambiente de hardware/compilação para fundamentar decisões técnicas ou artigos. | Cenários C01 e C02 (Entrega 4) e Análise de Tarefas T01 e T02 (Entrega 5). | F (Fato) |
| **Contexto de uso adotado** | Estação de trabalho desktop em ambiente profissional ou laboratorial, navegando em tela ampla para análise densa de dados numéricos e gráficos. | Descrição do contexto físico e social (Entrega 3 e 4). | F (Fato) |
| **Interface / recorte de IHC** | Aplicação web responsiva com foco em desktop (BMML Viewer), provendo catálogo de algoritmos, gráfico de dispersão cartesiano, tabela dinâmica e painel de auditoria de código/ambiente. | Especificação semiótica (Entrega 9/10) e protótipo de telas (Entrega 11). | Definido |
| **Relação com o TCC** | **Protótipo demonstrativo e camada de comunicabilidade:** transforma dados brutos e scripts herméticos em representações visuais interativas e auditáveis para terceiros. | Justificativa metodológica da disciplina de IHC. | Definido |

--------------------------------------------------------------------------------

###### 2. Registro de hipóteses e lacunas da Entrega 1

| ID | Afirmação / Dúvida inicial | Tipo | Por que importa | Como/onde investigar | Evidência obtida | Estado atual | Impacto no projeto |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **H01** | Desenvolvedores preferem interfaces gráficas em vez de ler relatórios brutos de terminal. | H | Define se a interface web tem valor real ou se uma CLI simples bastaria. | Entregas 2, 3 e 14. | Na Entrega 2 e nos testes (Entrega 14), confirmou-se que gráficos cartesianos de dispersão reduzem o tempo de compreensão do trade-off para menos de 30s. | **Sustentada** | Foco mantido no gráfico de dispersão com toggles paramétricos. |
| **H02** | Existem ferramentas consolidadas no mercado que comparam essas linguagens com facilidade. | ? | Mapear se o BMML é redundante ou inovador. | Entrega 2 (Análise de Concorrentes). | Análise do *Debian Benchmark Game* e *Rosetta Code*: as ferramentas são antigas, não possuem gráficos interativos, não têm filtros dinâmicos e não expõem ambientes determinísticos modernos. | **Refinada** | O BMML se diferenciou por oferecer gráficos interativos e receita do GNU Guix em um clique. |
| **H03** | Desenvolvedores e pesquisadores precisam dos mesmos dados e interações na interface. | H | Determina se o sistema precisaria de múltiplos níveis de acesso ou telas distintas. | Entregas 3 e 4. | Rafael (P01) foca na decisão rápida via tabela e gráfico; Mariana (P02) exige auditar flags e scripts. Ambos usam a mesma tela base, mas navegam em abas complementares. | **Refinada** | Criação das abas complementares "Visualizador" e "Código/Reprodutibilidade" sem segregação de login. |
| **H04** | A calibração de hardware precisa estar visível o tempo todo ou sob demanda? | ? | Impacta na densidade visual da tela principal. | Entregas 5, 8 e 11. | A análise de tarefas e o MoLIC mostraram que a verificação de hardware é eventual/auditoria. O acesso ubíquo via modal About atende sem poluir o gráfico. | **Sustentada** | Implementação do botão About no cabeçalho abrindo modal sobreposto. |

--------------------------------------------------------------------------------

###### 3. Rastreabilidade entre contribuição técnica, necessidades e artefatos

| ID | Capacidade do TCC | Necessidade / Problema | Persona | Cenário Problema | Tarefa (HTA/GOMS/CTT) | Signos / Conceitos | MoLIC | Tela Figma | Heurística (Entrega 13) | Tarefa no Teste | Decisão / Melhoria |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **R01** | Extração de tempo de CPU de algoritmos. | Necessidade de comparar velocidade entre linguagens para decisão técnica. | P01 (Rafael) | C01 | T01 (Subtarefa 1 e 2) | `tempo_execucao`, `media_consolidada`, `benchmark` | M01 (O01) | F01, F02, F03 | OK (H1, H2, H4) | **UT01** | Tabela ordenada por padrão pelo menor tempo médio para resposta visual imediata. |
| **R02** | Extração de consumo de memória RAM (RSS). | Avaliar o impacto de alocação de memória sob restrição de hardware. | P01 (Rafael) | C01 | T01 (Subtarefa 2 e 3) | `memoria_ram`, `escala_eixo` (linear/log) | M01 (O01) | F02, F03 | OK (H3) | **UT02** | Switches diretos de escala linear/logarítmica para evitar sobreposição de pontos discrepantes. |
| **R03** | Filtragem paramétrica de séries no dataset. | Isolar duas linguagens específicas sem a poluição de outras 8 curvas concorrentes. | P01 / P02 | C01, C02 | T01 (2.1) / T02 (2.1) | `linguagem`, `serie_dados`, `selecao_candidatas` | M01 (O01) | F03 | **V01 (H5)** e **V02 (H7)** | **UT02** | Adicionar atalhos "Select All / Deselect All" e bloquear gráfico vazio para sanar atrito observado em UT02. |
| **R04** | Registro formal de hardware físico e OS. | Garantir a credibilidade científica dos dados em publicação acadêmica. | P02 (Mariana) | C02 | T02 (Subtarefa 2) | `ambiente_execucao`, `hardware_cpu`, `memoria_total`, `kernel_so` | M02 (O02) | F06 | **V03 (H3)** | **UT03** | Modal permanente no topo; permitir fechar no backdrop e na tecla Esc para cumprir H3. |
| **R05** | Receitas de contêineres declarativos (GNU Guix). | Permitir que o auditor reproduza os experimentos exatos no próprio terminal. | P02 (Mariana) | C02 | T02 (Subtarefa 2) | `receita_guix`, `flags_otimizacao` (-O3), `codigo_fonte` | M02 (O02) | F04, F07 | OK (H1, H7) | **UT04** | Manter o botão Copy integrado ao bloco de código com feedback visual imediato. |
| **R06** | Geração e consolidação de datasets brutos de medições empíricas. | Obter medições completas e referência bibliográfica para citação em artigo científico. | P02 (Mariana) | C02 | T02 (Subtarefa 3) | `dataset_bruto` (.csv), `referencia_bibtex` | M02 (O02) | F04, F07 | OK (H1, H7) | **UT04** | Disponibilizar download direto em CSV e botão de cópia de citação em um clique com confirmação visual. |

--------------------------------------------------------------------------------

###### 4. Rastreabilidade de padrões de interface

| ID da tela / fluxo | Padrão de interface | Tarefa que justifica | Informação / Ação principal | Evidência de necessidade | Artefatos relacionados |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **F01** | Catálogo em Grade (Cards) com Filtro por Categoria | T01 / T02 (Achar algoritmo) | Exibe os 13 benchmarks agrupados por tipo de carga (CPU-bound vs. Memory-bound). | Previne sobrecarga cognitiva e facilita a busca rápida sem exigir paginação extensa. | C01, C02, HTA-1.2, MoLIC Pré-condição. |
| **F02 / F03** | Visualizador Cartesiano com Tabela de Séries Sincronizada | T01 (Comparar trade-off) | Gráfico de dispersão interativo com alternância de eixos e tabela inferior de médias com controles de seleção. | A literatura de IHC e a Entrega 2 mostram que gráficos mostram correlações e tabelas dão precisão numérica. | T01, M01 (Comparar Desempenho de Linguagens), Avaliação Heurística, UT01, UT02. |
| **F04 / F05 / F07** | Painel de Código com Ações de Cópia Assistida | T02 (Auditar e reproduzir) | Visualização de código (main.zig), flags (-O3) e scripts de contêiner com botão Copy. | Elimina erros motores de transcrição manual de comandos longos no terminal. | T02, M02 (Inspecionar Reprodutibilidade e Código-Fonte), UT04. |
| **F06** | Diálogo Modal Sobreposto (About) | T01 / T02 (Checar ambiente) | Exibição sob demanda da CPU Ryzen, 32GB RAM e Kernel sem desviar da análise em andamento. | Evita navegação para outra página, preservando o estado dos filtros e gráficos já ajustados. | T01-4, T02-2, MoLIC Acesso Ubíquo (About BMML), UT03. |

--------------------------------------------------------------------------------

###### 5. Registro de mudanças de escopo e evolução das decisões

| Data | O que mudou no projeto | Evidência / Feedback que motivou | Artefatos afetados | Responsável |
| :--- | :--- | :--- | :--- | :--- |
| **20/10/2026** | **Clarificação da Persona P01:** Rafael foi formalizado como *Tech Lead* (Desenvolvedor Sênior com papel decisor), harmonizando a Entrega 1 e a Entrega 3. | Feedback do Professor na Entrega 03 alertando para aparente contradição entre "desenvolvedor" e "gestor". | Entrega 3 (Personas) e Rastreabilidade. | João Pedro Bazoli Palma |
| **28/10/2026** | **Inclusão obrigatória de filtros e reprodutibilidade:** Incorporação formal de filtros de séries e comandos do Guix como requisitos centrais. | Feedback da Entrega 02 apontando que os concorrentes pecavam pela falta de filtros e opacidade metodológica. | Entrega 2, Entrega 5 (Tarefas) e MoLIC. | Augusto Pereira Teixeira |
| **12/11/2026** | **Adoção de Tema Escuro Estrito (Dark Mode):** Padronização visual em tons de cinza/preto (#121214) com pontos coloridos saturados. | Princípios de Design (Entrega 10) visando conforto visual em análises prolongadas e contraste WCAG AA. | Entrega 10 e Telas Figma (F01 a F07). | João Pedro Bazoli Palma |
| **16/11/2026** | **Planejamento de atalhos "Select/Deselect All":** Decisão de implementar atalhos de seleção rápida na tabela de séries. | Inspeção Heurística (V02 - H7) e confirmação empírica nos testes com usuários (UT02 / AU01). | Entrega 13, Entrega 14 e Plano de Evolução. | João Pedro Bazoli Palma |
| **16/11/2026** | **Ajuste de fechamento do Modal About:** Decisão de permitir fechar o modal clicando no backdrop ou via tecla Esc. | Inspeção Heurística (V03 - H3) e hesitação motora observada no participante U02 no teste de usabilidade. | Entrega 13, Entrega 14 e Plano de Evolução. | Augusto Pereira Teixeira |
| **21/11/2026** | **Reestruturação e formalização de HTA e GOMS:** Correção do nó 0 de T01 (desacoplamento da T02), eliminação de nós de filho único e inserção de operadores cognitivos de verificação nos métodos GOMS. | Feedback do Professor na Entrega 05. | Entrega 05 (HTA, GOMS, CTT). | João Pedro Bazoli Palma |
| **23/11/2026** | **Padronização dos Signos Conceituais:** Substituição de nomenclaturas de componentes de interface/widgets por signos de domínio e aplicação estáveis. | Feedback do Professor na Entrega 09 e Entrega 10. | Entrega 09 (Signos) e Entrega 10 (MoLIC). | Augusto Pereira Teixeira |
| **24/11/2026** | **Completude formal das conversas MoLIC:** Inclusão explícita de `gco`/`gcc`, segregação estrita de `d:` e `u:` nas cenas e modelagem de ruptura real com recuperação apoiada no M02. | Feedback do Professor na Entrega 10. | Entrega 10 (MoLIC M01 e M02). | João Pedro Bazoli Palma |

--------------------------------------------------------------------------------

###### Checklist de conformidade da rastreabilidade

* [x] A transição da contribuição técnica do TCC para a interface de IHC está plenamente justificada.
* [x] As hipóteses iniciais H01 a H04 foram atualizadas com o conhecimento obtido nas entregas posteriores.
* [x] A tabela principal conecta Capacidade do TCC → Persona → Cenário → Tarefa → MoLIC → Tela → Heurística → Teste de Usabilidade.
* [x] Todos os identificadores são estáveis (P01, C01, T01, M01, F01, UT01, etc.).
* [x] Os padrões de interface (Catálogo, Dashboard, Código, Modal) possuem justificativa de tarefa.
* [x] As mudanças de escopo e respostas aos feedbacks dos professores foram devidamente registradas no histórico.
