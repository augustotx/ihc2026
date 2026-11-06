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
| **PF02** | **Inspecionar reprodutibilidade do benchmark e exportar dataset para pesquisa (T02)** | Priorizado por atender aos requisitos de rigor acadêmico da Pesquisadora (P02). O fluxo estende a navegação até a Tela de Código e Execução, permitindo auditar os comandos de *build/run*, conferir o ambiente técnico e exportar o dataset bruto (CSV) e a citação (BibTeX). |

### Detalhamento dos caminhos de tela por fluxo

* **Caminho do Fluxo PF01 (Rafael - Gestor):**
  * `P01 (Página Inicial / Catálogo)` → Usa o campo de busca/filtros para encontrar o algoritmo → Clica no card do algoritmo.
  * `P02 (Página do Algoritmo / Comparativo)` → Ajusta os seletores de linguagens e métricas → Analisa visualmente o gráfico de barras comparativo de desempenho.
* **Caminho do Fluxo PF02 (Mariana - Pesquisadora):**
  * `P01 (Página Inicial / Catálogo)` → Filtra por categoria de processamento → Clica no experimento desejado.
  * `P02 (Página do Algoritmo / Comparativo)` → Avalia o resumo do algoritmo → Clica na aba/botão "Ver Código e Instruções de Execução".
  * `P03 (Página de Código, Build/Run & Reprodutibilidade)` → Inspeciona o código-fonte e os comandos de *build/run* → Confere metadados de hardware e compilador → Clica em "Exportar Dataset (CSV)" e "Copiar BibTeX".

## 3. Telas e estados

### Relação de Telas e Transições

* **`P01` — Página Inicial (Catálogo de Benchmarks):**
  * **Descrição:** Apresenta a visão geral do projeto, campo de busca e filtros laterais/superiores por categoria e linguagem, além dos cards dos algoritmos disponíveis.
  * **Controles & Ações:**
    * Clicar no campo de busca/filtro → Atualiza os cards exibidos.
    * Clicar no card de um algoritmo → Navega para a tela **`P02`**.

* **`P02` — Página do Algoritmo (Dashboard Comparativo):**
  * **Descrição:** Exibe o título e descrição do algoritmo, seletores de linguagens e métricas (tempo vs. memória), o gráfico comparativo em barras e atalho para o código.
  * **Controles & Ações:**
    * Alterar seletores de linguagens/métricas → Atualiza o gráfico comparativo na própria tela.
    * Clicar no botão/aba *"Ver Código e Instruções de Execução"* → Navega para a tela **`P03`**.
    * Clicar em *"Voltar ao Catálogo"* → Retorna para a tela **`P01`**.

* **`P03` — Página de Código, Build/Run & Reprodutibilidade:**
  * **Descrição:** Apresenta o código-fonte original, comandos de compilação/execução (*build/run*), especificações de hardware/compilador e utilitários de exportação.
  * **Controles & Ações:**
    * Clicar em *"Exportar Dataset (CSV)"* → Dispara o download do arquivo de dados brutos.
    * Clicar em *"Copiar BibTeX"* → Copia a citação formatada para a área de transferência.
    * Clicar no botão *"Voltar ao Comparativo"* → Retorna para a tela **`P02`**.

---

### Protótipos em Papel

## 4. Simulação / walkthrough

Realize uma simulação com uma pessoa que não participou da elaboração dessas telas. Um colega pode ser usado **para essa iteração formativa**, mas isso não substitui os participantes finais da Entrega 14.

| Observação | Tela/ação | Evidência | Consequência para o design |
|---|---|---|---|
| {{...}} | {{...}} | {{...}} | {{...}} |

## 5. Alterações após a simulação

| Antes | Problema | Depois | Justificativa |
|---|---|---|---|
| {{...}} | {{...}} | {{...}} | {{...}} |

## Checklist

- [ ] O protótipo cobre tarefas relevantes da Entrega 5.
- [ ] Cada tela/estado pode ser justificado por uma tarefa, decisão ou informação necessária.
- [ ] O projeto não criou dashboard/CRUD/login apenas para parecer “completo”.
- [ ] Telas/estados estão numerados e navegáveis na documentação.
- [ ] Há pelo menos uma simulação/walkthrough documentado.
- [ ] Críticas não foram apenas listadas: geraram decisão de revisão.
- [ ] O protótipo continua em baixa fidelidade; detalhes visuais não mascaram problemas de fluxo.
