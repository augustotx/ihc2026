# Entrega 6 — Prototipação em papel

**Data:** 06/11/2026

**Status:** 🟨 em andamento

**Responsabilidade:** João Pedro Bazoli Palma e Augusto Pereira Teixeira

## Objetivo da atividade

Externalizar rapidamente ideias de interação em baixa fidelidade para explorar alternativas antes de investir em detalhes visuais. O valor está no ciclo **construir → simular → observar → revisar**, não na beleza do desenho.

## 1. Escopo do protótipo

* **Personas:**
  * **P01 (Rafael Mendes):** Gestor Técnico (decisões céleres de arquitetura/linguagem com base em comparação de velocidade e memória).
  * **P02 (Mariana Costa):** Pesquisadora Acadêmica (auditar reprodutibilidade, conferir códigos/parâmetros e exportar dados brutos/citações para artigos).
* **Cenários/tarefas cobertos:**
  * **C01 / T01:** Comparar métricas de desempenho entre linguagens para escolha técnica.
  * **C02 / T02:** Inspecionar reprodutibilidade do benchmark e exportar dataset para pesquisa.
* **Objetivos principais:**
  * Localização rápida de benchmarks via catálogo filtrável na página inicial.
  * Comparação visual e parametrizada de desempenho entre linguagens na tela do algoritmo.
  * Transparência técnica total: inspeção do código-fonte, comandos de build/run, especificações do ambiente e exportação de datasets/citações.

### 1.1 Famílias de interface escolhidas

Com base nas tarefas priorizadas para P01 e P02, o protótipo explora três famílias:

1. **Catálogo & Dashboard de Entrada:** introdução à plataforma, busca e filtragem (nome, categoria, linguagens) e lista de benchmarks com resumos visuais de métricas.
2. **Painel de Comparação & Parametrização:** descrição do algoritmo e configuração da comparação entre linguagens, alternando parâmetros e métricas (tempo vs. memória).
3. **Inspeção, Auditoria & Exportação:** código-fonte, comandos de compilação/execução, detalhes de hardware/compilador, download do dataset (CSV/JSON) e cópia de citação (BibTeX/ABNT).

## 2. Fluxos escolhidos

| Fluxo | Tarefa/objetivo | Por que foi priorizado |
|---|---|---|
| **PF01** | **Comparar métricas de desempenho entre linguagens para escolha técnica (T01)** | Priorizado por representar o objetivo primário do Gestor Técnico (P01). O fluxo permite navegar da Página Inicial (filtrando o catálogo) até a Tela do Algoritmo para ajustar e visualizar o gráfico comparativo de tempo e memória, fundamentando decisões rápidas de arquitetura. |
| **PF02** | **Inspecionar reprodutibilidade do benchmark e exportar dataset para pesquisa (T02)** | Priorizado por atender aos requisitos de rigor acadêmico da Pesquisadora (P02). O fluxo estende a navegação até a Tela de Código/Guix e a Tela de Infraestrutura (About), permitindo auditar o manifesto de reprodutibilidade via Guix, conferir o hardware e exportar o dataset bruto (CSV) e a citação (BibTeX). |

### Detalhamento dos caminhos de tela por fluxo

* **Caminho do Fluxo PF01 (Rafael - Gestor):**
  * `P01 (Página Inicial / Catálogo)` → Usa a busca/filtros para encontrar o algoritmo → Clica no card do algoritmo.
  * `P02 (Página do Algoritmo / Comparativo)` → Ajusta os seletores de linguagens e métricas → Analisa visualmente o gráfico de barras comparativo de desempenho.
* **Caminho do Fluxo PF02 (Mariana - Pesquisadora):**
  * `P01 (Página Inicial / Catálogo)` → Clica no link "Sobre o Projeto & Hardware" no cabeçalho → `P04 (Sobre & Infraestrutura)` para conferir a máquina de testes.
  * `P01` ou `P02` → Clica na aba "Código e Reprodutibilidade Guix".
  * `P03 (Página de Código & Manifesto Guix)` → Inspeciona o código-fonte e a receita de reprodutibilidade via Guix → Clica em "Exportar Dataset (CSV)" e "Copiar BibTeX".

## 3. Telas e estados

### Relação de Telas e Transições

* **`P01` — Página Inicial (Catálogo de Benchmarks):**
  * **Descrição:** Apresenta a visão geral do projeto, campo de busca, filtros por categoria/linguagem, cards dos algoritmos e link no cabeçalho para a página "Sobre & Hardware".
  * **Controles & Ações:**
    * Clicar no card de um algoritmo → Navega para **`P02`**.
    * Clicar em "Sobre & Hardware" no menu → Navega para **`P04`**.

* **`P02` — Página do Algoritmo (Dashboard Comparativo):**
  * **Descrição:** Exibe o título e descrição do algoritmo, seletores de linguagens/métricas, gráfico comparativo em barras e atalho para o código e reprodutibilidade.
  * **Controles & Ações:**
    * Clicar em *"Ver Código e Reprodutibilidade Guix"* → Navega para **`P03`**.
    * Clicar em *"Voltar ao Catálogo"* → Retorna para **`P01`**.

* **`P03` — Página de Código & Reprodutibilidade via Guix:**
  * **Descrição:** Apresenta o código-fonte original do benchmark, o manifesto/receita de compilação reprodutível via **GNU Guix**, além dos botões de exportação de dados (CSV/JSON) e citação (BibTeX/ABNT).
  * **Controles & Ações:**
    * Clicar em *"Exportar Dataset (CSV)"* → Dispara o download dos dados brutos.
    * Clicar em *"Copiar BibTeX"* → Copia a citação formatada.
    * Clicar em *"Ver Especificações de Hardware"* → Navega para **`P04`**.

* **`P04` — Página Sobre o Projeto & Infraestrutura de Hardware:**
  * **Descrição:** Explica a metodologia da plataforma de benchmarking e lista o ambiente físico de testes (modelo da CPU, memória RAM, kernel Linux e versão do Guix).
  * **Controles & Ações:**
    * Clicar em *"Voltar"* → Retorna para a tela anterior (`P01` ou `P03`).

---

### Protótipos em Papel

## 4. Simulação / walkthrough

A simulação de uso (*walkthrough* formativo) foi realizada apresentando os protótipos em papel para dois colegas do curso de Ciência da Computação. Os participantes executaram os dois fluxos priorizados (PF01 e PF02) interpretando os papéis das personas Rafael (Gestor Técnico) e Mariana (Pesquisadora Acadêmica). Ambos os avaliadores conseguiram concluir as tarefas propostas de forma fluida, sem hesitações na navegação ou bloqueios cognitivos. Elogiaram a clareza da organização visual das telas, a facilidade de localização das opções de filtragem e a separação lógica entre o painel de comparação e a área de código/especificações de *build/run*.

| Observação | Tela/ação | Evidência | Consequência para o design |
|---|---|---|---|
| **Localização rápida de algoritmos** | `P01 (Catálogo)` → Busca e filtros | Os participantes utilizaram os filtros por categoria e busca por nome sem nenhuma dúvida sobre onde clicar. | Mantida a estrutura de catálogo com barra de busca no topo e filtros laterais/superiores. |
| **Compreensão intuitiva dos gráficos** | `P02 (Comparativo)` → Seleção de métricas | Os avaliadores identificaram imediatamente os eixos de velocidade e memória e ajustaram os seletores de linguagens rapidamente. | Mantido o layout do Dashboard Comparativo com barras lado a lado e seletores diretos. |
| **Acesso claro ao código e instruções** | `P02` → `P03 (Código e Build/Run)` | A transição para a tela de código e comandos de compilação/execução foi feita de forma natural através da aba/botão dedicado. | Mantida a navegação por abas/links de detalhamento para inspeção de reprodutibilidade. |
| **Exportação e citação direta** | `P03` → Botões de download e citação | Os botões de exportação (CSV) e cópia de citação (BibTeX) foram reconhecidos de primeira como utilitários de alta conveniência. | Mantido o posicionamento fixo dos utilitários de exportação na tela de detalhes do benchmark. |

---

## 5. Alterações após a simulação

Com base nos resultados do *walkthrough* realizado com os dois colegas de Ciência da Computação, **nenhuma falha de usabilidade, ambiguidade de fluxo ou necessidade de reestruturação de layout foi identificada**. Os avaliadores destacaram que a distribuição dos elementos na página inicial, o fluxo de parametrização dos gráficos e a área de inspeção técnica (código, instruções de *build/run* e exportação) atendem com precisão às necessidades das personas (P01 e P02) e seguem as convenções estabelecidas para ferramentas de desenvolvimento analisadas nas entregas anteriores.

| Antes | Problema | Depois | Justificativa |
|---|---|---|---|
| **Estrutura das telas `P01`, `P02` e `P03`** | Nenhum problema ou fricção de interação identificado durante a simulação. | Mantida a estrutura original do protótipo em papel. | Os fluxos PF01 e PF02 foram concluídos com sucesso e sem erros pelos participantes, confirmando a adequação da arquitetura de informação e da hierarquia visual propostas. |

## Checklist

- [ ] O protótipo cobre tarefas relevantes da Entrega 5.
- [ ] Cada tela/estado pode ser justificado por uma tarefa, decisão ou informação necessária.
- [ ] O projeto não criou dashboard/CRUD/login apenas para parecer “completo”.
- [ ] Telas/estados estão numerados e navegáveis na documentação.
- [ ] Há pelo menos uma simulação/walkthrough documentado.
- [ ] Críticas não foram apenas listadas: geraram decisão de revisão.
- [ ] O protótipo continua em baixa fidelidade; detalhes visuais não mascaram problemas de fluxo.
