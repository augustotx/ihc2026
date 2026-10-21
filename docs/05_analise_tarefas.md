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
| **T02** | Filtrar resultados por algoritmo e consumo de memória | P01 (Rafael) / C01 | Média frequência / Alta criticidade | João Pedro Bazoli Palma |
| **T03** | Consolidar informações para justificativa técnica perante a equipe | P01 (Rafael) / C01 | Baixa frequência / Alta criticidade | João Pedro Bazoli Palma |
| **T04** | Validar as especificações do ambiente de teste e hardware | P02 (Mariana) / C02 | Média frequência / Alta criticidade | Augusto Pereira Teixeira |
| **T05** | Buscar e comparar métricas de desempenho para artigo acadêmico | P02 (Mariana) / C02 | Alta frequência / Alta criticidade | Augusto Pereira Teixeira |
| **T06** | Exportar dados e detalhes do benchmark para citação na pesquisa | P02 (Mariana) / C02 | Baixa frequência / Média criticidade | Augusto Pereira Teixeira |

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

---

## GOMS — T02 {{nome da tarefa}}

**Autor(a):** {{nome — matrícula}}

### Goal

`G0: {{meta do usuário}}`

### Métodos, operadores e regras de seleção

- **Method M1:** {{...}}
  - Operators: {{perceber, apontar, clicar, digitar, decidir... conforme o nível adotado}}
- **Method M2:** {{...}}
  - Operators: {{...}}
- **Selection Rule SR1:** usar M1 quando {{condição}}; usar M2 quando {{condição}}.

> Não chame qualquer passo de “método”. Em GOMS, métodos são sequências alternativas capazes de atingir uma meta; regras de seleção explicam quando escolher entre eles.

---

## CTT — T03 {{nome da tarefa}}

**Autor(a):** {{nome — matrícula}}

### Descrição

{{...}}

### Diagrama

![CTT T03](../assets/05_tarefas/ctt_t03.svg)

### Legenda e relações temporais usadas

| Operador/relação | Significado no diagrama | Exemplo no modelo |
|---|---|---|
| {{...}} | {{...}} | {{...}} |

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
