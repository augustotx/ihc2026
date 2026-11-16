### Entrega 12 — Planejamento da avaliação de usabilidade (DECIDE)

**Data:** 16/11/2026

**Status:** 🟩 concluída

**Responsabilidade:** 1 solução por equipe

#### Objetivo da atividade

Planejar a avaliação antes de executá-la, ligando perguntas de avaliação a métodos, participantes, tarefas, métricas, aspectos práticos, ética e forma de análise.

#### O que está sendo avaliado

Esta avaliação investiga exclusivamente a **qualidade da interação e da interface** (clareza na leitura do gráfico, facilidade de filtragem, localização de artefatos de reprodutibilidade e compreensão do hardware). A avaliação não investiga o desempenho técnico dos algoritmos ou dos compiladores do TCC. Os dados apresentados no visualizador correspondem aos resultados reais consolidados nas baterias de testes da ferramenta BMML.

---

#### A. Método DECIDE

| Etapa | Aplicação no projeto |
| :--- | :--- |
| **D — Determine the goals** | Avaliar se desenvolvedores e pesquisadores conseguem comparar o desempenho entre linguagens no gráfico/tabela e localizar as informações de reprodução e hardware sem dificuldades. |
| **E — Explore the questions** | 1. O usuário consegue identificar a linguagem mais eficiente sem apoio?<br />2. Os filtros de séries e escalas logarítmicas são intuitivos?<br />3. A pesquisadora localiza os dados da máquina física e o comando Guix com facilidade? |
| **C — Choose the evaluation paradigm and techniques** | Combinação de dois métodos complementares e práticos:<br />1. **Avaliação Heurística** (inspeção pelos próprios membros da equipe baseada nas 10 heurísticas de Nielsen);<br />2. **Teste de Usabilidade com Observação** (observação de participantes realizando tarefas guiadas com pensamento em voz alta / *think-aloud*). |
| **I — Identify the practical issues** | Participantes: 3 a 5 estudantes/profissionais de computação (perfil dos usuários-alvo).<br />Ambiente: Presencial em notebook ou remoto via Google Meet com compartilhamento de tela.<br />Piloto: Teste prévio entre os dois integrantes da equipe para calibrar instruções. |
| **D — Decide how to deal with ethical issues** | Aplicação de Termo de Consentimento Livre e Esclarecido (TCLE) informando que a interface está sendo avaliada (e não o participante), com garantia de anonimato e liberdade de interromper a sessão a qualquer momento. |
| **E — Evaluate, interpret and present the data** | Registro de taxa de sucesso (concluiu / com ajuda / não concluiu), tempo por tarefa, contagem de dúvidas e nota subjetiva de facilidade (escala 1 a 5), compilando problemas identificados por grau de severidade. |

---

#### B. Perguntas de avaliação

| ID | Pergunta | Método | Métrica/evidência | Critério esperado |
| :--- | :--- | :--- | :--- | :--- |
| **QA01** | O usuário consegue identificar a linguagem de menor tempo no benchmark sem ajuda? | Observação de Teste | Taxa de conclusão e pedidos de ajuda | 100% de sucesso sem intervenção do avaliador |
| **QA02** | O usuário entende como aplicar a escala logarítmica e desmarcar séries na tabela? | Observação de Teste | Tempo de execução e erros de clique | Concluir ajuste em menos de 45 segundos |
| **QA03** | A pesquisadora consegue encontrar a CPU e RAM da máquina de testes? | Observação de Teste | Navegação até o menu `About` | Localizar em até 30 segundos via menu superior |
| **QA04** | Existem falhas de visibilidade do estado do sistema ou feedback de cópia? | Avaliação Heurística | Violação da Heurística 1 (Visibilidade do estado) | Zero problemas de severidade alta/catastrófica |

---

#### C. Escopo e participantes

| Item | Planejamento |
| :--- | :--- |
| **Perfis** | Desenvolvedores de software, engenheiros e estudantes de computação (representando Rafael Mendes e Mariana Costa). |
| **Critérios de inclusão/exclusão** | **Inclusão:** Conhecimento básico em programação e leitura de gráficos cartesianos.<br />**Exclusão:** Pessoas sem familiaridade com termos básicos de computação (CPU, RAM, compilador). |
| **Nº de participantes** | 3 a 4 participantes externos + 2 integrantes da equipe para inspeção heurística. |
| **Ambiente** | Presencial em laboratório/sala de estudos ou remoto via Google Meet. |
| **Dispositivo** | Notebook ou computador desktop com monitor e mouse/trackpad. |
| **Protótipo/versão** | Protótipo navegável com as telas consolidadas da interface BMML. |
| **Teste piloto** | Realizado entre Augusto e João Pedro antes do primeiro participante externo para validar o tempo e a clareza do roteiro. |

---

#### D. Lista de tarefas de avaliação

| ID | Cenário neutro entregue ao usuário | Objetivo oculto da avaliação | Critério de sucesso | Tempo-limite (se houver) |
| :--- | :--- | :--- | :--- | :--- |
| **UT01** | *"Você precisa escolher a linguagem mais rápida no teste MergeSort. Acesse o benchmark e identifique qual linguagem obteve o menor tempo médio."* | Avaliar navegação inicial (F01 → F02) e leitura direta da tabela de médias (M01). | Dizer o nome correto da linguagem mais rápida. | 60 segundos |
| **UT02** | *"No gráfico do MergeSort, deixe visíveis apenas as linguagens C e Rust e ative a escala logarítmica no eixo Y."* | Avaliar uso dos checkboxes na tabela (F03) e do toggle de escala `Log Y` (F02). | Gráfico atualizado exibindo apenas as duas séries em escala log. | 90 segundos |
| **UT03** | *"Você precisa auditar a máquina onde os testes rodaram. Descubra qual é o modelo do processador e o total de memória RAM utilizada."* | Avaliar a descoberta do acesso ubíquo `About` no cabeçalho (F06 / M02). | Informar "AMD Ryzen 5 3600" e "32GB RAM". | 45 segundos |
| **UT04** | *"Copie o comando de terminal necessário para reproduzir este ambiente experimental na sua máquina."* | Avaliar a localização da aba de reprodutibilidade e o botão `Copy` do script Guix (F07 / M02). | Clicar em `Copy` e receber a confirmação visual de cópia. | 60 segundos |

---

#### E. Instrumentos

* [Modelo de termo de consentimento](../instrumentos/termo_consentimento_modelo.md)
* [Roteiro de teste](../instrumentos/roteiro_teste_usabilidade.md)
* [Planilha de observação](../instrumentos/planilha_observacao_modelo.md)
* [Formulário de avaliação heurística](../instrumentos/formulario_heuristica_modelo.md)
* [Questionario_pos_teste](../instrumentos/questionario_pos_teste.md)

---

#### F. Plano de análise

Definições prévias para a consolidação dos dados:

* **Sucesso total:** O participante concluiu a tarefa sozinho, sem hesitação grave.
* **Sucesso parcial:** O participante concluiu após pedir esclarecimento sobre o que fazer.
* **Falha:** O participante desistiu ou executou ação incorreta sem conseguir se recuperar.
* **Métricas coletadas:**
  * Tempo decorrido em cada tarefa (em segundos);
  * Número de cliques ou tentativas incorretas;
  * Escala de facilidade percebida (Single Ease Question - SEQ de 1 a 5 aplicada após cada tarefa).
* **Classificação de problemas:** Severidade de 0 a 4 (0 = falso positivo; 1 = cosmético; 2 = simples; 3 = grave; 4 = catastrófico/impede a tarefa).
* **Comparação com metas:** Comparar a taxa de sucesso com a meta estabelecida na Entrega 8 (mínimo de 80% de conclusão sem erros graves).

---

#### Checklist

* [x] As seis etapas DECIDE foram contextualizadas, não apenas expandidas por sigla.
* [x] Perguntas de avaliação têm método e evidência correspondentes.
* [x] O plano distingue avaliação de IHC de avaliação técnica/científica do TCC.
* [x] Dados ou processamentos simulados no protótipo estão declarados.
* [x] Tarefas vêm de objetivos/cenários relevantes.
* [x] Critérios de sucesso foram definidos antes da coleta.
* [x] Questões práticas e éticas estão resolvidas.
* [x] Instrumentos estão prontos antes da Entrega 13/14.
* [x] Plano diz como dados serão analisados e apresentados.
