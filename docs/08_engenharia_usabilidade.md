##### Entrega 8 — Ciclo de vida e engenharia de usabilidade

**Data:** 10/11/2026

**Status:** 🟩 completa

**Responsabilidade:** João Pedro Bazoli Palma e Augusto Pereira Teixeira

###### Objetivo da atividade

Converter o conhecimento sobre usuários, tarefas, plataforma e contexto em **metas de usabilidade verificáveis**, mantendo o caráter iterativo do projeto.

###### Delimitação do sistema interativo

| Camada | O que pertence ao projeto | O que será avaliado em IHC |
| ------ | ------ | ------ |
| **Contribuição técnica do TCC** | Scripts de automação, execução em Linux com GNU Guix, medições de tempo/memória e base empírica de benchmarks. | O algoritmo e a performance do hardware não são avaliados em IHC. |
| **Camada de interação** | Interface web com catálogo, filtros, Dashboard comparativo (T01) e área de código/reprodutibilidade e exportação (T02). | Compreensão visual, facilidade de filtragem, rapidez na comparação, clareza na auditoria e sucesso na exportação. |
| **Integrações/dados simulados** | Base pré-processada em JSON/CSV com benchmarks reais consolidados. | Exportações geram arquivos reais dessa base; não há compilação/execução em tempo real na avaliação. |

--------------------------------------------------------------------------------

###### 1. Características da plataforma

| Característica | Descrição | Consequência para IHC |
| ------ | ------ | ------ |
| **Software** | SPA no navegador (HTML5, CSS3, JS/TS e biblioteca de gráficos). | Sem instalação; exige interface responsiva entre diferentes larguras de desktop e transições rápidas. |
| **Hardware** | Desktop/notebook (1366x768 a 4K). | Layout para mouse/teclado com espaço para gráficos e código. |
| **Capacidades** | Filtragem dinâmica, alternância de métricas e cópia de citações em um clique. | Respostas imediatas reduzem carga cognitiva e aceleram a decisão. |
| **Restrições** | Não compila sob demanda; consome dados homologados. | Deixar claro que os dados vêm de execuções prévias auditadas, não de um playground online. |
| **Conectividade** | Internet padrão; arquivos leves. | Filtros e gráficos funcionam no cliente após o carregamento inicial. |
| **Segurança/privacidade** | O escopo previsto não exige cadastro nem tratamento intencional de dados pessoais do usuário. | Política de privacidade simplificada e sem barreiras de entrada (sem telas de login). |
| **Volume de dados** | Dezenas de benchmarks e centenas de medições por par de linguagens. | Filtros rápidos, paginação e busca para evitar sobrecarga na página inicial. |
| **Tempo de processamento** | Renderização imediata e downloads leves (CSV/JSON/BibTeX). | Feedback visual instantâneo (ex: "Copiado para a área de transferência!"). |
| **Papéis/permissões** | Papel único de consulta e exportação. | Sem telas de controle de acesso ou CRUD administrativo. |

###### 2. Princípios gerais do projeto

###### 2.1 Princípios direcionados ao negócio/domínio

| Princípio/norma | Aplicabilidade | Decisão/requisito | Fonte |
| ------ | ------ | ------ | ------ |
| **Contexto técnico e científico** | P01 e P02 precisam de precisão métrica e rapidez. | Terminologia técnica padrão (*heap*, CPU-bound, flags -O3) sem tutoriais invasivos. | Entregas 1, 3 e 5 |
| **Transparência e Reprodutibilidade** | Pesquisadores demandam conhecer compilação, hardware e automação. | Expor hardware, código-fonte e manifesto reprodutível via GNU Guix. | Entregas 2, 6 e 7 |
| **Privacidade por Design (LGPD)** | Consulta e exportação de dados públicos. | Sem coleta de credenciais, cookies de rastreamento ou dados pessoais (Lei nº 13.709/2018). | Lei nº 13.709/2018 |

###### 2.2 Princípios direcionados à interface

| Princípio/norma | Aplicabilidade | Decisão/requisito | Fonte |
| ------ | ------ | ------ | ------ |
| **Acessibilidade (WCAG 2.1 AA)** | Gráficos legíveis para daltonismo e baixa acuidade. | Contraste 4.5:1 (texto) e 3:1 (gráficos); texturas/rótulos além de cores. | W3C |
| **Carga Cognitiva (Nielsen)** | Comparar opções sem alternar páginas. | Métricas lado a lado e cópia de comandos em um clique. | Nielsen |
| **Tipografia Técnica Especializada** | Leitura de comandos e tabelas. | Fonte monoespaçada (JetBrains Mono) reservada para códigos e dados numéricos, mantendo fonte sem serifa para textos de interface. | Diretrizes de UI |

--------------------------------------------------------------------------------

###### 3. Metas de usabilidade

###### 3.1 Qualitativas

| Meta | Tarefa | Evidência | Justificativa |
| ------ | ------ | ------ | ------ |
| **Compreensão do trade-off** | P01 / T01 | Afirma sem hesitação qual linguagem foi mais rápida e qual usou menos memória. | Evitar esforço cognitivo com grandezas inversas. |
| **Auditabilidade e transparência** | P02 / T02 | Localiza e interpreta as informações necessárias para avaliar as condições em que o benchmark foi produzido. | O rigor acadêmico demanda identificação das variáveis de contorno experimentais. |
| **Clareza nos filtros** | P01 e P02 | Localiza o benchmark sem dúvida sobre os filtros (CPU vs. Memória). | Evitar perda em catálogo denso. |

###### 3.2 Quantitativas

| ID | Dimensão | Métrica | Tarefa | Meta | Como medir |
| ------ | ------ | ------ | ------ | ------ | ------ |
| **MU01** | Eficácia | Conclusão sem ajuda | T01 | 100% dos participantes (sem intervenção) | Observação em teste com usuários |
| **MU02** | Eficiência | Tempo mediano | T01 | ≤ 45 s | Cronômetro do catálogo à resposta |
| **MU03** | Eficácia | Sucesso na exportação | T02 | 100% dos participantes (sem intervenção) | Verificação de download CSV e cópia BibTeX/Guix |
| **MU04** | Eficiência | Tempo mediano | T02 | ≤ 60 s | Cronômetro da tela de código à exportação |
| **MU05** | Satisfação | Facilidade percebida (1 a 5) | T01 e T02 | Média ≥ 4.0 | Pergunta pós-tarefa |

> *Nota sobre a amostragem:* Para testes formativos com amostras reduzidas (participantes proxy), as metas de eficácia MU01 e MU03 foram formuladas operacionalmente como conclusão autônoma sem ajuda externa, compatibilizando os critérios com a escala observável.

###### 3.3 Priorização das metas de usabilidade (Metas de Nielsen)

A priorização das cinco metas de usabilidade propostas por Nielsen fundamenta-se nas necessidades das personas Rafael (P01) e Mariana (P02) e no contexto de uso:

1. **Eficiência (Prioridade Máxima):** Tanto o Tech Lead em decisões de sprint quanto a pesquisadora em análise de dados necessitam de respostas rápidas. Uma vez compreendida a interface, a parametrização de filtros e extração de resultados deve ocorrer sem etapas desnecessárias (refletida em MU02 e MU04).
2. **Baixa Taxa de Erros (Prioridade Alta):** Interpretações errôneas em benchmarks geram decisões arquiteturais inadequadas ou artigos com dados distorcidos. A prevenção de erros na leitura dos eixos e métricas é mandatória (refletida em MU01 e MU03).
3. **Facilidade de Aprendizado (Prioridade Média):** Sendo uma ferramenta web de acesso aberto e eventual, sem treinamentos formais, a interface deve permitir uso intuitivo imediato apoiado em convenções padrão de visualização de dados.
4. **Satisfação Positiva (Prioridade Média):** A aceitação geral da experiência e a clareza visual fortalecem a confiança na plataforma (refletida em MU05).
5. **Facilidade de Memorização (Prioridade Secundária):** Como o fluxo de telas é enxuto (catálogo → comparativo → código/ambiente), a retenção da forma de navegação entre sessões eventuais é apoiada diretamente pela visibilidade dos controles na tela, demandando menor esforço mnemônico.

--------------------------------------------------------------------------------

###### 4. Como o ciclo será iterado

O projeto segue o **Ciclo de Engenharia de Usabilidade de Deborah Mayhew**, organizado em três fases iterativas com avaliações formativas em cada nível:

1. **Análise de Requisitos (Entregas 1 a 5 e 8):** Definição do perfil dos usuários (P01 e P02), estruturação das tarefas (HTA/GOMS/CTT), levantamento de capacidades da plataforma e fixação das metas de usabilidade verificáveis (MU01 a MU05).
2. **Projeto e Prototipação em Três Níveis com Avaliações Intermediárias:**
   * **Nível 1 — Projeto Essencial (Entrega 6):** Prototipação em papel e simulação formativa (*walkthrough*) para avaliar o modelo conceitual e o fluxo das tarefas.
     * *Retorno iterativo:* Se os participantes revelarem incompreensão estrutural da navegação, o fluxo macro é redesenhado antes do avanço para mídia digital.
   * **Nível 2 — Padrões de Telas e Diálogos (Entregas 9 e 10):** Modelagem semiótica e diagramas de interação MoLIC (M01 e M02), definindo o estilo da conversa usuário-sistema e diretrizes de interface.
     * *Retorno iterativo:* Quebras de comunicabilidade ou caminhos sem saída no diálogo forçam a revisão da modelagem antes do protótipo de alta fidelidade.
   * **Nível 3 — Projeto Detalhado (Entrega 11):** Elaboração do protótipo navegável em alta fidelidade no Figma (F01 a F07) com componentes e estilos consolidados.
3. **Avaliações de Usabilidade e Refinamento (Entregas 12 a 14):** Avaliação Heurística de inspeção (Entrega 13) e Testes de Usabilidade com usuários *proxy* (Entrega 14) para mensuração empírica de MU01 a MU05.
   * *Retorno iterativo final:* Caso as metas quantitativas (tempos ou satisfação) não sejam atingidas ou atritos ergonômicos sejam detectados nos testes, o ciclo determina o retorno ao nível de projeto detalhado para ajustes nos padrões de tela e componentes para a versão final.

--------------------------------------------------------------------------------

###### Checklist

* [x] Impacto de IHC em capacidades e restrições explicitado.
* [x] Limite entre TCC técnico e camada interativa claro.
* [x] Processamento simulado explicitado.
* [x] Metas avaliam interação, não substituem métricas do TCC.
* [x] Normas contextualizadas, não copiadas.
* [x] Metas quantitativas mensuráveis e associadas a tarefas/público.
* [x] Eficácia, eficiência e satisfação consideradas.
* [x] Metas verificáveis nas Entregas 12–14.
