#### Entrega 12 — Planejamento da avaliação de usabilidade (DECIDE)

**Data:** 16/11/2026

**Status:** 🟩 concluída

**Responsabilidade:** 1 solução por equipe

###### Objetivo da atividade

Planejar a avaliação antes de executá-la, ligando perguntas de avaliação a métodos, participantes, tarefas, métricas, aspectos práticos, ética e forma de análise.

###### O que está sendo avaliado

Esta avaliação investiga exclusivamente a **qualidade da interação e da interface** (clareza na leitura do gráfico, facilidade de filtragem, localização de artefatos de reprodutibilidade e compreensão do hardware). A avaliação não investiga o desempenho técnico dos algoritmos ou dos compiladores do TCC. Os dados apresentados no visualizador correspondem aos resultados reais consolidados nas baterias de testes da ferramenta BMML.

--------------------------------------------------------------------------------

###### A. Método DECIDE

| Etapa | Aplicação no projeto |
| ------ | ------ |
| **D — Determine the goals** | Avaliar se desenvolvedores e pesquisadores conseguem comparar o desempenho entre linguagens no gráfico/tabela e localizar as informações de reprodução e hardware sem dificuldades. |
| **E — Explore the questions** | 1. O usuário consegue identificar a linguagem de menor tempo no benchmark sem apoio?<br />2. Os filtros de séries e escalas logarítmicas são intuitivos?<br />3. A pesquisadora localiza os dados da máquina física e o comando Guix com facilidade?<br />4. Quais violações das 10 Heurísticas de Nielsen existem na interface e qual a sua severidade? |
| **C — Choose the evaluation paradigm and techniques** | Combinação de dois métodos complementares e práticos:<br />1. **Avaliação Heurística** (inspeção analítica individual pelos dois membros da equipe baseada nas 10 heurísticas de Nielsen, com posterior consolidação);<br />2. **Teste de Usabilidade com Observação** (observação de participantes realizando tarefas guiadas com pensamento em voz alta / *think-aloud*). |
| **I — Identify the practical issues** | Participantes: 2 a 4 participantes externos (estudantes do 8º ciclo atuando como *proxy* de P01 e P02).<br />Papéis: João Pedro atua como moderador (condução neutra) e Augusto como observador/anotador.<br />Ambiente: Presencial em desktop/notebook (1920×1080) com mouse e teclado físico.<br />Piloto: Sessão prévia com 1 participante externo ao planejamento para calibrar tempo e clareza do roteiro. |
| **D — Decide how to deal with ethical issues** | Aplicação de Termo de Consentimento Livre e Esclarecido (TCLE) informando que a interface está sendo avaliada (e não o participante), com dados de teste anonimizados por códigos (U01, U02), garantia de confidencialidade e liberdade de interromper a sessão a qualquer momento. |
| **E — Evaluate, interpret and present the data** | Registro de taxa de eficácia (sucesso sem ajuda / sucesso com ajuda / falha), tempo por tarefa (indicador exploratório sob *think-aloud*), contagem de erros/hesitações e nota subjetiva de facilidade percebida (escala de 1 a 5), consolidando problemas por grau de severidade e limitações amostrais. |

--------------------------------------------------------------------------------

###### B. Perguntas de avaliação

| ID | Pergunta | Método | Métrica/evidência | Critério esperado |
| ------ | ------ | ------ | ------ | ------ |
| **QA01** | O usuário consegue identificar a linguagem de menor tempo no benchmark sem ajuda? | Observação de Teste | Taxa de conclusão e pedidos de ajuda (MU01) | 100% dos participantes concluem sem intervenção |
| **QA02** | O usuário entende como aplicar a escala logarítmica e desmarcar séries na tabela? | Observação de Teste | Tempo de execução e erros de clique | Concluir ajuste em até 60 segundos |
| **QA03** | A pesquisadora consegue encontrar a CPU e RAM da máquina de testes? | Observação de Teste | Navegação até o menu About e tempo decorrido | Localizar em até 45 segundos via menu superior |
| **QA04** | Quais violações das 10 Heurísticas de Nielsen existem nos fluxos da interface? | Avaliação Heurística | Mapeamento por heurística (H1–H10) e grau de severidade (0–4) | Zero problemas de severidade 4 (catastrófica) e plano de correção para severidades 2 e 3 |

--------------------------------------------------------------------------------

###### C. Escopo e participantes

| Item | Planejamento |
| ------ | ------ |
| **Perfis** | Desenvolvedores de software e estudantes concluintes de Ciência da Computação (8º ciclo) atuando como *proxy* das personas Rafael Mendes (P01) e Mariana Costa (P02). |
| **Critérios de inclusão/exclusão** | **Inclusão:** Conhecimento em linguagens compiladas (C, Rust), interpretação de gráficos cartesianos e familiaridade com terminal Linux.<br />**Exclusão:** Pessoas sem familiaridade com conceitos básicos de computação (CPU, RAM, compilador) ou que participaram do design do protótipo. |
| **Nº de participantes** | 2 a 4 participantes externos (*proxy*) para o teste de usabilidade + 2 integrantes da equipe como avaliadores heurísticos independentes. |
| **Ambiente** | Presencial em ambiente controlado de laboratório ou estação de trabalho silenciosa. |
| **Dispositivo** | Computador desktop/notebook com monitor padrão, mouse físico e teclado. |
| **Protótipo/versão** | Protótipo de alta fidelidade navegável com as telas consolidadas da interface BMML (F01 a F07). |
| **Teste piloto** | Realizado com 1 estudante externo ao planejamento antes das sessões oficiais, para validar se as tarefas e métricas permitem responder QA01–QA04 (dados do piloto descartados da amostra final). |

--------------------------------------------------------------------------------

###### D. Lista de tarefas de avaliação

| ID | Cenário neutro entregue ao usuário | Objetivo oculto da avaliação | Critério de sucesso | Tempo-limite (se houver) |
| ------ | ------ | ------ | ------ | ------ |
| **UT01** | *"Você precisa escolher a linguagem mais rápida no teste MergeSort. Acesse o benchmark e identifique qual linguagem obteve o menor tempo médio."* | Avaliar navegação inicial (F01 → F02) e leitura direta da tabela de médias (M01 / MU01 / MU02). | Dizer o nome correto da linguagem mais rápida sem ajuda externa. | 45 segundos |
| **UT02** | *"No gráfico do MergeSort, deixe visíveis apenas as linguagens C e Rust e ative a escala logarítmica no eixo Y."* | Avaliar uso dos checkboxes na tabela (F03) e do toggle de escala Log Y (F02). | Gráfico atualizado exibindo apenas as duas séries em escala log. | 60 segundos |
| **UT03** | *"Você precisa auditar a máquina onde os testes rodaram. Descubra qual é o modelo do processador e o total de memória RAM utilizada."* | Avaliar a descoberta do acesso ubíquo About no cabeçalho (F06 / M02). | Informar "AMD Ryzen 5 3600" e "32GB RAM". | 45 segundos |
| **UT04** | *"Copie o comando de terminal necessário para reproduzir este ambiente experimental na sua máquina."* | Avaliar a localização da aba de reprodutibilidade e o botão Copy do script Guix (F07 / M02 / MU03 / MU04). | Clicar em Copy e receber a confirmação visual de cópia. | 60 segundos |

--------------------------------------------------------------------------------

###### E. Instrumentos

* [Modelo de termo de consentimento](../instrumentos/termo_consentimento_modelo.md)
* [Roteiro de teste](../instrumentos/roteiro_teste_usabilidade.md)
* [Planilha de observação](../instrumentos/planilha_observacao_modelo.md)
* [Formulário de avaliação heurística](../instrumentos/formulario_heuristica_modelo.md)
* [Questionario_pos_teste](../instrumentos/questionario_pos_teste.md)

--------------------------------------------------------------------------------

###### F. Plano de análise

Definições prévias e critérios para a consolidação dos dados:

* **Sucesso total:** O participante atinge o objetivo da tarefa com autonomia, sem intervenção do moderador.
* **Sucesso parcial:** O participante atinge o objetivo somente após o moderador reler a instrução ou intervir para destravar a navegação.
* **Falha / Abandono:** O participante desiste da tarefa ou fornece resposta incorreta sem conseguir se recuperar.
* **Definição de eventos operacionais:**
  * *Hesitação:* Pausa prolongada (> 5s) ou exploração visual em silêncio procurando onde clicar, sem caracterizar erro de ação.
  * *Erro:* Clique em controle incorreto, desmarcação errada de série ou navegação para área não relacionada ao objetivo.
  * *Ajuda do moderador:* Qualquer intervenção verbal quando o participante expressa bloqueio definitivo (conta como falha para a meta de autonomia).
* **Métricas coletadas:**
  * Taxa de eficácia (percentual de sucesso sem ajuda vs. com ajuda);
  * Tempo decorrido por tarefa em segundos (interpretado como indicador exploratório, considerando a influência da verbalização em voz alta / *think-aloud*);
  * Contagem de cliques e erros de navegação;
  * Facilidade percebida pós-tarefa (escala numérica de 1 = Muito Difícil a 5 = Muito Fácil).
* **Classificação de problemas:** Escala de severidade de Nielsen de 0 a 4 (0 = falso positivo; 1 = cosmético; 2 = simples; 3 = grave; 4 = catastrófico/impede a tarefa).
* **Comparação com metas da Entrega 8:**
  * Eficácia (MU01 e MU03): 100% de conclusão autônoma sem ajuda externa entre os participantes avaliados;
  * Eficiência (MU02 e MU04): tempos medianos de até 45s (UT01) e até 60s (UT04);
  * Satisfação (MU05): facilidade percebida média $\ge 4.0$ na escala de 1 a 5.

--------------------------------------------------------------------------------

###### Checklist

* [x] As seis etapas DECIDE foram contextualizadas, não apenas expandidas por sigla.
* [x] Perguntas de avaliação têm método e evidência correspondentes.
* [x] O plano distingue avaliação de IHC de avaliação técnica/científica do TCC.
* [x] Dados ou processamentos simulados no protótipo estão declarados.
* [x] Tarefas vêm de objetivos/cenários relevantes.
* [x] Critérios de sucesso foram definidos antes da coleta.
* [x] Questões práticas e éticas estão resolvidas.
* [x] Instrumentos estão prontos antes da Entrega 13/14.
* [x] Plano diz como dados serão analisados e apresentados.
