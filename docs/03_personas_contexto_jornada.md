# Entrega 3 — Personas, mapa de empatia, contexto de uso e jornada

**Data:** 14/10/2005  
**Status:** 🟨 em andamento`  
**Responsabilidade:** 1 persona por integrante; 1 mapa de empatia, 1 contexto de uso consolidado e 1 jornada por equipe (salvo orientação diferente do docente).

## Objetivo da atividade

Representar grupos de usuários de forma útil para decisões de design. Persona não é personagem decorativo: suas características devem alterar requisitos, prioridades, linguagem, fluxos ou critérios de avaliação.

## Atenção a projetos técnicos

Em TCCs sem interface original, a persona pode representar um **profissional que se apropria da contribuição técnica**: DBA, analista, cientista de dados, administrador, pesquisador, técnico, operador, gestor ou especialista de domínio.

Não escolha um perfil apenas porque “parece combinar” com a tecnologia. Explique **qual objetivo esse perfil teria e qual parte da contribuição do TCC produziria valor para ele**. Se ainda for hipótese, mantenha como hipótese/proto-persona a validar.

Também considere papéis diferentes quando houver tarefas distintas, por exemplo:

- operador que executa análises;
- administrador que configura e gerencia permissões;
- especialista que interpreta resultados;
- gestor que consulta relatórios e decide;
- auditor que revisa histórico.

## Entradas da Entrega 1

Antes de criar personas, retome os tipos de usuários, características relevantes, objetivos e hipóteses registradas na Entrega 1. A persona **não deve transformar uma hipótese inicial em fato por meio de uma história fictícia**.

| Item da Entrega 1 | Status inicial | Evidência disponível agora | Como será tratado nesta entrega |
| --- | --- | --- | --- |
| Desenvolvedores como público prioritário | F | Definição registrada na Entrega 1 e retomada na Entrega 2 | Incorporar como público principal e base da persona P01 |
| Escolha de linguagens com base em métricas de desempenho | F | Objetivo de uso definido na Entrega 1 | Incorporar como objetivo principal da persona P01 |
| Comparação manual ou enviesada entre linguagens | H | Levantamento inicial da Entrega 1 sobre como o problema pode ser resolvido atualmente | Manter como hipótese e usar como base para  as personas P01 e P02 |
| Interesse em consultar resultados de diferentes problemas e linguagens | H | Escopo proposto para a ferramenta e análise do Debian Benchmark Game na Entrega 2 | usar como necessidade provável e como base para P02 |
| Necessidade de visualizar e filtrar resultados | H | Funcionalidades F01 e F02 da Entrega 1 e análise de ferramentas semelhantes na Entrega 2 | Incorporar como necessidade de interação, ainda sujeita a validação |
| Interesse acadêmico na análise de benchmarks | H | Contexto acadêmico considerado na Entrega 1 | Usar como base para a persona P02, mantendo como hipótese |

## 1. Personas

### Persona P01 — Rafael Mendes, gestor de projetos de software

**Autor:** João Pedro Bazoli Palma — 24.123.041-6

**Tipo:** primária

**Base de evidências:** proto-persona a validar, baseada nas Entregas 1 e 2

**Hipóteses da Entrega 1 relacionadas:** H01, H03

| Campo | Descrição |
| --- | --- |
| Faixa etária / contexto relevante | Não definida. A idade não é considerada relevante para as tarefas previstas nesta etapa. |
| Ocupação/papel | Gestor de projetos de software que precisa avaliar alternativas técnicas para implementar um projeto. |
| Conhecimento do domínio | Conhece linguagens de programação,entende que o desempenho pode variar conforme a linguagem, o algoritmo e o problema executado e possui conhecimento das necessidades e limitações técnicas do projeto que supervisiona.|
| Experiência tecnológica | Utiliza computador e ferramentas de desenvolvimento de software e possui acesso à internet. |
| Objetivos | escolher a linguagem de programação idea para o projeto que está supervisionando |
| Necessidades | Precisa tomar a decisão de qual linguagem de programação utilizar no projeto de software que supervisiona |
| Dores/frustrações | Escolha de linguagem de programação enviesada pelo mercado e experiência pessoal; Objetivo do projeto supervisionado abrangente quanto a linguagem de programação|
| Motivadores | Escolher a melhor linguagem possível para o projeto supervisionado |
| Restrições/acessibilidade | A proposta considera acesso a um computador, navegador e internet. Outras restrições de acessibilidade ainda não foram investigadas. |
| Ambiente típico de uso | Possivelmente em um ambiente de trabalho, utilizando um computador para consultar e comparar resultados.  |
| Comportamentos relevantes | Pode pesquisar benchmarks, selecionar um problema, comparar linguagens e analisar métricas antes de tomar uma decisão. A sequência exata de comportamento ainda precisa ser investigada. |

![Persona P01](../assets/03_personas/persona_p01.svg)

| Campo | Descrição |
|---|---|
| Faixa etária / contexto relevante | {{somente o que impacta o uso}} |
| Ocupação/papel | {{...}} |
| Conhecimento do domínio | {{...}} |
| Experiência tecnológica | {{...}} |
| Objetivos | {{...}} |
| Necessidades | {{...}} |
| Dores/frustrações | {{...}} |
| Motivadores | {{...}} |
| Restrições/acessibilidade | {{...}} |
| Ambiente típico de uso | {{...}} |
| Comportamentos relevantes | {{...}} |

**Decisões de design influenciadas por P01:**

- {{...}}

> Repita para P02, P03... Cada integrante deve produzir ao menos uma persona.

### Síntese das personas

Explique diferenças entre os perfis e qual persona é prioritária. Evite personas duplicadas que só mudam nome/foto.

## 2. Mapa de empatia — equipe

**Persona escolhida:** {{P01}}  
**Justificativa:** {{por que esse perfil é relevante}}

![Mapa de empatia](../assets/03_personas/mapa_empatia.svg)

Documente também em texto: o que vê; ouve; diz/faz; pensa/sente; dores; ganhos. Diferencie **evidência** de **hipótese**.

## 3. Contexto de uso — consolidação

| Dimensão | Descrição | Implicação de design |
|---|---|---|
| Usuários | {{...}} | {{...}} |
| Tarefas | {{...}} | {{...}} |
| Equipamentos | {{...}} | {{...}} |
| Ambiente físico | {{...}} | {{...}} |
| Ambiente social/organizacional | {{...}} | {{...}} |
| Papéis/permissões/governança | {{...}} | {{...}} |
| Volume de dados/histórico | {{...}} | {{...}} |

## 4. Jornada do usuário — equipe

**Persona:** {{P01}}  
**Objetivo da jornada:** {{...}}  
**Início e fim da jornada:** {{...}}

| Etapa | Situação/ação | Objetivo | Pensamento/emoção | Dor | Oportunidade de design | Evidência |
|---|---|---|---|---|---|---|
| 1 | {{...}} | {{...}} | {{...}} | {{...}} | {{...}} | {{...}} |

> A jornada pode incluir etapas **antes, durante e depois** do uso do produto. Não transforme a jornada em lista de telas.

## Síntese

Quais necessidades e objetivos devem obrigatoriamente aparecer nos cenários e nas tarefas seguintes?

## Checklist

- [ ] Existe pelo menos uma persona por integrante.
- [ ] As personas não são apenas diferenças demográficas superficiais.
- [ ] Está claro o que é dado real e o que é hipótese/proto-persona.
- [ ] A persona não “validou por ficção” uma hipótese da Entrega 1; afirmações continuam marcadas como hipótese quando não há evidência.
- [ ] Objetivos e dores têm consequência para o design.
- [ ] Contexto de uso está coerente com a Entrega 1.
- [ ] Em TCC sem interface original, a persona possui relação explícita com a contribuição técnica.
- [ ] Papéis administrativos, técnicos e decisórios só foram criados quando possuem objetivos/tarefas diferentes.
- [ ] Jornada possui etapas, dores e oportunidades e não é apenas wireflow.
- [ ] IDs das personas foram adicionados à rastreabilidade.
