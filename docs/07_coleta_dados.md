### Entrega 7 — Coleta de dados, necessidades e aspectos éticos

**Data:** 06/11/2026

**Status:** 🟩 completa

**Responsabilidade:** João Pedro Bazoli Palma e Augusto Pereira Teixeira

#### Objetivo da atividade

Planejar os dados necessários para compreender usuários e requisitos de IHC, escolher técnicas adequadas e documentar instrumentos de modo que a aplicação possa ser reproduzida por pessoas diferentes.

#### Hipóteses e lacunas prioritárias herdadas da Entrega 1

| ID | Hipótese/lacuna | Evidência atual | Decisão que depende da resposta | Prioridade |
|---|---|---|---|---|
| **H01** | Gestores técnicos (P01) e desenvolvedores precisam de gráficos comparativos diretos (tempo de execução vs. uso de memória) para escolher a linguagem de um novo projeto de forma objetiva. | **[F]** Decisões hoje são tomadas por tendência de mercado ou preferência pessoal (Entrega 1). | Definir quais gráficos aparecem em destaque no Dashboard Comparativo (T01). | Alta |
| **H02** | Pesquisadores (P02) precisam ver os detalhes do ambiente (versão do compilador, flags `-O3`, hardware e scripts Guix) para confiar nos dados antes de usá-los em artigos. | **[H]** Ferramentas atuais não mostram compilador e ambiente com clareza (Entrega 2). | Incluir a tela de auditoria de reprodutibilidade e exibição do manifesto Guix. | Alta |
| **H03** | Filtrar por categoria de problema (ex: uso de CPU vs. uso de memória) é o caminho preferido de quem quer explorar opções sem ter um algoritmo específico em mente. | **[H]** Apenas a busca por nome exato não atende quem está explorando alternativas (Entrega 5). | Organizar os filtros por tipo de processamento na Página Inicial. | Média |
| **H04** | Oferecer opções para baixar dados em CSV e copiar citações em BibTeX/ABNT economiza tempo na escrita de trabalhos acadêmicos. | **[H]** Pesquisadores perdem tempo formatando dados e referências manualmente (Entrega 3). | Colocar botões de exportação de dados e cópia de citação na tela do benchmark. | Alta |

---

#### Parte A — necessidades e requisitos de IHC

##### A01 — João Pedro Bazoli Palma

**Autor(a):** João Pedro Bazoli Palma — 24.123.041-6

###### Que dados coletar?

| Dado/informação | Hipótese/lacuna relacionada | Por que é necessário | Qual decisão de design pode afetar |
|---|---|---|---|
| Informações e métricas mais importantes na escolha de uma linguagem para projetos reais | H01 | Entender se o tempo de execução e o uso de memória são suficientes para tomar uma decisão técnica. | Escolher quais gráficos e métricas devem aparecer primeiro na tela de comparação. |
| Preferência entre gráficos visuais e tabelas com números exatos | H01 | Descobrir a forma mais fácil e rápida de mostrar as diferenças de desempenho. | Definir se o layout da tela destaca gráficos de barras ou tabelas de dados. |
| Utilidade da busca por categorias de problema (ex: CPU vs. Memória) | H03 | Saber se a divisão por tipo de processamento ajuda na navegação. | Ajustar as opções de filtro na Página Inicial. |

###### De quem coletar?

| Perfil/stakeholder | Critério de inclusão | Relação com persona/público |
|---|---|---|
| Líderes técnicos, gestores de TI e desenvolvedores seniores | Profissionais que participam ativamente da escolha de linguagens e tecnologias em projetos de software. | Representantes diretos da persona **P01 (Rafael Mendes — Gestor Técnico)**. |

###### Aspectos éticos

* **Voluntariedade e Consentimento:** A participação será voluntária. Todos os convidados lerão e assinarão o Termo de Consentimento Livre e Esclarecido (TCLE), que explica os objetivos da pesquisa acadêmica.
* **Minimização de Dados e Privacidade:** Serão coletadas apenas informações profissionais gerais (tempo de experiência e área de atuação). Nenhum dado pessoal sensível ou nome de empresa será solicitado.
* **Anonimização e Descarte:** As respostas serão identificadas apenas por códigos (ex: G01, G02). Os dados serão salvos em pasta segura da equipe e apagados ao final da disciplina.

---

##### A02 — Augusto Pereira Teixeira

**Autor(a):** Augusto Pereira Teixeira — 24.123.008-5

###### Que dados coletar?

| Dado/informação | Hipótese/lacuna relacionada | Por que é necessário | Qual decisão de design pode afetar |
|---|---|---|---|
| Nível de detalhe exigido sobre o ambiente do teste (compilador, flags, hardware e script Guix) | H02 | Saber se mostrar os detalhes técnicos do teste aumenta a confiança nos dados apresentados. | Definir o conteúdo e a organização da tela de reprodutibilidade e código (P03). |
| Formatos mais usados para baixar dados e copiar referências acadêmicas | H04 | Entender como os pesquisadores transferem dados para programas de análise (R, Python) e editores de texto (LaTeX). | Definir quais botões de exportação criar (CSV, JSON, BibTeX ou ABNT). |
| Maiores dificuldades ao usar plataformas atuais de benchmark | H02 / H04 | Descobrir problemas em ferramentas existentes que nossa interface pode resolver. | Garantir uma navegação mais simples e acesso direto às informações importantes. |

###### De quem coletar?

| Perfil/stakeholder | Critério de inclusão | Relação com persona/público |
|---|---|---|
| Pesquisadores, professores e alunos de pós-graduação ou graduação em Ciência da Computação / Engenharia de Software | Pessoas com experiência em escrita de artigos científicos ou experimentos práticos em computação. | Representantes diretos da persona **P02 (Mariana Costa — Pesquisadora Acadêmica)**. |

###### Aspectos éticos

* **Voluntariedade e Consentimento:** Exposição clara do objetivo da pesquisa antes de começar, garantindo que o participante possa desistir a qualquer momento sem problemas.
* **Privacidade em Entrevistas:** Caso haja gravação de áudio, ela só será feita com autorização prévia por escrito no termo de consentimento.
* **Anonimização e Descarte:** Os participantes serão identificados nos relatórios apenas por códigos (ex: P01, P02). Áudios e anotações serão mantidos em pasta restrita da equipe e excluídos após o encerramento do semestre.

## Parte B — ferramentas de coleta

Cada integrante preparou um instrumento de coleta completo e distinto. O **Questionário** foi definido para a abordagem quantitativa/qualitativa de larga escala (P01), e a **Entrevista Semiestruturada** para o aprofundamento qualitativo (P02).

---

### Instrumento I01 — Questionário sobre escolha técnica de linguagens

**Autor(a):** João Pedro Bazoli Palma — 24.123.041-6

**Técnica:** Questionário online

**Objetivo:** Identificar métricas prioritárias, preferência entre gráficos e tabelas, e utilidade dos filtros por categoria.

**Público:** Líderes técnicos, gestores de TI e desenvolvedores seniores (P01).

### Procedimento padronizado de aplicação

1. **Preparação:** Criação de formulário digital rápido em plataforma online (ex: Google Forms).
2. **Apresentação e Consentimento:** Exibição do TCLE na tela inicial, condicionando a resposta ao aceite.
3. **Aplicação:** Divulgação do link em redes profissionais (LinkedIn) e comunidades técnicas por 10 dias.
4. **Encerramento:** Mensagem automática de agradecimento ao enviar a resposta.
5. **Armazenamento e Anonimização:** Exportação das respostas para planilha restrita e anonimizada (`G01`, `G02`).

### Instrumento

**Bloco 1 — Perfil Profissional**

1. Há quanto tempo você atua na área de desenvolvimento de software ou gestão de tecnologia?
   - [ ] Menos de 2 anos
   - [ ] De 2 a 5 anos
   - [ ] De 5 a 10 anos
   - [ ] Mais de 10 anos
2. Qual é o seu papel principal no trabalho atual?
   - [ ] Gestor de TI / Líder Técnico / Arquiteto de Software
   - [ ] Desenvolvedor Senior / Pleno
   - [ ] Outro: ___________

**Bloco 2 — Escolha de Linguagens e Métricas**

3. Como é feita hoje a escolha da linguagem de programação para um novo projeto na sua equipe?
   - [ ] Preferência da equipe ou familiaridade dos desenvolvedores
   - [ ] Tendência de mercado e padrão da empresa
   - [ ] Testes práticos e benchmarks de desempenho
   - [ ] Outro: ___________
4. Ao comparar o desempenho de duas linguagens, qual métrica é mais importante para a sua tomada de decisão?
   - [ ] Tempo de execução (velocidade)
   - [ ] Consumo de memória RAM
   - [ ] Tempo de compilação
   - [ ] Ambas (tempo de execução e memória têm o mesmo peso)
   - [ ] Outra: ___________

**Bloco 3 — Interface e Filtros**

5. Como você prefere visualizar os dados de desempenho para decidir rapidamente entre duas linguagens?
   - [ ] Gráficos visuais (ex: barras lado a lado)
   - [ ] Tabelas com valores exatos
   - [ ] Ambas as opções na mesma tela
6. Quando você não sabe o nome exato do algoritmo, como prefere buscar o benchmark?
   - [ ] Digitando no campo de busca rápida
   - [ ] Navegando por categorias de problema (ex: CPU vs. Memória)
   - [ ] Filtrando direto pelas linguagens que quer comparar
7. O que falta nas ferramentas atuais de benchmark para ajudar na sua decisão técnica? *(Resposta livre)*

### Como os dados serão analisados

* **Quantitativa (Perguntas 1 a 6):** Distribuição de frequências e porcentagens apresentadas em gráficos.
* **Qualitativa (Pergunta 7):** Agrupamento temático das sugestões enviadas.

---

### Instrumento I02 — Entrevista Semiestruturada (Reprodutibilidade e Exportação)

**Autor(a):** Augusto Pereira Teixeira — 24.123.008-5

**Técnica:** Entrevista semiestruturada

**Objetivo:** Avaliar o impacto da transparência do ambiente (compiladores, hardware e scripts Guix) e a utilidade da exportação de dados e citações.

**Público:** Pesquisadores, professores e pós-graduandos em computação (P02).

### Procedimento padronizado de aplicação

1. **Preparação:** Agendamento prévio de sessão de 15 minutos (presencial ou online) e teste de gravação.
2. **Apresentação e Consentimento:** Leitura dos objetivos e assinatura/aceite do TCLE com autorização de gravação.
3. **Aplicação:** Condução de entrevista guiada por roteiro flexível.
4. **Encerramento:** Agradecimento pelo tempo e abertura para considerações finais do participante.
5. **Armazenamento e Anonimização:** Transcrição do áudio, descarte da gravação e anonimização dos relatórios (`P01`, `P02`).

### Instrumento (Roteiro)

1. Com que frequência você consulta ou cita dados de benchmark em seus trabalhos acadêmicos?
2. O que faz você confiar ou duvidar dos dados de desempenho que encontra na internet?
3. Qual é a importância de visualizar o compilador exato, as flags (`-O3`) e o hardware usado nos testes?
4. Como a presença de um script de reprodutibilidade em GNU Guix afetaria a sua percepção de qualidade do teste?
5. Como você costuma extrair os dados para usar no seu artigo (download CSV, cópia manual)?
6. Ter um botão para copiar a citação direta em BibTeX/ABNT ajudaria no seu fluxo de escrita?
7. Qual é a principal falha das ferramentas atuais de benchmark sob o ponto de vista acadêmico?

### Como os dados serão analisados

* **Análise de Conteúdo:** Categorização das respostas transcritas em três eixos: *Fatores de Confiança*, *Gargalos de Reprodutibilidade* e *Integração com a Escrita Acadêmica*.

## Síntese

As técnicas (Questionário I01 para gestores e Entrevista I02 para pesquisadores) buscam entender como esses perfis decidem e usam dados de desempenho. Após a coleta, os resultados validarão as hipóteses da Entrega 1:

* **H01 (Gráficos comparativos):** sustentada se tempo e memória forem determinantes na decisão gerencial; refinada se outras métricas forem exigidas.
* **H02 (Transparência do ambiente e Guix):** sustentada se expor compiladores, flags e receitas Guix for essencial para a confiança dos pesquisadores.
* **H03 (Busca por categorias):** refinada para definir a melhor estrutura de filtros na Página Inicial.
* **H04 (Exportação CSV e BibTeX):** sustentada se eliminar o trabalho manual na produção de artigos.

Os achados serão consolidados no arquivo \`RASTREABILIDADE.md\` ao término da aplicação.

## Checklist

- [x] Hipóteses/lacunas prioritárias da Entrega 1 foram revisitadas.
- [x] Se o escopo de IHC foi derivado de TCC técnico, a coleta investiga a plausibilidade do usuário, tarefa e contexto adotados.
- [x] Perguntas não pressupõem que dashboard, CRUD, filtros ou relatórios sejam necessários; investigam a necessidade.
- [x] Cada dado a coletar responde uma dúvida concreta do projeto ou justifica outra necessidade de informação.
- [x] Parte A identifica dados e perfis de coleta de forma específica.
- [x] Aspectos éticos são contextualizados para o projeto.
- [x] Há uma técnica completa por integrante e técnicas distintas.
- [x] Questionário está incluído entre as técnicas.
- [x] Cada instrumento possui objetivo, público, procedimento e conteúdo integral.
- [x] Perguntas evitam indução e coletam apenas dados necessários.
- [x] Está claro como os dados serão analisados e usados no design.
