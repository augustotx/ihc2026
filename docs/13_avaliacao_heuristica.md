## Entrega 13 — Avaliação de IHC por inspeção heurística

**Data:** 16/11/2026

**Status:** 🟩 concluída

**Responsabilidade:** 1 avaliação completa por integrante, sobre todas as telas/estados relevantes do projeto.

#### Objetivo da atividade

Encontrar problemas de usabilidade por inspeção sistemática da interface com as **10 heurísticas de Nielsen**. Cada avaliador trabalhou individualmente primeiro; depois a equipe consolidou os problemas duplicados e definiu as prioridades de melhoria. A inspeção avalia estritamente a **qualidade da interface e da interação**, sem entrar no mérito técnico dos algoritmos ou compiladores do TCC.

#### 1. Heurísticas adotadas

1. Visibilidade do status do sistema
2. Compatibilidade entre o sistema e o mundo real
3. Controle e liberdade do usuário
4. Consistência e padrões
5. Prevenção de erros
6. Reconhecimento em vez de memorização
7. Flexibilidade e eficiência de uso
8. Estética e design minimalista
9. Ajudar usuários a reconhecer, diagnosticar e recuperar-se de erros
10. Ajuda e documentação

---

#### 2. Escopo da inspeção

| Item | Definição |
| :--- | :--- |
| **Versão avaliada** | Protótipo de Telas BMML (Telas F01 a F07 catalogadas na Entrega 11) |
| **Telas/estados** | F01 (Catálogo), F02 (Dispersão/Eixos), F03 (Tabela de Médias), F04 (Código), F05 (Flags), F06 (Modal About), F07 (Receita Guix) |
| **Fluxos** | M01 (Comparação de Desempenho) e M02 (Auditoria de Reprodutibilidade e Hardware) |
| **Dispositivo/viewport** | Desktop / Web 1920x1080 |
| **Avaliadores** | A01: João Pedro Bazoli Palma; A02: Augusto Pereira Teixeira |

---

#### 3. Procedimento individual

Cada avaliador percorreu as telas individualmente, inspecionando cada elemento interativo à luz das 10 heurísticas de Nielsen e classificando a severidade (0 a 4) com base na frequência, impacto e persistência.

##### Escala de severidade (0–4)

| Grau | Interpretação |
| :---: | :--- |
| **0** | Não é considerado problema de usabilidade. |
| **1** | Problema cosmético; corrigir apenas se houver tempo. |
| **2** | Problema menor; baixa prioridade. |
| **3** | Problema maior; alta prioridade de correção. |
| **4** | Catástrofe de usabilidade; correção obrigatória antes da liberação. |

---

### Avaliador A01 — João Pedro Bazoli Palma (Foco: M01 — Catálogo e Gráficos)

##### 4. Matriz de cobertura das 10 heurísticas

| Heurística | Telas/fluxos examinados | Houve violação? | IDs dos achados | Exemplo de boa prática se não violada |
| :---: | :--- | :---: | :---: | :--- |
| **H1** | F01, F02, F03 | Não | — | Atualização dinâmica imediata dos pontos no gráfico ao marcar ou desmarcar séries na tabela. |
| **H2** | F02 | Não | — | Uso de eixos cartesianos padrão (X = Tempo em segundos; Y = Memória em MB). |
| **H3** | F02, F03 | Não | — | Toggles diretos para alternar livremente entre escala Linear e Logarítmica nos eixos. |
| **H4** | F01, F02, F03 | Não | — | Cores idênticas para cada linguagem entre os pontos do gráfico, legendas e tabela. |
| **H5** | F03 | **Sim** | **V01** | — |
| **H6** | F02, F03 | Não | — | Tabela com métricas numéricas explícitas, sem exigir estimativa visual pelo gráfico. |
| **H7** | F03 | **Sim** | **V02** | — |
| **H8** | F01, F02 | Não | — | Design limpo em tema escuro, alto contraste e sem elementos decorativos desnecessários. |
| **H9** | F03 | Não | — | Instrução textual contextual informando como ordenar colunas e ocultar séries. |
| **H10** | F01, F02 | Não | — | Tags contextuais indicando o tipo de carga de cada teste (CPU-bound ou Memory-bound). |

##### 5. Declaração de violações

| ID | Heurística | Tela/estado | Problema observado | Evidência | Severidade | Justificativa da severidade | Recomendação |
| :-: | :-: | :--- | :--- | :--- | :-: | :--- | :--- |
| **V01** | **H5** | F03 (Tabela de Séries) | A interface permite desmarcar todas as séries da tabela, deixando o gráfico em branco sem aviso ou bloqueio prévio. | [Ver tela3.jpeg](../assets/11_figma/tela3.jpeg) | **2** | **Frequência média / impacto baixo:** O usuário recupera o estado facilmente ao remarcar uma caixa, mas pode estranhar a área vazia momentaneamente. | Impedir a desmarcação da última série ativa ou exibir alerta inline automático. |
| **V02** | **H7** | F03 (Tabela de Séries) | Inexistência de atalho para selecionar ou desmarcar todas as séries de uma só vez na tabela de médias. | [Ver tela3.jpeg](../assets/11_figma/tela3.jpeg) | **2** | **Frequência alta / persistência média:** Exige múltiplos cliques caso o usuário queira isolar apenas 1 ou 2 linguagens para comparação direta. | Adicionar botões de atalho "Select All / Deselect All" logo acima do cabeçalho da tabela. |

##### 6. Boas práticas — heurísticas não violadas

| Heurística sem violação | Exemplo no sistema | Evidência | Por que atende |
| :---: | :--- | :--- | :--- |
| **H4** | Consistência de cores entre gráfico e tabela | [Ver tela2.jpeg](../assets/11_figma/tela2.jpeg) | Cada linguagem preserva o mesmo código cromático tanto na dispersão gráfica quanto na tabela inferior. |
| **H8** | Estética e design minimalista no catálogo | [Ver tela1.jpeg](../assets/11_figma/tela1.jpeg) | Cards de benchmarks organizados em grade regular, destacando apenas o nome, tags de carga e métricas-chave. |

---

### Avaliador A02 — Augusto Pereira Teixeira (Foco: M02 — Código, Guix e About)

##### 4. Matriz de cobertura das 10 heurísticas

| Heurística | Telas/fluxos examinados | Houve violação? | IDs dos achados | Exemplo de boa prática se não violada |
| :---: | :--- | :---: | :---: | :--- |
| **H1** | F07 | Não | — | Notificação visual de feedback imediato ao clicar no botão `Copy` do script Guix. |
| **H2** | F04, F07 | Não | — | Uso de comandos e conceitos familiares ao público técnico (`guix time-machine`, `build`, `run`). |
| **H3** | F06 | **Sim** | **V03** | — |
| **H4** | F04, F05, F07 | Não | — | Tipografia monoespaçada consistente em todos os blocos de código e comandos de terminal. |
| **H5** | F07 | Não | — | O botão de cópia direta previne erros de digitação de comandos complexos no terminal. |
| **H6** | F05 | Não | — | As flags de compilação (`.ReleaseFast` / `-O3`) são mostradas diretamente no arquivo de build. |
| **H7** | F04, F07 | Não | — | Botões `Copy` agilizam a execução e reprodução dos testes no terminal. |
| **H8** | F04, F06 | Não | — | Visualizador de código limpo com numeração de linhas e sem ornamentos supérfluos. |
| **H9** | F04, F05 | Não | — | Ausência de mensagens de erro confusas ou bloqueios nas rotas de leitura de código. |
| **H10** | F06 | Não | — | Modal About documenta detalhadamente a CPU, quantidade de memória RAM e Kernel da máquina. |

##### 5. Declaração de violações

| ID | Heurística | Tela/estado | Problema observado | Evidência | Severidade | Justificativa da severidade | Recomendação |
| :-: | :-: | :--- | :--- | :--- | :-: | :--- | :--- |
| **V03** | **H3** | F06 (Modal About) | O modal com as informações de hardware só fecha através do clique no botão 'X', não respondendo ao clique na área externa (*backdrop*) nem à tecla `Esc`. | [Ver tela6.jpeg](../assets/11_figma/tela6.jpeg) | **1** | **Frequência baixa / impacto cosmético:** O botão de fechar é visível e cumpre a função, mas quebra a expectativa usual de fechar clicando fora. | Habilitar o fechamento do modal ao clicar na área externa e via tecla `Esc`. |

##### 6. Boas práticas — heurísticas não violadas

| Heurística sem violação | Exemplo no sistema | Evidência | Por que atende |
| :---: | :--- | :--- | :--- |
| **H1** | Feedback de status de cópia | [Ver tela7.jpeg](../assets/11_figma/tela7.jpeg) | O botão `Copy` exibe confirmação visual após o clique, garantindo ao usuário que o comando foi para a área de transferência. |
| **H10** | Documentação e calibração de hardware | [Ver tela6.jpeg](../assets/11_figma/tela6.jpeg) | O modal About documenta as especificações completas do ambiente de teste sem exigir que o usuário procure em fontes externas. |

---

#### 7. Consolidação da equipe

Problemas identificados individualmente consolidados pela equipe:

| ID consolidado | Achados individuais | Heurística | Problema consolidado | Severidade final | Prioridade | Responsável pela correção |
| :---: | :---: | :---: | :--- | :---: | :---: | :---: |
| **HC01** | V01 (A01) | **H5** | Desmarcar todas as séries resulta em área de gráfico vazia sem aviso prévio. | **2** (Menor) | Média | João Pedro Bazoli Palma |
| **HC02** | V02 (A01) | **H7** | Inexistência de atalho para seleção/desmarcação rápida de todas as linguagens na tabela. | **2** (Menor) | Média | João Pedro Bazoli Palma |
| **HC03** | V03 (A02) | **H3** | Modal About só fecha através do botão 'X', não respondendo ao clique fora nem ao `Esc`. | **1** (Cosmético) | Baixa | Augusto Pereira Teixeira |

---

#### 8. Síntese e plano de melhoria

* **Distribuição de severidade:** Foram detectados 3 problemas no total (1 cosmético de grau 1 e 2 menores de grau 2). **Nenhum problema grave (grau 3) ou catastrófico (grau 4)** foi encontrado na interface.
* **Padrões observados:** A interface apresenta alta consistência semiótica e visual, forte conformidade com padrões de desenvolvimento técnico e excelente clareza na apresentação dos dados brutos e scripts.
* **Ajustes para os testes com usuários:**
  1. No teste de usabilidade (Entrega 14), observar se os participantes sentem falta espontânea do atalho de desmarcar todas as linguagens na tarefa UT02.
  2. Verificar se algum participante tenta fechar o modal About clicando fora da janela antes de localizar o botão 'X'.

---

#### Checklist

* [x] Cada integrante fez uma inspeção completa e identificada.
* [x] Todas as telas/estados relevantes foram examinados.
* [x] Estados administrativos, filtros, relatórios, históricos, processamento e erros foram incluídos quando existentes.
* [x] A inspeção avaliou a interface/protótipo, não o mérito técnico do algoritmo/modelo.
* [x] H1–H10 aparecem na matriz de cobertura de cada avaliador.
* [x] Parte de violações contém apenas violações reais, sem forçar exemplos.
* [x] Todo problema tem print/localização e contexto.
* [x] Severidade possui justificativa, não apenas número.
* [x] Recomendação resolve a causa ou reduz o impacto.
* [x] Achados duplicados foram consolidados ao final.
