# Entrega 5 — Análise de tarefas: HTA, GOMS e CTT

**Data:** 18/10/2026  
**Status:** 🟨 em andamento  
**Responsabilidade:** Cada integrante modela 1 HTA, 1 GOMS e 1 CTT.

## Objetivo da atividade

Modelar tarefas importantes sob perspectivas complementares: decomposição hierárquica (HTA), estrutura de metas/métodos/operações (GOMS) e relações temporais entre tarefas (CTT). O diagrama deve ser acompanhado de interpretação textual.

## Para projetos cujo TCC não previa interface

Modele **tarefas humanas relacionadas ao uso da contribuição técnica**, e não a implementação interna do algoritmo. Exemplos de boas tarefas para análise:

- investigar uma consulta de baixo desempenho;
- configurar uma análise e selecionar parâmetros;
- submeter um dataset e verificar sua validade;
- acompanhar uma execução demorada;
- comparar dois resultados/modelos;
- interpretar uma recomendação e decidir se a aceita;
- localizar uma execução anterior usando busca/filtros;
- gerar e compartilhar um relatório;
- administrar papéis/permissões quando isso for parte do trabalho real;
- revisar um alerta e registrar uma decisão.

Um CRUD pode gerar tarefas relevantes, mas “cadastrar usuário” só merece modelagem se tiver significado no domínio (papéis, validações, riscos, permissões, dependências).

## Seleção das tarefas

| ID | Tarefa | Persona/cenário de origem | Frequência/criticidade | Autor responsável |
| :--- | :--- | :--- | :--- | :--- |
| **T01** | Comparar métricas de desempenho entre linguagens para escolha técnica | P01 (Rafael) / C01 | Alta frequência / Alta criticidade | João Pedro Bazoli Palma |
| **T02** | Buscar e comparar métricas de desempenho para artigo acadêmico | P02 (Mariana) / C02 | Alta frequência / Alta criticidade | Augusto Pereira Teixeira |

> Priorize tarefas necessárias para que o usuário alcance objetivos centrais. Não desperdice a modelagem em ações triviais isoladas, como “clicar em login”, se o objetivo relevante é maior. Da mesma forma, não modele o funcionamento interno do algoritmo como se fosse uma tarefa humana.

---

## HTA — T01 Comparar métricas de desempenho entre linguagens para escolha técnica

**Autor(a):** João Pedro Bazoli Palma — 24.123.041-6

##### **Descrição da tarefa**

- **Objetivo:** Escolher a linguagem ideal para um novo projeto com base em velocidade e uso de memória.
- **Ponto de início:** Acesso à ferramenta de consulta de benchmarks.
- **Conclusão esperada:** Comparativo claro entre linguagens para fundamentar a decisão técnica.
- **Contexto:** Rafael Mendes (P01) precisa definir a linguagem em 2 dias e justificar para a equipe.

### Diagrama

![HTA T01](../assets/05_tarefas/hta_t01.svg)

#### **Decomposição e planos**

| **ID** | **Objetivo/operação** | **Plano/ordem** | **Problema ou decisão de design observada** |
| --- | --- | --- | --- |
| **0** | Comparar desempenho entre linguagens para escolha técnica | `1 > 2 > 3`. Se houver dúvida nos dados, faça `4`. | Evitar muitas etapas antes de exibir os resultados. |
| **1** | Selecionar o problema/algoritmo | `1.1 OU 1.2` | Incluir resumos simples dos problemas. |
| **1.1** | Buscar algoritmo por palavra-chave | Operação | Aceitar termos genéricos e sinônimos na busca. |
| **1.2** | Selecionar algoritmo por categoria | Operação | Agrupar por tipo de processamento (ex: memória, CPU). |
| **2** | Selecionar linguagens e métricas | `2.1 + 2.2` | Permitir comparar 2 ou mais linguagens lado a lado. |
| **2.1** | Escolher as linguagens para comparação | Operação | Facilitar a seleção direta na interface. |
| **2.2** | Definir métricas (tempo e memória) | Operação | Exibir ambas as métricas na mesma visualização. |
| **3** | Analisar os resultados | `3.1` | Mostrar a diferença em termos relativos (ex: "2x mais rápida"). |
| **3.1** | Avaliar o ganho relativo de desempenho | Operação | Facilitar a interpretação sem exigir cálculos manuais. |
| **4** | Checar credibilidade do teste | `4.1` (Opcional) | Exibir o computador e o compilador em um clique para dar credibilidade. |
| **4.1** | Conferir especificações do hardware e versões | Operação | Garantir transparência sobre as condições do teste. |

**Verificação do HTA:**

- O objetivo 0 representa uma meta do usuário?
- As subtarefas são necessárias e suficientes?
- Os **planos** indicam ordem, alternativa, repetição ou condição?
- A decomposição parou em nível útil para projeto de interação?

- 
## **GOMS — T01 Comparar métricas de desempenho entre linguagens para escolha técnica**

**Autor(a):** João Pedro Bazoli Palma — 24.123.041-6

### **Goal**

#### **G0:** Comparar métricas de desempenho entre duas ou mais linguagens de programação para fundamentar uma escolha técnica.

- **Métodos, operadores e regras de seleção**

#### **G1: Selecionar o algoritmo/problema de interesse**

- **Method M1.A (Busca direta por palavra-chave):**
  - Identificar algoritmo → Mover cursor até a busca → Clicar no campo → Digitar nome → Clicar na opção desejada.
- **Method M1.B (Navegação por categoria de processamento):**
  - Identificar tipo de processamento → Clicar no menu suspenso de categorias → Clicar na categoria desejada.
- **Selection Rule SR1:** Usar M1.A quando souber o nome exato do algoritmo; usar M1.B quando quiser explorar por categoria.

#### **G2: Selecionar linguagens e gerar confronto direto**

- **Method M2 (Confronto de linguagens e métricas):**
  - Mover cursor até o seletor de linguagens → Marcar as linguagens a comparar → Marcar as métricas (tempo e memória) → Clicar em "Gerar Comparativo".

#### **G3: Analisar os resultados e tomar decisão**

- **Method M3 (Interpretação visual e validação):**
  - Observar gráfico de velocidade relativa → Observar gráfico de uso de memória → Identificar a linguagem mais eficiente para o projeto.
 
## **CTT — T01 Comparar métricas de desempenho entre linguagens para escolha técnica**

**Autor(a):** João Pedro Bazoli Palma — 24.123.041-6

### **Descrição da tarefa**

O gestor Rafael Mendes (P01) acessa a plataforma para escolher e fundamentar a linguagem de programação de um novo projeto. Ele define o algoritmo de interesse, escolhe as linguagens e métricas desejadas, aguarda o processamento do sistema e analisa os gráficos gerados para tomar sua decisão técnica.

### Diagrama

![CTT T03](../assets/05_tarefas/ctt_t03.svg)

---

### **Legenda dos tipos de tarefas**

- **[A]** **Tarefa Abstrata (Abstract):** Meta principal que precisa ser decomposta em sub-tarefas.
- **[U]** **Tarefa de Usuário (User):** Ação puramente mental/cognitiva do usuário (análise ou decisão).
- **[I]** **Tarefa de Interação (Interaction):** Ação direta do usuário na interface do sistema.
- **[S]** **Tarefa de Sistema (System):** Processamento automático realizado pelo sistema.

### **Legenda dos operadores temporais utilizados**

| **Operador** | **Nome da relação** | **Significado na Tarefa T01** |
| --- | --- | --- |
| **&gt;>** | Habilitação (Sequencial) | A conclusão de uma tarefa habilita o início da próxima. |
| **[]>>** | Habilitação com Troca de Informação | A tarefa é concluída e envia parâmetros/dados para a próxima. |
| **[]** | Escolha (Alternativa) | Escolha entre duas ações mutuamente exclusivas. |
| \*\*\` | | |

---

### **Estrutura textual da árvore (Decomposição CTT)**

- **T01: Comparar métricas de desempenho entre linguagens** **[A]**
  - *Plano temporal principal:* `1. Definir Problema &gt;&gt; 2. Configurar Comparativo []&gt;&gt; 3. Processar Resultados &gt;&gt; 4. Analisar e Decidir`
  - **1. Definir Problema/Algoritmo** **[A]**
    - *Relação:* `1.1 Buscar por Nome [] 1.2 Selecionar por Categoria`
    - **1.1 Buscar por nome** **[I]:** Digitar o termo no campo de busca rápida.
    - **1.2 Selecionar por categoria** **[I]:** Escolher o tipo de processamento no menu suspenso.
  - **2. Configurar Comparativo** **[A]**
    - *Relação:* `2.1 Selecionar Linguagens ||| 2.2 Selecionar Métricas`
    - **2.1 Selecionar linguagens** **[I]:** Escolher as linguagens a serem comparadas.
    - **2.2 Selecionar métricas** **[I]:** Marcar as métricas desejadas (tempo e memória).
  - **3. Processar e Exibir Resultados** **[A]**
    - *Relação:* `3.1 Consultar Banco []&gt;&gt; 3.2 Renderizar Gráfico`
    - **3.1 Consultar banco** **[S]:** O sistema busca os dados de benchmark filtrados.
    - **3.2 Renderizar gráfico** **[S]:** O sistema gera os gráficos comparativos na tela.
  - **4. Analisar e Decidir** **[A]**
    - *Relação:* `4.1 Avaliar Gráficos &gt;&gt; 4.2 Tomar Decisão Técnica`
    - **4.1 Avaliar gráficos** **[U]:** O gestor interpreta a diferença de velocidade e uso de memória.
    - **4.2 Tomar decisão técnica** **[U]:** O gestor define a linguagem escolhida e registra os dados.

Identifique, quando aplicável, tarefas de usuário, sistema, interação e tarefas abstratas. Verifique se concorrência, escolha, habilitação, desabilitação e repetição estão representadas corretamente segundo a notação adotada em aula.

---

## Síntese da equipe

Quais problemas de interação, oportunidades e requisitos apareceram a partir das modelagens? Quais tarefas irão para o protótipo e para o teste de usabilidade?

## Checklist

- [ ] Cada integrante produziu ao menos 1 HTA, 1 GOMS e 1 CTT.
- [ ] Cada artefato identifica autor e tarefa.
- [ ] Diagramas são legíveis e possuem fonte editável quando possível.
- [ ] HTA contém planos, não apenas árvore de tópicos.
- [ ] GOMS distingue Goals, Operators, Methods e Selection Rules.
- [ ] CTT usa operadores temporais e tipos de tarefa coerentes.
- [ ] Há texto explicando cada diagrama.
- [ ] Tarefas estão ligadas a cenários/personas na rastreabilidade.
- [ ] Em TCC técnico, as tarefas descrevem o que a pessoa faz com a contribuição/resultados, não passos internos do código.
- [ ] CRUDs, relatórios, filtros e atividades administrativas foram escolhidos por relevância ao objetivo do usuário.
