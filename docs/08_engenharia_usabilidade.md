### Entrega 8 — Ciclo de vida e engenharia de usabilidade

**Data:** 10/11/2026

**Status:** 🟩 completa

**Responsabilidade:** João Pedro Bazoli Palma e Augusto Pereira Teixeira

#### Objetivo da atividade

Converter o conhecimento sobre usuários, tarefas, plataforma e contexto em **metas de usabilidade verificáveis**, mantendo o caráter iterativo do projeto.

#### Delimitação do sistema interativo

| Camada | O que pertence ao projeto | O que será avaliado em IHC |
|---|---|---|
| **Contribuição técnica do TCC** | Scripts de automação, execução em Linux com GNU Guix, medições de tempo/memória e base empírica de benchmarks. | O algoritmo e a performance do hardware não são avaliados em IHC. |
| **Camada de interação** | Interface web com catálogo, filtros, Dashboard comparativo (T01) e área de código/reprodutibilidade e exportação (T02). | Compreensão visual, facilidade de filtragem, rapidez na comparação, clareza na auditoria e sucesso na exportação. |
| **Integrações/dados simulados** | Base pré-processada em JSON/CSV com benchmarks reais consolidados. | Exportações geram arquivos reais dessa base; não há compilação/execução em tempo real na avaliação. |

---

#### 1. Características da plataforma

| Característica | Descrição | Consequência para IHC |
|---|---|---|
| **Software** | SPA no navegador (HTML5, CSS3, JS/TS e biblioteca de gráficos). | Sem instalação; exige interface responsiva e transições rápidas. |
| **Hardware** | Desktop/notebook (1366x768 a 4K). | Layout para mouse/teclado com espaço para gráficos e código. |
| **Capacidades** | Filtragem dinâmica, alternância de métricas e cópia de citações em um clique. | Respostas imediatas reduzem carga cognitiva e aceleram a decisão. |
| **Restrições** | Não compila sob demanda; consome dados homologados. | Deixar claro que os dados vêm de execuções prévias auditadas, não de um playground online. |
| **Conectividade** | Internet padrão; arquivos leves. | Filtros e gráficos funcionam no cliente após o carregamento inicial. |
| **Segurança/privacidade** | Sistema público, sem login ou dados pessoais. | Sem risco de vazamento; política de privacidade simplificada e sem barreiras de entrada. |
| **Volume de dados** | Dezenas de benchmarks e centenas de medições por par de linguagens. | Filtros rápidos, paginação e busca para evitar sobrecarga na página inicial. |
| **Tempo de processamento** | Renderização imediata e downloads leves (CSV/JSON/BibTeX). | Feedback visual instantâneo (ex: "Copiado para a área de transferência!"). |
| **Papéis/permissões** | Papel único de consulta e exportação. | Sem telas de controle de acesso ou CRUD administrativo. |

#### 2. Princípios gerais do projeto

| Princípio/norma | Aplicabilidade | Decisão/requisito | Fonte |
|---|---|---|---|
| **Contexto técnico e científico** | P01 e P02 precisam de precisão métrica e rapidez. | Terminologia técnica padrão (*heap*, CPU-bound, flags `-O3`) sem tutoriais invasivos. | Entregas 1, 3 e 5 |
| **Transparência e Reprodutibilidade** | Pesquisadores só confiam conhecendo compilação, hardware e automação. | Expor hardware, código-fonte e manifesto reprodutível via GNU Guix. | Entregas 2, 6 e 7 |
| **Acessibilidade (WCAG 2.1 AA)** | Gráficos legíveis para daltonismo e baixa acuidade. | Contraste 4.5:1 (texto) e 3:1 (gráficos); texturas/rótulos além de cores. | W3C |
| **Privacidade por Design (LGPD)** | Consulta e exportação de dados públicos. | Sem cookies, login ou dados pessoais. | Lei nº 13.709/2018 |
| **Carga Cognitiva (Nielsen)** | Comparar opções sem alternar páginas. | Métricas lado a lado e cópia em um clique. | Nielsen |

---

#### 3. Metas de usabilidade

##### 3.1 Qualitativas

| Meta | Tarefa | Evidência | Justificativa |
|---|---|---|---|
| **Compreensão do trade-off** | P01 / T01 | Afirma sem hesitação qual linguagem foi mais rápida e qual usou menos memória. | Evitar esforço cognitivo com grandezas inversas. |
| **Confiança e rigor** | P02 / T02 | Relata que manifesto Guix e hardware tornam os dados confiáveis. | Transparência é a principal dor dos pesquisadores. |
| **Clareza nos filtros** | P01 e P02 | Localiza o benchmark sem dúvida sobre os filtros (CPU vs. Memória). | Evitar perda em catálogo denso. |

##### 3.2 Quantitativas

| ID | Dimensão | Métrica | Tarefa | Meta | Como medir |
|---|---|---|---|---|---|
| **MU01** | Eficácia | Conclusão sem ajuda | T01 | ≥ 90% | Observação em teste |
| **MU02** | Eficiência | Tempo mediano | T01 | ≤ 45 s | Cronômetro do catálogo à resposta |
| **MU03** | Eficácia | Sucesso na exportação | T02 | ≥ 95% | Verificação de download CSV e cópia BibTeX |
| **MU04** | Eficiência | Tempo mediano | T02 | ≤ 60 s | Cronômetro da tela de código à exportação |
| **MU05** | Satisfação | SEQ (1–7) | T01 e T02 | ≥ 5.5 | Pergunta pós-tarefa |

##### 3.3 Priorização

| Meta | Peso | Justificativa |
|---|---|---|
| MU01 | 30% | Sem resposta comparativa autônoma, o propósito central falha. |
| MU03 | 25% | Exportação é o principal diferencial acadêmico. |
| MU02 | 20% | Velocidade é crítica para gestores. |
| MU05 | 15% | Mede aceitação geral da experiência. |
| MU04 | 10% | Precisão e completude superam alguns segundos no contexto acadêmico. |
| **Total** | **100%** | |

---

#### 4. Como o ciclo será iterado

Ciclo iterativo de Mayhew:

1. **Baixa fidelidade (Entrega 6):** simulação em papel consolidou P01–P04 com navegação linear e atalhos.
2. **Média/alta fidelidade (Entregas 9–11):** protótipo digital com contraste WCAG, paleta para daltônicos e filtros refinados.
3. **Validação final (Entregas 12–14):** testes com usuários avaliam MU01–MU05; metas não atingidas geram revisão antes do fechamento.

---

#### Checklist

* [x] Impacto de IHC em capacidades e restrições explicitado.
* [x] Limite entre TCC técnico e camada interativa claro.
* [x] Processamento simulado explicitado.
* [x] Metas avaliam interação, não substituem métricas do TCC.
* [x] Normas contextualizadas, não copiadas.
* [x] Metas quantitativas mensuráveis e associadas a tarefas/público.
* [x] Eficácia, eficiência e satisfação consideradas.
* [x] Metas verificáveis nas Entregas 12–14.
