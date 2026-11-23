#### Entrega 13 — Avaliação de IHC por inspeção heurística

**Data:** 16/11/2026 (Revisado em 23/11/2026)

**Status:** 🟩 concluída

**Responsabilidade:** 1 avaliação completa e independente por integrante sobre todas as telas/estados da interface.

###### Objetivo da atividade

Encontrar problemas de usabilidade por inspeção sistemática da interface com as **10 heurísticas de Nielsen**. Cada avaliador trabalhou individualmente e de forma independente cobrindo todas as telas (F01 a F07); posteriormente, a equipe reuniu-se para consolidar os problemas, comparar achados e definir as prioridades de melhoria. A inspeção avalia estritamente a **qualidade da interface e da interação**, sem entrar no mérito técnico dos algoritmos ou compiladores do TCC.

###### 1. Heurísticas adotadas

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

--------------------------------------------------------------------------------

###### 2. Escopo da inspeção

| Item | Definição |
| ------ | ------ |
| **Versão avaliada** | Protótipo de Telas BMML de Alta Fidelidade (Telas F01 a F07 catalogadas na Entrega 11) |
| **Telas/estados** | F01 (Catálogo), F02 (Dispersão/Eixos), F03 (Tabela de Médias), F04 (Código), F05 (Flags), F06 (Página About BMML), F07 (Receita Guix) |
| **Fluxos inspecionados** | M01 (Comparação de Desempenho) e M02 (Auditoria de Reprodutibilidade e Hardware) |
| **Dispositivo/viewport** | Desktop / Web 1920x1080 |
| **Avaliadores** | A01: João Pedro Bazoli Palma; A02: Augusto Pereira Teixeira |

--------------------------------------------------------------------------------

###### 3. Procedimento individual

Cada avaliador percorreu independentemente o conjunto integral de telas (F01 a F07), inspecionando cada elemento interativo à luz das 10 heurísticas de Nielsen e classificando a severidade (0 a 4) com base na combinação de frequência, impacto e persistência do problema. Como limitação metodológica do projeto, a inspeção foi realizada por 2 avaliadores (o recomendado pela literatura é de 3 a 5 especialistas), o que reforça a necessidade de cobertura completa e cruzada por ambos.

###### Escala de severidade (0–4)

| Grau | Interpretação |
| ------ | ------ |
| **0** | Não é considerado problema de usabilidade. |
| **1** | Problema cosmético; corrigir apenas se houver tempo. |
| **2** | Problema menor; baixa prioridade. |
| **3** | Problema maior; alta prioridade de correção. |
| **4** | Catástrofe de usabilidade; correção obrigatória antes da liberação. |

--------------------------------------------------------------------------------

##### Avaliador A01 — João Pedro Bazoli Palma (Inspeção Completa)

###### 4. Matriz de cobertura das 10 heurísticas

| Heurística | Telas/fluxos examinados | Houve violação? | IDs dos achados | Exemplo de boa prática se não violada |
| ------ | ------ | ------ | ------ | ------ |
| **H1** | F01 a F07 | Não | — | Atualização dinâmica imediata dos pontos no gráfico ao marcar ou desmarcar séries na tabela (F02/F03). |
| **H2** | F01 a F07 | Não | — | Uso de eixos cartesianos convencionais (X = Tempo em segundos; Y = Memória em MB) e terminologia técnica usual do domínio. |
| **H3** | F01 a F07 | Não | — | Preservação dos filtros e estado de análise ao navegar entre abas de código e parâmetros. |
| **H4** | F01 a F07 | Não | — | Cores idênticas para cada linguagem entre os pontos do gráfico, legendas e linhas da tabela de médias. |
| **H5** | F01 a F07 | **Sim** | **V01** | O botão de cópia direta em F04/F07 previne erros de digitação manual de comandos complexos no terminal. |
| **H6** | F01 a F07 | Não | — | Tabela com métricas numéricas explícitas e parâmetros de compilação visíveis diretamente no arquivo de build (F05). |
| **H7** | F01 a F07 | **Sim** | **V02** | Toggles diretos para alternar livremente entre escala linear e logarítmica nos eixos sem recarregar a visualização (F02). |
| **H8** | F01 a F07 | Não | — | Design limpo em tema escuro, alto contraste, sem elementos visuais supérfluos que concorram com os dados. |
| **H9** | F01 a F07 | Não | — | *Não aplicável nos estados normais avaliados* (não foram identificadas mensagens confusas nos fluxos padrão). |
| **H10** | F01 a F07 | Não | — | Seção técnica explicativa antecedendo o script Guix em F07, orientando o usuário sobre a finalidade da receita. |

###### 5. Declaração de violações

| ID | Heurística | Tela/estado | Problema observado | Evidência | Severidade | Justificativa da severidade | Recomendação |
| ------ | ------ | ------ | ------ | ------ | ------ | ------ | ------ |
| **V01** | **H5** | F03 (Tabela de Séries) | A interface permite desmarcar todas as séries da tabela, deixando a área do gráfico vazia sem bloqueio ou aviso preventivo. | [Ver tela3.jpeg](../assets/11_figma/tela3.jpeg) | **2** | **Frequência média / impacto baixo / persistência baixa:** Ocorre sempre que o usuário tenta limpar a tela desmarcando todas as opções; não trava o sistema e é revertido facilmente remarcando uma caixa, mas gera desorientação visual momentânea. | Impedir a desmarcação da última série ativa ou exibir alerta automático inline de seleção vazia. |
| **V02** | **H7** | F03 (Tabela de Séries) | Inexistência de atalhos rápidos para selecionar ou desmarcar todas as séries de uma só vez na tabela de médias. | [Ver tela3.jpeg](../assets/11_figma/tela3.jpeg) | **2** | **Frequência alta / impacto moderado / persistência contínua:** Afeta diretamente qualquer usuário que deseje isolar apenas uma linguagem para análise, exigindo múltiplos cliques repetitivos (8 a 10 cliques desnecessários) a cada comparação. | Adicionar botões de atalho "Select All / Deselect All" logo acima do cabeçalho da tabela. |

###### 6. Boas práticas — heurísticas não violadas

| Heurística sem violação | Exemplo no sistema | Evidência | Por que atende |
| ------ | ------ | ------ | ------ |
| **H4** | Consistência de cores entre gráfico e tabela | [Ver tela2.jpeg](../assets/11_figma/tela2.jpeg) | Cada linguagem preserva rigorosamente o mesmo código cromático tanto na dispersão gráfica quanto na tabela inferior. |
| **H8** | Estética e design minimalista no catálogo | [Ver tela1.jpeg](../assets/11_figma/tela1.jpeg) | Cards de benchmarks organizados em grade regular, destacando apenas nome, tags de carga e métricas essenciais. |

--------------------------------------------------------------------------------

##### Avaliador A02 — Augusto Pereira Teixeira (Inspeção Completa)

###### 4. Matriz de cobertura das 10 heurísticas

| Heurística | Telas/fluxos examinados | Houve violação? | IDs dos achados | Exemplo de boa prática se não violada |
| ------ | ------ | ------ | ------ | ------ |
| **H1** | F01 a F07 | Não | — | Breadcrumbs de navegação ativos indicando com clareza a localização atual do usuário no sistema. |
| **H2** | F01 a F07 | Não | — | Vocabulário alinhado às práticas da engenharia de software e pesquisa experimental (build, run, release, kernel). |
| **H3** | F01 a F07 | **Sim** | **V03** | Facilidade de transição entre abas de arquivos técnicos (main.zig, build.zig, setup.sh) sem barreiras. |
| **H4** | F01 a F07 | Não | — | Tipografia monoespaçada consistente em todos os blocos de código e comandos de terminal em F04, F05 e F07. |
| **H5** | F01 a F07 | **Sim** | **V01** | Redução de erros de digitação via cópia direta de comandos para o terminal. |
| **H6** | F01 a F07 | Não | — | Parâmetros de compilação (.ReleaseFast / -O3) exibidos no contexto do próprio arquivo de configuração (F05). |
| **H7** | F01 a F07 | **Sim** | **V02** | Botões Copy agilizam o fluxo de trabalho de reprodução no terminal. |
| **H8** | F01 a F07 | Não | — | Visualizador de código limpo com numeração de linhas, sem elementos gráficos distrativos. |
| **H9** | F01 a F07 | Não | — | *Não aplicável nos estados estáticos avaliados* (ausência de cenários de ruptura nas capturas homologadas). |
| **H10** | F01 a F07 | Não | — | A página About BMML (F06) documenta detalhadamente a CPU, memória RAM e Kernel da máquina de testes. |

###### 5. Declaração de violações

| ID | Heurística | Tela/estado | Problema observado | Evidência | Severidade | Justificativa da severidade | Recomendação |
| ------ | ------ | ------ | ------ | ------ | ------ | ------ | ------ |
| **V01** | **H5** | F03 (Tabela de Séries) | Ausência de mecanismo preventivo contra remoção total de séries, resultando em visualização vazia. | [Ver tela3.jpeg](../assets/11_figma/tela3.jpeg) | **2** | **Frequência média / impacto baixo / persistência baixa:** Desorienta o usuário iniciante que desseleciona itens sem perceber o esvaziamento imediato do gráfico cartesiano. | Bloquear a desmarcação da última série ou alertar inline. |
| **V02** | **H7** | F03 (Tabela de Séries) | Sobrecarga operacional para isolar dados devido à falta de seleção/desmarcação em lote. | [Ver tela3.jpeg](../assets/11_figma/tela3.jpeg) | **2** | **Frequência alta / impacto moderado / persistência contínua:** Reduz a eficiência em tarefas frequentes de benchmarking comparativo pareado. | Implementar controles de atalho "Select All" e "Deselect All". |
| **V03** | **H3** | F06 (Página About BMML) | A navegação para a página de ambiente exige que o usuário role até o topo para localizar o link "Back to benchmarks" para retornar à análise. | [Ver tela6.jpeg](../assets/11_figma/tela6.jpeg) | **1** | **Frequência baixa / impacto cosmético / persistência pontual:** Não impede o retorno, mas obriga o usuário a rolar páginas extensas para retomar o fluxo de trabalho anterior. | Inserir link de retorno também no rodapé da página ou manter cabeçalho fixo (*sticky*) com a rota de saída visível. |

###### 6. Boas práticas — heurísticas não violadas

| Heurística sem violação | Exemplo no sistema | Evidência | Por que atende |
| ------ | ------ | ------ | ------ |
| **H6** | Exibição direta de parâmetros de build | [Ver tela5.jpeg](../assets/11_figma/tela5.jpeg) | As flags de otimização aparecem contextualizadas no script de automação, eliminando esforço de memorização. |
| **H10** | Documentação e calibração de hardware | [Ver tela6.jpeg](../assets/11_figma/tela6.jpeg) | A página About documenta as especificações completas do ambiente de teste (CPU, RAM, Kernel) de forma estruturada. |

--------------------------------------------------------------------------------

###### 7. Consolidação da equipe

Problemas identificados individualmente consolidados pela equipe após sessão conjunta de alinhamento:

| ID consolidado | Achados individuais | Heurística | Problema consolidado | Severidade final | Prioridade | Responsável pela correção |
| ------ | ------ | ------ | ------ | ------ | ------ | ------ |
| **HC01** | V01 (A01, A02) | **H5** | Desmarcar todas as séries resulta em área de gráfico vazia sem aviso prévio ou bloqueio preventivo. | **2** (Menor) | Média | João Pedro Bazoli Palma |
| **HC02** | V02 (A01, A02) | **H7** | Inexistência de atalhos para seleção e desmarcação em lote de séries na tabela de médias. | **2** (Menor) | Média | João Pedro Bazoli Palma |
| **HC03** | V03 (A02) | **H3** | Retorno da página About BMML para a análise exige rolagem até o topo para acionar o link "Back to benchmarks". | **1** (Cosmético) | Baixa | Augusto Pereira Teixeira |

--------------------------------------------------------------------------------

###### 8. Síntese e plano de melhoria

* **Distribuição de severidade:** Foram detectados 3 problemas no total (1 cosmético de grau 1 e 2 menores de grau 2). **Nenhum problema maior (grau 3) ou catastrófico (grau 4)** foi identificado na interface.
* **Padrões observados:** Os avaliadores constataram forte consistência visual e terminológica em toda a aplicação, boa aderência aos padrões de representação gráfica de dados e ausência de bloqueios severos de navegação nos fluxos inspecionados. Como limitação técnica da inspeção, a avaliação restringiu-se a 2 avaliadores e a capturas de estados operacionais estáticos.
* **Ajustes para os testes com usuários:**
  1. No teste de usabilidade (Entrega 14), observar o tempo e a quantidade de cliques dispensados pelos participantes ao isolar linguagens na tabela de médias (verificação empírica de HC02).
  2. Avaliar se a ausência de gráfico ao desmarcar séries induz dúvidas ou comentários nos participantes (verificação empírica de HC01).
  3. Observar a facilidade de retorno à análise comparativa após a consulta das especificações do sistema (verificação empírica de HC03).

--------------------------------------------------------------------------------

###### Checklist

* [x] Cada integrante fez uma inspeção completa e independente sobre todas as telas (F01 a F07).
* [x] Todas as telas e fluxos principais (M01 e M02) foram examinados.
* [x] A inspeção avaliou a interface/protótipo, não o mérito técnico do algoritmo do TCC.
* [x] H1–H10 aparecem na matriz de cobertura de cada avaliador.
* [x] Parte de violações contém apenas violações reais, sem forçar exemplos.
* [x] Todo problema tem print/localização e contexto correspondente à interface real.
* [x] Severidade possui justificativa baseada em frequência, impacto e persistência.
* [x] Recomendação resolve a causa ou reduz o impacto do problema.
* [x] Achados coincidentes foram consolidados conjuntamente ao final.
* [x] A limitação amostral de 2 avaliadores foi formalmente registrada no método.
