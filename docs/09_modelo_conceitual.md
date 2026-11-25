##### Entrega 9 — Modelo conceitual e design centrado na comunicação

**Data:** 15/11/2026 (Revisado em 24/11/2026)

**Status:** 🟩 concluída

**Responsabilidade:** João Pedro Bazoli Palma e Augusto Pereira Teixeira

###### Objetivo da atividade

Passar dos cenários de problema da Entrega 4 para a concepção da interação, definindo objetivos, tópicos de conversa e o esquema de signos da interface da plataforma BMML (*Benchmarking Multi-Linguagem*).

###### Transformando resultados técnicos em conceitos compreensíveis

A interface traduz os dados brutos de benchmarking e as receitas Linux/Guix em conceitos familiares e operacionais para os perfis de usuário:

* **Para o Gestor Técnico (P01 - Rafael):** *Trade-off* de desempenho (tempo de execução vs. consumo de memória RAM), dispersão gráfica cartesiana, médias aritméticas sumarizadas por linguagem e filtros por perfil de carga algorítmica.
* **Para a Pesquisadora Acadêmica (P02 - Mariana):** Reprodutibilidade declarativa com GNU Guix (manifest.scm), código-fonte com diretivas de compilação (-O3, .ReleaseFast), especificações da máquina física de testes (CPU, RAM, Kernel) e exportação direta de medições brutas (.csv) e citação bibliográfica (BibTeX).

--------------------------------------------------------------------------------

###### 1. Cenários de interação

###### CI01 — Comparação de desempenho para decisão técnica de arquitetura

**Autor(a):** João Pedro Bazoli Palma — 24.123.041-6

**Origem:** Cenário de problema C01 (Rafael Mendes — Líder Técnico)

Rafael precisa definir a tecnologia mais adequada para um novo microsserviço crítico de pagamentos, com restrição severa de latência e teto de memória, evitando debates subjetivos da equipe.

**[SOLUÇÃO: Rafael acessa a plataforma BMML e navega no catálogo de algoritmos para localizar o teste "MergeSort". Ao abrir a análise comparativa, o sistema apresenta a dispersão cartesiana correlacionando tempo de execução (s) e memória RAM (MB), acompanhada da tabela de médias. Observando que há muitas séries sobrepostas, Rafael desmarca as opções fora do escopo da infraestrutura corporativa, mantendo apenas Go, Rust e Java. Para desaglomerar os pontos líderes, Rafael alterna a escala do eixo vertical para logarítmica. Avaliando visualmente o trade-off de dispersão e conferindo os valores numéricos exatos na tabela, Rafael define a linguagem escolhida e copia as métricas para embasar a ata técnica de arquitetura.]**

###### Diferenças relevantes

| Alteração | Por que foi necessária | Evidência/artefato que justifica |
| :--- | :--- | :--- |
| Catálogo categorizado com busca textual | Reduz o tempo de localização do benchmark representativo. | C01 (Entrega 4) e Meta MU02 (Entrega 8). |
| Gráfico interativo com controle dinâmico de séries e escalas | Permite confrontar tempo vs. memória e isolar linguagens em um clique. | Necessidade de P01 (Entrega 3) e Meta MU01 (Entrega 8). |
| Tabela com ordenação e médias sumarizadas | Elimina a necessidade de cálculos manuais e transcrição em planilhas. | Consequência em C01 (Entrega 4). |

--------------------------------------------------------------------------------

###### CI02 — Auditoria metodológica e exportação de dados para pesquisa

**Autor(a):** Augusto Pereira Teixeira — 24.123.008-5

**Origem:** Cenário de problema C02 (Mariana Costa — Pesquisadora Acadêmica)

Mariana precisa de dados rigorosos sobre o algoritmo MergeSort para fundamentar um artigo científico, mas os revisores exigem comprovação de ambiente determinístico e controle de variáveis.

**[SOLUÇÃO: Mariana acessa a plataforma e busca por "MergeSort" no catálogo, abrindo o experimento. Para validar a paridade de teste, ela inspeciona o bloco de código-fonte e as flags de otimização aplicadas (-O3). Em seguida, ela acessa a seção de reprodutibilidade para auditar a receita do contêiner GNU Guix (manifest.scm), assegurando que o experimento é determinístico. Pelo cabeçalho permanente, ela consulta o painel de especificações de hardware para conferir o processador Ryzen e a memória física da bancada. Confiante no rigor metodológico, Mariana realiza o download do dataset bruto tabular (.csv) e clica no botão de cópia da referência formatada em BibTeX para inclusão imediata em seu artigo.]**

###### Diferenças relevantes

| Alteração | Por que foi necessária | Evidência/artefato que justifica |
| :--- | :--- | :--- |
| Exposição transparente de código, flags e receita Guix | Garante a reprodutibilidade científica e transparência metodológica. | C02 (Entrega 4) e Meta MU03 (Entrega 8). |
| Painel de especificações da máquina física de testes | Fornece dados exatos de CPU, memória e kernel exigidos em artigos científicos. | Princípios de Projeto (Entrega 8). |
| Download direto de CSV bruto e cópia assistida de BibTeX | Elimina digitação manual de números e formatação manual de citações. | Tarefa T02 (Entrega 5) e Meta MU04 (Entrega 8). |

--------------------------------------------------------------------------------

###### 2. Design centrado na comunicação (DCC)

###### CI01 — Conversa de Rafael (Comparação e Decisão Técnica)

| Tópico > Subtópico | Falas e Signos Envolvidos | Intenção / Efeito Esperado |
| :--- | :--- | :--- |
| **Localizar benchmark** | **D:** "Aqui está o catálogo de benchmarks com 13 algoritmos classificados por perfil de carga." <br /> **Signos:** `benchmark`, `algoritmo`, `perfil_carga`. | Localizar o teste representativo com agilidade. |
| **Configurar visualização** | **U:** "Quero confrontar as linguagens selecionadas correlacionando tempo e memória em escala logarítmica." <br /> **D:** "Aqui está a dispersão cartesiana e a tabela de médias sumarizadas." <br /> **Signos:** `tempo_execucao`, `memoria_ram`, `escala_eixo`, `linguagem`, `serie_dados`. | Parametrizar os eixos e isolar as linguagens concorrentes. |
| **Analisar trade-off e decidir** | **U:** "Avaliar o ganho relativo de velocidade e consumo de RAM para definir a tecnologia." <br /> **D:** "Aqui estão os dados numéricos consolidados para fundamentar sua ata técnica." <br /> **Signos:** `media_consolidada`, `selecao_candidatas`. | Consolidar a recomendação arquitetural com respaldo empírico. |

###### CI02 — Conversa de Mariana (Auditoria e Coleta)

| Tópico > Subtópico | Falas e Signos Envolvidos | Intenção / Efeito Esperado |
| :--- | :--- | :--- |
| **Auditar rigor experimental** | **U:** "Quero inspecionar o código, as flags de otimização e a receita declarativa GNU Guix." <br /> **D:** "Aqui estão a implementação, as diretivas -O3 e a receita de reprodução determinística." <br /> **Signos:** `codigo_fonte`, `flags_otimizacao`, `receita_guix`. | Verificar a paridade algorítmica e o determinismo metodológico. |
| **Consultar ambiente físico** | **U:** "Quero consultar as especificações de hardware da bancada de teste." <br /> **D:** "Aqui estão o modelo de processador, volume de RAM física e versão do Kernel Linux." <br /> **Signos:** `ambiente_execucao`, `hardware_cpu`, `memoria_total`, `kernel_so`. | Confirmar as variáveis de contorno da máquina física. |
| **Extrair dados científicos** | **U:** "Baixar dataset tabular bruto e copiar citação acadêmica para o artigo." <br /> **D:** "Arquivo CSV transferido e referência BibTeX copiada para a área de transferência." <br /> **Signos:** `dataset_bruto`, `referencia_bibtex`. | Coletar os artefatos de pesquisa para embasar a publicação. |

--------------------------------------------------------------------------------

###### 3. Mapa de objetivos

###### Dicionário de objetivos

*Nota teórica de formalismo:* Os objetivos dividem-se formalmente entre **Objetivos Finais** (metas de alto nível das personas) e **Objetivos Instrumentais** (meios operacionais necessários para atingir os objetivos finais). No diagrama formal, a relação de instrumentação aponta do objetivo instrumental para o objetivo que ele ajuda a alcançar (Meio $\rightarrow$ Fim).

| ID | Objetivo | Natureza / Classificação | Persona (Papel) | Cenário |
| :--- | :--- | :--- | :--- | :--- |
| **O01** | Escolher linguagem com base em trade-off de desempenho | **Objetivo Final** | P01 (GT — Gestor Técnico) | CI01 |
| **O02** | Auditar rigor dos dados e embasar artigo acadêmico | **Objetivo Final** | P02 (PA — Pesquisadora Acadêmica) | CI02 |
| **O03** | Localizar benchmark de interesse no catálogo | **Objetivo Instrumental** (Pré-condição de O01 e O02) | P01 e P02 (GT e PA) | CI01 e CI02 |
| **O04** | Parametrizar métricas e visibilidade de linguagens | **Objetivo Instrumental** (Instrumenta O01) | P01 (GT) | CI01 |
| **O05** | Analisar visualmente trade-off na dispersão gráfica | **Objetivo Instrumental** (Instrumenta O01) | P01 (GT) | CI01 |
| **O06** | Inspecionar código-fonte, flags de build e receita GNU Guix | **Objetivo Instrumental** (Instrumenta O02) | P02 (PA) | CI02 |
| **O07** | Obter receita GNU Guix para reprodução em terminal | **Objetivo Instrumental** (Instrumenta O02 / Opcional) | P02 (PA) | CI02 |
| **O08** | Baixar dataset bruto tabular em CSV e citação BibTeX | **Objetivo Instrumental** (Instrumenta O02 / Opcional) | P02 (PA) | CI02 |

###### Diagrama do Mapa de Objetivos

*Legenda de papéis:* **GT** = Gestor Técnico (Rafael Mendes — P01); **PA** = Pesquisadora Acadêmica (Mariana Costa — P02).

*Convenção gráfica:* Caixas com contorno sólido representam **Objetivos Finais**; caixas com contorno tracejado representam **Objetivos Instrumentais**.

![Mapa de Objetivos](../assets/09_semiotica/Mapa2.jpg)

--------------------------------------------------------------------------------

###### 4. Esquema conceitual de signos

| Grupo | Signo | Origem | Observações / Semântica de Domínio | Tipo | Restrição | Padrão | Prevenção | Recuperação |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **Catálogo** | `benchmark` | Sistema | Unidade de teste baseada em algoritmo clássico padronizado. | Conceito / Dado | 13 testes homologados | MergeSort | **PP:** Descrição e perfil de carga destacados no card. | Retornar ao catálogo via navegação. |
| **Catálogo** | `perfil_carga` | Usuário | Caracterização do gargalo computacional (CPU-bound vs Memory-bound). | Parâmetro | Valores categóricos válidos | Todos | **PP:** Rótulos semânticos claros nos seletores de categoria. | Alternar categoria no catálogo. |
| **Métricas** | `tempo_execucao` | Sistema | Duração do processamento medido em segundos (eixo X por padrão). | Grandeza contínua | Valores reais positivos | Segundos | **PP:** Identificação de unidade de medida no rótulo do eixo. | Alternar métrica atribuída ao eixo. |
| **Métricas** | `memoria_ram` | Sistema | Consumo máximo de memória residente (RSS) medido em MB (eixo Y). | Grandeza contínua | Valores reais positivos | Megabytes | **PP:** Indicação explícita da escala numérica e grandeza. | Alternar métrica atribuída ao eixo. |
| **Visualização** | `escala_eixo` | Usuário | Modo de representação da grandeza cartesiana (Linear vs Logarítmica). | Controle de estado | Linear ou Log | Linear | **PP:** Indicação visual de estado ativo no switch. | Reverter toggle para escala linear. |
| **Séries** | `linguagem` | Sistema | Tecnologia de compilação avaliada (C, Rust, Go, Zig, etc.). | Identificador | 10 linguagens homologadas | — | **PP:** Cores cromáticas padronizadas e nomes explícitos. | — |
| **Séries** | `selecao_candidatas` | Usuário | Conjunto de linguagens ativas simultaneamente na análise. | Lista paramétrica | Pelo menos 1 linguagem ativa | Todas ativas | **PA:** Bloqueio de esvaziamento total ou alerta de seleção vazia. | Reativar séries na tabela de seleção. |
| **Síntese** | `media_consolidada` | Sistema | Média aritmética e desvio padrão das repetições experimentais. | Dado quantitativo | Somente leitura | Ordem crescente | **PP:** Ordenação automática por menor tempo médio. | Clicar no cabeçalho para reordenar. |
| **Auditoria** | `ambiente_execucao` | Sistema | Especificações da máquina física de bancada (Ryzen 5, 32GB RAM, Kernel). | Metadado técnico | Somente leitura | — | **PP:** Acesso ubíquo permanente no cabeçalho global. | Retornar via link de navegação. |
| **Compilação** | `flags_otimizacao` | Sistema | Parâmetros passados ao compilador (-O3, .ReleaseFast) para assegurar paridade. | Metadado técnico | Somente leitura | — | **PP:** Exibição contextualizada junto ao código-fonte. | — |
| **Reprodutibilidade** | `receita_guix` | Sistema | Manifesto declarativo com canais e pacotes determinísticos GNU Guix. | Script / Comando | Somente leitura | — | **PP:** Realce de sintaxe e botão de cópia direta para o terminal. | Recopiar comando caso necessário. |
| **Exportação** | `dataset_bruto` | Sistema | Arquivo tabular (.csv) contendo todas as medições individuais brutas. | Arquivo de dados | Download direto | .csv UTF-8 | **PP:** Indicação prévia do volume de registros e formato. | Acionar novamente caso ocorra falha de rede. |
| **Exportação** | `referencia_bibtex` | Sistema | Citação acadêmica padronizada do benchmark para editores LaTeX. | Texto formatado | Padrão BibTeX / ABNT | — | **PP:** Confirmação visual temporária ("Copiado para a área de transferência"). | Clicar para recopiar. |

*Legenda:* **PP** = Prevenção Passiva (orientações semânticas e rótulos explícitos); **PA** = Prevenção Ativa (restrições funcionais e travas da interface).

--------------------------------------------------------------------------------

###### Síntese

Para a Entrega 10, a interação é modelada em **dois diagramas MoLIC** focados e integrados:

1. **MoLIC 01 — Rafael (João Pedro):** Cobre a localização do benchmark e a conversa de comparação de desempenho (*trade-off* tempo vs. memória) no visualizador cartesiano (O01, O03, O04, O05), manipulando os signos `benchmark`, `tempo_execucao`, `memoria_ram`, `escala_eixo` e `selecao_candidatas`.
2. **MoLIC 02 — Mariana (Augusto):** Cobre a conversa de auditoria de código, diretivas de compilação, manifesto GNU Guix e ambiente de hardware, concluindo com a extração de dados científicos e citação (O02, O03, O06, O07, O08), manipulando os signos `ambiente_execucao`, `flags_otimizacao`, `receita_guix`, `dataset_bruto` e `referencia_bibtex`.

--------------------------------------------------------------------------------

###### Checklist

* [x] Cenários mostram alterações em relação aos cenários de problema.
* [x] Cada solução identifica autor e cenário de origem.
* [x] Tópicos/falas/signos são coerentes com os objetivos do usuário.
* [x] Mapa de objetivos diferencia claramente Objetivos Finais de Objetivos Instrumentais.
* [x] Esquema de signos estruturado com signos conceituais de domínio e aplicação em tabela única.
* [x] Vocabulário conceitual padronizado para reutilização direta na Entrega 10 e no Figma.
