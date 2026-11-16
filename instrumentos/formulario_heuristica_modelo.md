### Formulário de avaliação heurística — BMML

**Avaliadores:** Augusto Pereira Teixeira e João Pedro Bazoli Palma (dupla inspeção)

**Versão avaliada:** Protótipo de Telas BMML (Telas F01 a F07)

**Data:** 16/11/2026

**Estados especiais examinados:** Gráfico carregado, seleção/desmarcação de séries, modal About aberto e cópia para clipboard.

#### Cobertura das Heurísticas de Nielsen

| H | Heurística | Fluxos/telas examinados | Violação? | IDs de Problemas |
| :-: | :--- | :--- | :-: | :-: |
| **1** | Visibilidade do status do sistema | F02 (Gráfico), F05 (Download), F07 (Cópia Guix) | Não | — |
| **2** | Compatibilidade sistema–mundo real | F01 (Catálogo), F02 (Eixos cartesianos e métricas) | Não | — |
| **3** | Controle e liberdade do usuário | F03 (Filtrar séries), F06 (Modal About) | Sim | V01 |
| **4** | Consistência e padrões | Todas as telas (tema dark, botões e tabelas) | Não | — |
| **5** | Prevenção de erros | F03 (Desmarcar todas as séries) | Sim | V02 |
| **6** | Reconhecimento em vez de memorização | F02 (Legenda de cores vinculada à tabela) | Não | — |
| **7** | Flexibilidade e eficiência de uso | F03 (Tabela de seleção de linguagens) | Sim | V03 |
| **8** | Estética e design minimalista | F01 a F07 (Painéis limpos, foco em dados) | Não | — |
| **9** | Reconhecer, diagnosticar e recuperar erros | F03 (Aviso de seleção vazia) | Não | — |
| **10** | Ajuda e documentação | F06 (Modal About com calibração de hardware) | Não | — |

#### Registro de Problemas Encontrados

| ID | H | Tela/estado | Ação/condição | Problema identificado | Consequência para o usuário | Severidade (0 a 4) | Recomendação de melhoria |
| :-: | :-: | :--- | :--- | :--- | :--- | :-: | :--- |
| **V01** | H3 | F06 (Modal About) | Usuário abre o modal About | Não fechar ao clicar fora do modal (apenas no 'X'). | Usuário acostumado a clicar no backdrop escuro pode se sentir preso. | 1 (Cosmético) | Permitir fechar o modal clicando na área escura externa ou com a tecla `Esc`. |
| **V02** | H5 | F03 (Tabela) | Desmarcar checkboxes | Permitir desmarcar a última caixa sem aviso prévio. | Risco de deixar o gráfico sem nenhum ponto plotado. | 2 (Simples) | Impedir desmarcar a última série ativa ou exibir alerta inline automático. |
| **V03** | H7 | F03 (Tabela) | Filtrar muitas linguagens | Não ter botão "Selecionar Todas" ou "Desmarcar Todas". | Força o usuário a clicar em 10 caixas se quiser ver só uma linguagem. | 2 (Simples) | Incluir atalho rápido "Deselect All / Select All" no topo da tabela. |
