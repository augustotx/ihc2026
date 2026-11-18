### Entrega 4 — Cenários de análise/problema

**Data:** 18/10/2026 (Revisado em 18/11/2026)

**Status:** 🟩 concluída

**Responsabilidade:** João Pedro Bazoli Palma (C01); Augusto Pereira Teixeira (C02).

#### Objetivo da atividade

Descrever e investigar sistematicamente situações reais do problema atual em que o usuário tenta alcançar seus objetivos e encontra dificuldades e rupturas metodológicas. O cenário de análise/problema investiga **o contexto, os atores, o planejamento, as ações, os eventos e a avaliação**, sem antecipar telas, botões ou fluxos da futura interface de IHC.

---

#### Cenário C01 — Seleção e justificativa de linguagem de programação para um novo serviço

* **Autor(a):** João Pedro Bazoli Palma — 24.123.041-6
* **Persona(s) relacionada(s):** P01 — Rafael Mendes (Líder Técnico / *Tech Lead*)
* **Necessidade relacionada:** N01 — Fundamentar a escolha da linguagem de programação com base em dados objetivos e comparáveis de desempenho
* **Situação concreta da Entrega 1 relacionada:** Seção 4.5 — Escolha de linguagem para um projeto específico
* **Hipóteses da Entrega 1 relacionadas:** H01, H03

##### 1. Cenário inicial (C01)

Rafael Mendes é líder técnico de desenvolvimento e precisa definir a linguagem de programação mais adequada para um novo microsserviço de alto rendimento. Para evitar decisões baseadas em preferências pessoais ou modismos, ele pesquisa testes de desempenho na internet. Porém, encontra apenas dados dispersos, contraditórios e sem informações sobre o computador ou as versões utilizadas. Sem uma fonte padronizada, Rafael tenta organizar os dados em uma planilha manual, mas fica inseguro para defender a escolha técnica perante a equipe de desenvolvimento, que pressiona pelo uso de suas linguagens favoritas.

##### 2. Questões de refinamento sistemático (C01)

| # | Elemento característico refinado | Questão de refinamento | Por que precisa ser respondida | Fonte / Forma de obtenção |
| :-: | :--- | :--- | :--- | :--- |
| **Q1** | **Objetivos** | Quais restrições de desempenho e métricas específicas são prioritárias para o novo microsserviço? | Determinar as grandezas que guiam a escolha e evitam decisões generalistas. | Requisitos não-funcionais do sistema e SLA da empresa. |
| **Q2** | **Ambiente / Contexto** | Qual é o prazo limite e as condições de pressão sob as quais Rafael precisa consolidar a recomendação técnica? | Compreender a pressão de tempo e a densidade de trabalho na rotina profissional. | Cronograma da sprint de arquitetura e diretoria. |
| **Q3** | **Atores / Relações sociais** | Quais conflitos e pressões internas a equipe técnica manifesta sobre a escolha da tecnologia? | Mapear as dinâmicas sociais e resistências que exigem fundamentação por evidências. | Observação de reuniões de alinhamento com a equipe de engenharia. |
| **Q4** | **Eventos** | Que evento disparou a necessidade dessa escolha e qual evento marcará a conclusão da tomada de decisão? | Delimitar com precisão o início e o término da atividade no tempo. | Ata de aprovação de novo projeto corporativo. |
| **Q5** | **Planejamento** | Qual estratégia de busca Rafael adota e como organiza o processo investigativo ao encontrar fontes conflitantes? | Explicitar a atividade mental e o método de triagem de dados do profissional. | Entrevista em profundidade com o perfil profissional da persona. |
| **Q6** | **Ações** | Como Rafael tenta tabular e normalizar manualmente as medições extraídas de fóruns e artigos dispersos? | Identificar o esforço operacional e as ferramentas paliativas empregadas hoje. | Análise de planilhas de teste de bancada de projetos anteriores. |
| **Q7** | **Avaliação** | Quais critérios objetivos Rafael adota para julgar se uma fonte é confiável e decidir que já tem dados suficientes? | Identificar os critérios mentais de aceitação e confiança técnica nos dados. | Discussão sobre governança de arquitetura e credibilidade metodológica. |

##### 3. Cenário refinado com referências de refinamento (C01)

Um incidente de sobrecarga no serviço legado de liquidação financeira disparou a abertura de um novo projeto de microsserviço [Q4]. Rafael Mendes, na condição de líder técnico, recebe a responsabilidade de recomendar a linguagem de programação mais adequada às restrições do sistema, tendo como meta estrita garantir baixa latência de execução e teto máximo de 256 MB de memória RAM por instância de contêiner [Q1]. Com apenas dois dias úteis antes da reunião formal de arquitetura com a diretoria executiva [Q2], Rafael inicia seu planejamento delimitando a busca a benchmarks de algoritmos de ordenação e estruturas de dados intensivas em memória [Q5]. Ele pesquisa em repositórios abertos e artigos de engenharia, mas logo se depara com dados contraditórios: o mesmo algoritmo em Rust aparece ora cinco vezes mais rápido, ora com o dobro do consumo de memória em relação a C [Q5]. Para tentar comparar as informações, Rafael gasta horas copiando medições manuais para uma planilha eletrônica, convertendo tempos de milissegundos para segundos e estimando o uso de memória [Q6]. No entanto, ao avaliar a credibilidade das fontes, percebe que nenhum dos artigos cita o processador utilizado, a quantidade de núcleos ativados ou se foram usadas flags de otimização de compilação como `-O3`, o que impede Rafael de considerar as medições válidas para uma decisão de produção [Q7]. Enquanto tenta validar os números, Rafael sofre pressão contínua no escritório: engenheiros seniores insistem em manter C++ por familiaridade da equipe, enquanto desenvolvedores recém-contratados pressionam para reescrever o núcleo em Go [Q3]. Diante da falta de evidências padronizadas e verificáveis, Rafael sente-se inseguro para apresentar a recomendação na reunião com a diretoria [Q2, Q4], ciente de que qualquer escolha equivocada poderá estourar o orçamento de nuvem da empresa [Q1].

##### 4. Elementos característicos extraídos (C01)

| Elemento característico | Evidência textual no cenário refinado |
| :--- | :--- |
| **Atores** | Rafael Mendes (*Tech Lead* decisor), equipe de engenharia de software (pressão técnica) e diretoria executiva (aprovação final). |
| **Ambiente / Contexto** | Escritório corporativo de software, prazo crítico de 2 dias úteis, alta cobrança por redução de custos de infraestrutura. |
| **Objetivos** | Selecionar a linguagem mais adequada sob a restrição de baixa latência e consumo de RAM abaixo de 256 MB por contêiner. |
| **Planejamento** | Focar em algoritmos representativos de carga de memória e tentar isolar variáveis para confrontar resultados discrepantes da web. |
| **Ações** | Pesquisar em fóruns técnicos, copiar medições para planilha eletrônica manual, converter unidades de medida e buscar dados de hardware. |
| **Eventos** | **Gatilho inicial:** Sobrecarga no sistema legado disparando novo microsserviço.<br />**Conclusão:** Reunião decisória formal com a diretoria. |
| **Avaliação** | Rafael julga as fontes da internet como insuficientes e não-confiáveis por omitirem processador, memória física e flags de compilação. |
| **Recursos / Informações** | Artigos na web, repositórios públicos, planilha eletrônica de apoio e documentação de arquitetura da empresa. |
| **Problemas / Rupturas** | Resultados contraditórios na internet, falta de transparência sobre o ambiente de execução e esforço manual improdutivo. |
| **Consequências** | Perda de tempo hábil de projeto, atrito com a equipe técnica e insegurança na tomada de decisão arquitetural. |

##### 5. Implicações para as próximas entregas

Este cenário demonstra a necessidade imperiosa de prover visualizações comparativas que combinem tempo e memória simultaneamente (gráfico de dispersão cartesiano) e deixem explícita a calibração física dos testes, permitindo ao líder técnico fundamentar suas decisões sem perda de tempo em planilhas manuais.

---

#### Cenário C02 — Comparação e auditoria de linguagens para trabalho acadêmico

* **Autor(a):** Augusto Pereira Teixeira — 24.123.008-5
* **Persona(s) relacionada(s):** P02 — Mariana Costa (Pesquisadora e Mestranda)
* **Necessidade relacionada:** N02 — Acessar dados confiáveis e detalhados para embasar trabalhos e pesquisas acadêmicas
* **Situação concreta da Entrega 1 relacionada:** Seção 4.5 — Comparação de desempenho de linguagens para estudos
* **Hipóteses da Entrega 1 relacionadas:** H01, H03, H04

##### 1. Cenário inicial (C02)

Mariana Costa é estudante de mestrado e precisa comparar a velocidade de diferentes linguagens de programação para um artigo. Ela pesquisa testes na internet, mas só encontra dados espalhados, pouco confiáveis e sem informações sobre qual computador foi usado. Sem fontes seguras, Mariana precisa baixar os códigos e rodar os testes manualmente no próprio computador, o que toma muito tempo e limita seus resultados.

##### 2. Questões de refinamento sistemático (C02)

| # | Elemento característico refinado | Questão de refinamento | Por que precisa ser respondida | Fonte / Forma de obtenção |
| :-: | :--- | :--- | :--- | :--- |
| **Q1** | **Objetivos** | Quais dados experimentais e evidências de compilação Mariana necessita extrair para fundamentar sua pesquisa? | Definir o conjunto de dados indispensável para a validade do experimento científico. | Metodologia da dissertação de mestrado. |
| **Q2** | **Ambiente / Contexto** | Em quais prazos e sob quais condições de infraestrutura acadêmica Mariana está conduzindo a comparação? | Caracterizar a urgência e as limitações de hardware enfrentadas pelo pesquisador. | Calendário de submissão do congresso e condições do laboratório. |
| **Q3** | **Atores / Relações sociais** | Quem são as partes acadêmicas que auditam o trabalho de Mariana e exigem comprovação metodológica dos testes? | Identificar o rigor avaliativo e as exigências do meio científico sobre os dados. | Reuniões de orientação com o orientador e diretrizes dos revisores de artigos (*peer review*). |
| **Q4** | **Eventos** | Qual evento acadêmico iniciou a necessidade dos benchmarks e o que ocorre após a obtenção dos dados? | Estabelecer o marco temporal inicial e a consequência da entrega do experimento. | Chamada de trabalhos (*Call for Papers*) de simpósio científico. |
| **Q5** | **Planejamento** | Qual método Mariana planeja seguir para selecionar os algoritmos antes de decidir compilar tudo manualmente? | Explicitar a estratégia investigativa e a tomada de decisão da pesquisadora. | Planejamento experimental de bancada acadêmica. |
| **Q6** | **Ações** | Como Mariana tenta contornar a falta de reprodutibilidade da web executando testes locais em seu notebook? | Descrever a sequência de tarefas operacionais, scripts e limitações de bancada. | Observação direta de rotina de testes em ambiente Linux. |
| **Q7** | **Avaliação** | Quais critérios metodológicos Mariana utiliza para considerar se um teste de terceiros possui validade científica? | Definir os requisitos de reprodutibilidade formal (determinismo, hardware e flags). | Critérios epistemológicos de reprodutibilidade computacional (ACM / SBC). |

##### 3. Cenário refinado com referências de refinamento (C02)

A aprovação do resumo de sua pesquisa para apresentação no Simpósio de Sistemas Computacionais disparou o prazo fatal de duas semanas para a submissão do manuscrito completo [Q4]. Mariana Costa precisa incluir uma seção experimental quantitativa comparando tempo de CPU e consumo de memória entre C, Rust e Zig, com o objetivo de avaliar se as garantias de segurança de memória das linguagens modernas impõem sobrecusto computacional mensurável [Q1]. Trabalhando no laboratório da universidade com um notebook pessoal de recursos limitados [Q2], Mariana planeja inicialmente aproveitar medições públicas de projetos abertos de benchmarking para evitar a reexecução manual de dezenas de suítes de testes [Q5]. Contudo, ao avaliar os relatórios disponíveis na internet, constata que nenhum artigo descreve as flags de otimização utilizadas no compilador (como `.ReleaseFast` ou `-O3`), tampouco detalham a frequência da CPU, a memória RAM física ou a versão do kernel Linux adotado [Q7]. Seu orientador de mestrado já a alertou rigorosamente de que os revisores do simpósio rejeitam artigos que utilizam dados de bancada sem comprovação de ambiente determinístico e controle de variáveis [Q3, Q7]. Diante da falta de fontes críveis, Mariana altera seu plano e decide reproduzir os testes por conta própria: clona repositórios de algoritmos, escreve scripts manuais em Shell para medir o tempo via `/usr/bin/time -v` e compila cada programa individualmente em sua máquina [Q6]. O processo de compilação e execução repetida consome mais de seis horas consecutivas de processamento, travando seu notebook devido ao esgotamento de memória e gerando dados enviesados pela interferência de processos do sistema operacional [Q2, Q6]. Ao avaliar os resultados preliminares, Mariana conclui que seus próprios dados não possuem o isolamento térmico e a calibração de bancada necessários para publicação [Q7], deixando-a frustrada e com o cronograma de submissão do artigo criticamente ameaçado [Q2, Q4].

##### 4. Elementos característicos extraídos (C02)

| Elemento característico | Evidência textual no cenário refinado |
| :--- | :--- |
| **Atores** | Mariana Costa (pesquisadora/mestranda), professor orientador e revisores científicos (*reviewers* do simpósio). |
| **Ambiente / Contexto** | Laboratório acadêmico, bancada com notebook pessoal, prazo rígido de 2 semanas para submissão do artigo. |
| **Objetivos** | Obter dados experimentais rigorosos e auditáveis de tempo e memória entre C, Rust e Zig para validar hipótese científica. |
| **Planejamento** | Buscar primeiro dados secundários confiáveis na web; falhando isso, montar ambiente de bancada local para execução empírica. |
| **Ações** | Clonar códigos-fonte de algoritmos, criar scripts manuais de automação (`time -v`), compilar programas e monitorar logs de terminal. |
| **Eventos** | **Gatilho inicial:** Aprovação de trabalho científico exigindo manuscrito completo em 2 semanas.<br />**Conclusão:** Submissão do artigo com a seção experimental validada. |
| **Avaliação** | Mariana e seu orientador avaliam que testes sem especificação de flags e determinismo ambiental não possuem validade para publicação. |
| **Recursos / Informações** | Artigos na web, terminal Linux, compiladores (GCC, Clang, rustc, zig), scripts Bash e notebook pessoal. |
| **Problemas / Rupturas** | Falta de dados metodológicos na internet, esforço manual excessivo, travamento de máquina pessoal e falta de reprodutibilidade. |
| **Consequências** | Perda de horas úteis de pesquisa, estresse com prazos acadêmicos e risco iminente de rejeição do artigo científico. |

##### 5. Implicações para as próximas entregas

O cenário de Mariana demonstra que a interface não pode ser apenas um visualizador gráfico de médias; ela precisa obrigatoriamente fornecer transparência de auditoria: exibição do hardware de bancada (CPU, RAM, Kernel), acesso às diretivas de compilação e disponibilização de comandos declarativos de reprodução em contêineres (como GNU Guix), que alimentarão as tarefas da Entrega 5 e a modelagem do MoLIC M02.

---

#### Checklist

* [x] Há um cenário completo, refinado e com autoria individual para cada integrante.
* [x] Cada cenário possui título, ator, objetivo, contexto, planejamento, ações, eventos e avaliação.
* [x] Os cenários descrevem rigorosamente a situação do problema atual, sem antecipar a futura interface.
* [x] O refinamento cobre de forma sistemática os 7 elementos característicos recomendados pela literatura de IHC.
* [x] Cada questão de refinamento está explicitamente associada ao elemento característico correspondente.
* [x] As respostas das questões de refinamento estão claramente sinalizadas na narrativa refinada através de colchetes `[Q1]`, `[Q2]` etc.
* [x] A tabela de elementos extraídos reflete fielmente os 7 elementos de Carroll/Rosson.
* [x] Questões inválidas ou redundantes com o cenário inicial foram substituídas por investigações reais.
* [x] Expressões absolutas como "linguagem ideal" foram eliminadas em prol de "adequação aos requisitos".
* [x] Os cenários e personas estão formalmente conectados na matriz de rastreabilidade.
