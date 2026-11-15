# Entrega 10 — Modelagem da interação com MoLIC

**Data:** 15/11/2026

**Status:** 🟨 em andamento

**Responsabilidade:** João Pedro Bazoli Palma e Augusto Pereira Teixeira

## Objetivo da atividade

Representar a interação em nível conceitual e comunicativo por meio de diagramas MoLIC (*Modelling Language for Interaction as Conversation*), explicitando a conversa entre o usuário e o preposto do sistema (designer) para as tarefas prioritárias de cada integrante.

---

## 1. Soluções individuais

### M01 — Comparação de Desempenho no Dashboard

**Autor(a):** João Pedro Bazoli Palma — 24.123.041-6

**Cenário de origem:** CI01 (Rafael Mendes — Gestor Técnico)

**Objetivos vinculados:** `O01` (Escolher linguagem), `O03` (Localizar benchmark), `O04` (Parametrizar linguagens/métricas), `O05` (Analisar trade-off nos gráficos).

**Tarefas relacionadas (Entrega 5):** T01 (Comparar desempenho de linguagens no catálogo de benchmarks).

**Signos relevantes manipulados:** `filtro_categoria`, `seletor_linguagens`, `seletor_metrica`, `grafico_barras`.

**Link da fonte editável:** *(Inserir link do Draw.io / SVG)*

![Diagrama MoLIC - M01](../assets/10_molic/molic_01_joao_pedro.png)

#### Leitura textual do diagrama (Caminho Principal)

1. **Abertura:** Parte do ponto de abertura com a meta `gco: Comparar desempenho de linguagens`.
2. **Cena Principal (Configurar comparação no Dashboard):** O sistema exibe os seletores (`d+u: parâmetros do teste`). Rafael seleciona as linguagens candidatas (Go, Rust, Java), define a métrica ativa (tempo vs. memória) e aciona `u: Atualizar gráfico`.
3. **Processamento do Sistema (Caixa Preta):** O sistema valida o número de seleções (mínimo 2, máximo 5) e consolida os dados de medição.
4. **Fechamento da Meta:** O sistema retorna com sucesso (`d: Gráfico comparativo gerado`), transitando com `gcc: Comparar desempenho de linguagens`.
5. **Cena Final (Analisar trade-off de desempenho):** O preposto plota o gráfico de barras comparativo (`d: grafico_barras`), permitindo a Rafael avaliar visualmente o trade-off e encerrar a consulta no ponto de término.

#### Alternativas e Rupturas (Breakdowns)

| Identificador | Ponto de partida | Condição / Ruptura | Comportamento do sistema | Recuperação / Desfecho |
|---|---|---|---|---|
| **ALERTA-01** | Cena Principal (Seleção) | Rafael tenta marcar mais de 5 linguagens simultâneas no gráfico. | O sistema emite aviso de limite (`d: "Limite máximo de 5 linguagens atingido"`). | Transita para cena tracejada de aviso; Rafael aciona `u: Desmarcar linguagem excedente` e retorna à configuração. |
| **ALT-01** | Cena Principal (Filtro) | Rafael deseja isolar apenas algoritmos intensivos em CPU antes de gerar o gráfico. | O preposto aplica a restrição via `u: Filtrar CPU-bound`. | A lista de testes do dashboard é filtrada diretamente sem sair da cena. |

---

### M02 — Auditoria Metodológica e Exportação de Dados

**Autor(a):** Augusto Pereira Teixeira — 24.123.008-5

**Cenário de origem:** CI02 (Mariana Costa — Pesquisadora Acadêmica)

**Objetivos vinculados:** `O02` (Auditar rigor e embasar artigo), `O03` (Localizar benchmark), `O06` (Inspecionar código e Guix), `O07` (Baixar CSV), `O08` (Copiar BibTeX).

**Tarefas relacionadas (Entrega 5):** T02 (Auditar reprodutibilidade metodológica e exportar dados/citação).

**Signos relevantes manipulados:** `campo_busca`, `bloco_guix`, `botao_csv`, `botao_bibtex`, `toast_feedback`.

**Link da fonte editável:** *(Inserir link do Draw.io / SVG)*

![Diagrama MoLIC - M02](../assets/10_molic/molic_02_augusto.png)

#### Leitura textual do diagrama (Caminho Principal)

1. **Abertura:** Parte do ponto de abertura com a meta `gco: Auditar rigor e exportar dados`.
2. **Cena Principal (Detalhes do Experimento e Reprodutibilidade):** O preposto exibe o código-fonte, flags de compilação (`-O3`) e a receita declarativa do GNU Guix (`d+u: bloco_guix, opções de exportação`). Mariana confere a metodologia e aciona a exportação (`u: Baixar CSV e copiar citação`).
3. **Processamento do Sistema (Caixa Preta):** O sistema prepara o arquivo tabular para download e copia a referência formatada para a área de transferência.
4. **Fechamento da Meta:** O sistema conclui o processamento com sucesso (`d: Arquivo CSV enviado e BibTeX copiado`), transitando com `gcc: Auditar rigor e exportar dados`.
5. **Cena Final (Dados coletados para pesquisa):** O preposto exibe o toast de confirmação (`d: toast_feedback`), e Mariana conclui a tarefa no ponto de encerramento.

#### Alternativas e Rupturas (Breakdowns)

| Identificador | Ponto de partida | Condição / Ruptura | Comportamento do sistema | Recuperação / Desfecho |
|---|---|---|---|---|
| **AJUDA-01** | Cena Principal (Detalhes) | Mariana tem dúvidas sobre a máquina física onde os testes foram executados. | Mariana aciona `u: Consultar hardware de teste`. | Desvia para cena tracejada de ajuda com especificações da CPU/RAM; Mariana clica em `u: Voltar aos detalhes`. |
| **ALT-01** | Cena Principal (Ações) | Mariana deseja apenas a citação bibliográfica, sem fazer o download do CSV. | Mariana aciona apenas `u: Copiar BibTeX`. | O sistema copia o texto para o clipboard, emite o toast de confirmação e finaliza o fluxo. |

---

## 2. Síntese e decisões de design

1. **Estrutura Focal em uma Cena Central:** Seguindo a boa prática do MoLIC, cada diagrama foca na cena interativa central da sua respectiva persona (o Dashboard de Comparação para o Rafael e a Tela de Auditoria/Exportação para a Mariana), evitando diagramas sobrecarregados.
2. **Uso de Cenas Satélites Tracejadas:** Situações de contorno (como o alerta de excesso de linguagens no M01 e a consulta de hardware no M02) foram modeladas como cenas tracejadas auxiliares que retornam à cena principal após a resolução.
3. **Consolidação dos Processamentos do Sistema:** Cada fluxo contém um ponto central de processamento (caixa preta) que valida os inputs antes de emitir a fala de encerramento da meta (`gcc:`).

---

## Checklist

- [x] O documento possui 1 solução completa por integrante (M01 - João Pedro e M02 - Augusto).
- [x] Cada solução identifica autor, cenário de origem, objetivos, tarefas e signos manipulados.
- [x] Os diagramas possuem pontos de abertura (círculo preto), cenas de conversa, caixas pretas de processamento e pontos de encerramento (alvo).
- [x] Transições contêm a identificação explícita de falas do usuário (`u:`) e do sistema (`d:`), além das tags `gco:` e `gcc:`.
- [x] Há representação de caminhos alternativos e recuperação de rupturas (*breakdowns*) com tabelas explicativas enxutas.
- [x] Os nomes dos objetivos e signos são rigorosamente idênticos aos definidos nas Entregas 8 e 9.
