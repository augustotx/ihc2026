### Entrega 2 — Público-alvo e análise de concorrência

**Data:** 02/09/2026 (Revisado em 18/11/2026)

**Status:** 🟩 concluída

**Responsabilidade:** Cada integrante analisou 1 concorrente/interface representativa; síntese comparativa e recomendações consolidadas pela equipe.

#### Objetivo da atividade

Compreender soluções do mesmo domínio e interfaces familiares ao público-alvo para identificar convenções de interação, padrões de projeto, problemas recorrentes de usabilidade e oportunidades de design para a ferramenta BMML.

---

#### Entrada obrigatória da Entrega 1

Mapeamento inicial de alternativas e ferramentas do domínio revisitado sistematicamente:

| Item citado na Entrega 1 | Tipo | Por que foi citado | Status inicial | Decisão nesta entrega |
| :--- | :---: | :--- | :---: | :---: |
| **Rosetta Code** | Análogo | Repositório colaborativo de algoritmos implementados em centenas de linguagens. | F | Analisado por João Pedro Bazoli Palma (C02). |
| **Debian Benchmark Game** | Concorrente direto | Agregador de métricas comparativas (tempo, memória e CPU) em tabelas de dados. | F | Analisado por Augusto Pereira Teixeira (C01). |
| **Repositório Dave Plummer (Primes)** | Processo manual | Benchmark de números primos executado em dezenas de linguagens em terminal. | F | Descartado para análise de UI (não possui interface gráfica/web). |

---

#### 1. Público-alvo desta análise

Desenvolvedores de software de sistemas, arquitetos técnicos (*Tech Leads*) e pesquisadores/estudantes de computação que necessitam comparar métricas objetivas de desempenho e consumo de memória entre diferentes linguagens de programação sob condições controladas de execução.

---

#### 2. Concorrentes diretos/indiretos

##### Análise C01 — Debian Benchmark Game

* **Autor(a):** Augusto Pereira Teixeira — 24.123.008-5
* **Tipo:** Concorrente direto
* **Link oficial:** [suspicious link removed]
* **Data de acesso:** 02/09/2026

###### Contexto e proposta

Agregador estático de testes de desempenho entre linguagens compiladas e interpretadas. Organiza medições de tempo de CPU, consumo de memória (KB) e tamanho do código-fonte em tabelas ordenáveis, acompanhadas de breves descrições do problema matemático e dos parâmetros de máquina.

###### Funcionalidades relevantes (C01)

| Funcionalidade | Como é realizada | Evidência visual | Observação de IHC |
| :--- | :--- | :--- | :--- |
| **Visualização de tabelas densas** | Seleciona-se um problema na lista lateral da página inicial. | `debian_table.png` | Apresenta os dados tabulares em lote. Permite inspeção de várias linguagens simultaneamente, mas sofre com excesso de informação sem agrupamento visual. |
| **Ordenação por métrica** | Clique no cabeçalho das colunas (Secs, Mem, Busy). | `debian_sort.png` | A ordenação funciona de forma descendente direta. É eficiente para identificar o primeiro colocado, mas não permite isolar subconjuntos de linguagens. |
| **Auditoria de código e compilação** | Clique sobre o nome da implementação na tabela. | `debian_source.png` | Exibe o código-fonte integral com destaque de sintaxe, flags do compilador utilizadas e linha de comando de execução. |
| **Descrição do algoritmo** | Clique no link "description" no topo da página. | `debian_nbody.png` | Textos concisos delimitando as regras do teste para evitar implementações que burlem o algoritmo base. |

---

##### Análise C02 — Rosetta Code

* **Autor(a):** João Pedro Bazoli Palma — 24.123.041-6
* **Tipo:** Análogo de domínio
* **Link oficial:** [suspicious link removed]
* **Data de acesso:** 02/09/2026

###### Contexto e proposta

Enciclopédia colaborativa baseada no modelo *wiki* que apresenta a resolução de um mesmo problema de programação em centenas de linguagens. Foca na semântica, sintaxe e idiomática de cada linguagem, organizando as implementações em seções sequenciais na mesma página.

###### Funcionalidades relevantes (C02)

| Funcionalidade | Como é realizada | Evidência visual | Observação de IHC |
| :--- | :--- | :--- | :--- |
| **Navegação por tarefas (*tasks*)** | Seleção a partir de lista alfabética de problemas. | `rosetta_helloworld.png` | Navegação simples por links diretos, porém com alta sobrecarga visual devido à quantidade massiva de tarefas cadastradas. |
| **Exibição paralela de implementações** | Rolagem vertical da página da tarefa selecionada. | `rosetta_happy_numbers.png` | Concentra diversas linguagens na mesma página, permitindo comparar estilos de código sem trocar de aba. |
| **Destaque de sintaxe (*syntax highlighting*)** | Formatação automática nos blocos de código. | `rosetta_c_highlight.png` | Aumenta a legibilidade de estruturas e palavras-chave nas linguagens suportadas pela ferramenta de realce. |

---

###### Experiência do usuário e inspeção técnica

Não foram localizados estudos formais de usabilidade publicados sobre os dois sites. A avaliação a seguir fundamenta-se em **inspeção analítica realizada pela equipe técnica**, orientada por boas práticas de IHC e ergonomia de interfaces:

* **C01 (Debian Game):** A interface é minimalista e rápida no carregamento, mas impõe alta carga cognitiva. A ausência de representação visual (gráficos de dispersão) força o usuário a realizar cálculos mentais para compreender a relação de *trade-off* entre tempo e consumo de memória.
* **C02 (Rosetta Code):** A estrutura de *wiki* tradicional favorece a indexação de busca textual, mas falha gravemente na filtragem: o usuário precisa realizar rolagem extensa de tela (*infinite scroll* manual) para encontrar a linguagem desejada em meio a centenas de blocos não filtráveis.

###### Modelo de acesso

Ambas as ferramentas são gratuitas, públicas e de código aberto, operando na web sem barreiras de autenticação ou cadastro.

###### Padrões percebidos e hipóteses sobre o perfil de uso

* **C01:** Adota densidade informacional estrita, vocabulário altamente técnico e dispensa tutoriais. **Hipótese de IHC:** Usuários com maturidade técnica valorizam acesso imediato aos dados brutos e métricas, mas demandam mecanismos de ordenação e filtros para reduzir ruído visual.
* **C02:** Organiza soluções como documentação de referência comparativa. **Hipótese de IHC:** Ter o código-fonte visível lado a lado com os resultados aumenta a confiabilidade da comparação.

---

###### Pontos fortes, limitações e implicações para o BMML

| Produto | Pontos fortes observados | Limitações observadas | Implicações para o BMML |
| :---: | :--- | :--- | :--- |
| **C01** | Transparência de flags e comandos de compilação; registro de versões de bibliotecas e histórico de execuções. | Total ausência de gráficos interativos; impossibilidade de desmarcar linguagens não desejadas na tabela. | Adotar gráfico cartesiano de dispersão (Tempo × Memória) com toggles paramétricos e sincronizado a uma tabela de dados. |
| **C02** | Código-fonte acessível diretamente com realce de sintaxe; descrição conceitual clara do objetivo do algoritmo. | Ausência completa de filtros por família de linguagem ou paradigma; poluição visual por rolagem excessiva. | Implementar abas dedicadas de código e filtros diretos no catálogo de problemas (`CPU-bound` vs. `Memory-bound`). |

---

#### 3. Softwares que o público-alvo usa no cotidiano

Análise de plataformas técnicas de referência que moldam os modelos mentais e hábitos de interação do perfil de usuário:

| Software | Por que o público utiliza | Padrões de interface relevantes | Lições e convenções aplicáveis ao BMML |
| :--- | :--- | :--- | :--- |
| **GitHub** | Versionamento de código, auditoria de alterações e documentação de software. | Blocos de código monoespaçados com numeração de linhas, botões integrados de cópia direta (`Copy`) e abas de navegação de arquivos. | Incorporar o padrão de bloco de código com botão `Copy` para comandos de terminal e scripts determinísticos do GNU Guix. |
| **Stack Overflow** | Consulta técnica de problemas, discussões e comparação de soluções algorítmicas. | Identificação de tópicos via tags semânticas, tipografia com alto contraste e distinção clara entre texto explicativo e código executável. | Utilizar tags visuais para caracterizar o perfil de processamento dos algoritmos (`CPU-bound`, `Memory-bound`). |

---

#### 3.1 Padrões de interface relevantes ao escopo de IHC

| Padrão observado | Origem | Tarefa do usuário que justifica | Vantagem de IHC | Risco / Limitação de design | Decisão no BMML |
| :--- | :---: | :--- | :--- | :--- | :---: |
| **Catálogo com tags semânticas** | Stack Overflow / C02 | Localizar e selecionar o benchmark de interesse. | Categoriza algoritmos por perfil de carga, agilizando a busca de casos representativos. | Excesso de tags pode fragmentar a navegação. | **Adotado** (Filtro por CPU-bound e Memory-bound no catálogo F01). |
| **Gráfico de dispersão com toggles** | Literatura de visualização de dados | Comparar o *trade-off* relativo entre velocidade e memória. | Permite correlacionar duas grandezas contínuas em um único plano visual. | Pode haver sobreposição de pontos caso a escala seja linear. | **Adotado** (Gráfico com switches `Log X` e `Log Y` na tela F02). |
| **Tabela com filtros de séries (checkboxes)** | C01 | Isolar linguagens específicas para confronto direto. | Reduz a carga cognitiva permitindo ocultar séries irrelevantes para a análise do usuário. | Risco de deixar a área do gráfico vazia caso tudo seja desmarcado. | **Adotado** (Tabela sincronizada com checkboxes na tela F03). |
| **Bloco de comando com cópia assistida** | GitHub | Auditar e reproduzir o ambiente experimental no terminal. | Acelera a reprodução e elimina erros motores de digitação de instruções complexas. | Dependência do suporte à área de transferência do navegador. | **Adotado** (Botão `Copy` na receita do Guix na tela F07). |
| **Modal sobreposto sob demanda** | Convenções web modernas | Checar especificações da máquina física de testes. | Evita a quebra do fluxo da análise atual, sem recarregar a página ou perder o estado dos filtros. | Deve prever múltiplos métodos de fechamento (botão 'X', clique externo e `Esc`). | **Adotado** (Modal `About` ubíquo na tela F06). |

---

#### 4. Síntese comparativa da equipe

Avaliação sistemática dos produtos com base nas tarefas prioritárias do domínio de benchmarking:

| Critério operacional de tarefa | C01 (Debian Game) | C02 (Rosetta Code) | Oportunidade e decisão para o BMML |
| :--- | :--- | :--- | :--- |
| **Localização rápida de algoritmos** | Lista alfabética longa em texto puro. | Índice massivo em formato *wiki* com mais de 1000 itens. | Adotar grade de cartões (*cards*) organizados por categoria de processamento com busca rápida. |
| **Comparação direta de métricas** | Boa apresentação tabular numérica, mas sem gráficos. | Inexistente (foco exclusivo em sintaxe e código). | Unir visualização cartesiana de dispersão a uma tabela de médias numéricas exatas. |
| **Filtragem seletiva de dados** | Ordenação de colunas em sentido único; sem ocultação de linhas. | Inexistente (rolagem vertical obrigatória). | Checkboxes individuais por linguagem, permitindo isolar apenas os competidores de interesse. |
| **Acesso a código e compilação** | Página dedicada com código estático e flags textuais. | Blocos de código sequenciais na mesma página. | Aba de código integrada na mesma tela, exibindo flags de build e script de contêiner. |
| **Garantia de reprodutibilidade** | Descreve versão do compilador, mas não fornece contêiner. | Não aborda ambiente de execução ou reprodutibilidade. | Disponibilizar receita declarativa de contêiner GNU Guix com botão de cópia direta. |
| **Acessibilidade e ergonomia visual** | Alto contraste nativo, mas sem suporte a leitores modernos ou responsividade. | Suporte parcial a ajuste de tamanho de fonte nativo do MediaWiki. | Tema escuro com alto contraste WCAG AA, tipografia sem serifa para dados e monoespaçada para código. |

---

#### 5. Recomendações derivadas para o projeto

Recomendações fundamentadas nas observações empíricas das interfaces, conectadas diretamente às metas e tarefas do BMML:

| ID | Recomendação de Design | Origem no estudo | Tarefa / Objetivo apoiado | Impacto esperado na interação | Status no projeto |
| :---: | :--- | :---: | :--- | :--- | :---: |
| **RC01** | **Interface limpa e focada nos dados:** Apresentar gráficos e tabelas com baixa densidade decorativa, priorizando espaço de tela para dados brutos. | C01 | T01 (Comparar métricas de desempenho). | Reduz fadiga visual e permite visualização contínua de múltiplos benchmarks em tela cheia. | **Adotada** (Telas F01 e F02) |
| **RC02** | **Centralização da análise na mesma visualização:** Manter gráfico e tabela de médias na mesma tela, sem exigir troca constante de páginas. | C02 / C01 | T01 (Avaliar ganho relativo). | Elimina a sobrecarga de memória de trabalho ao comparar números e curvas visuais. | **Adotada** (Telas F02 e F03) |
| **RC03** | **Descrições conceituais dos problemas:** Exibir breve contextualização sobre a natureza da carga do benchmark (ex.: CPU vs. memória). | C01 / C02 | T01 / T02 (Selecionar algoritmo). | Ajuda o usuário a compreender por que uma linguagem teve comportamento anômalo naquele caso específico. | **Adotada** (Tags e cards em F01) |
| **RC04** | **Explicitação rigorosa de métricas e eixos:** Declarar expressamente as unidades de medida (segundos, MB) e prover chaves de escala logarítmica. | C01 | T01 (Analisar trade-off de recursos). | Previne distorções na interpretação de ordens de grandeza discrepantes entre linguagens compiladas e interpretadas. | **Adotada** (Controles de eixos em F02) |
| **RC05** | **Filtragem dinâmica de séries com checkboxes:** Permitir ligar e desligar linguagens diretamente na tabela de médias. | Ausência em C01 e C02 | T01 / T02 (Isolar linguagens de interesse). | Permite comparar concorrentes diretos (ex.: C vs. Rust) sem a poluição visual das demais séries no gráfico. | **Adotada** (Tabela de séries em F03) |
| **RC06** | **Reprodutibilidade e auditoria em um clique:** Fornecer o script de contêiner e comandos de compilação acompanhados de botão de cópia assistida. | C01 / GitHub | T02 (Validar ambiente e citar teste). | Garante credibilidade científica ao estudo e economiza tempo do auditor ao reproduzir os testes localmente. | **Adotada** (Aba Guix em F07) |
| **RC07** | **Acesso ubíquo aos dados de calibração física:** Disponibilizar os parâmetros de hardware (CPU, RAM, Kernel) em modal sobreposto acessível de qualquer tela. | C01 | T01 / T02 (Conferir especificações de hardware). | Evita que o usuário precise sair da análise gráfica em andamento para verificar em que máquina os testes rodaram. | **Adotada** (Modal About em F06) |

---

#### Referências

* Debian Benchmark Game Team. *The Computer Language Benchmarks Game*. Disponível em: <[https://benchmarksgame-team.pages.debian.net/benchmarksgame/index.html]>. Acesso em: 02 set. 2026.
* Rosetta Code Consortium. *Rosetta Code: Chrestomathy of Computer Programs*. Disponível em: <[https://rosettacode.org/wiki/Rosetta_Code]>. Acesso em: 02 set. 2026.
* GitHub Docs. *About READMEs and Code Navigation*. Disponível em: <[https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/about-readmes]>. Acesso em: 02 set. 2026.

---

#### Checklist

* [x] O mapa inicial de alternativas da Entrega 1 foi revisitado e aprofundado.
* [x] Hipóteses relevantes sobre mercado/padrões foram atualizadas na rastreabilidade com base nas evidências.
* [x] Há pelo menos uma análise completa e identificada por integrante.
* [x] Cada análise contém referências a prints legíveis e pertinentes de estados reais.
* [x] Foram analisados concorrentes e interfaces de referência de uso cotidiano do público.
* [x] Padrões de interface foram justificados como respostas a tarefas reais, e não por mera imitação.
* [x] A seção de opiniões de UX registra inspeção técnica fundamentada e fontes explícitas.
* [x] A síntese comparativa adota critérios operacionais e objetivos de tarefas.
* [x] As recomendações compõem uma matriz rastreável com origem, objetivo e impacto.
