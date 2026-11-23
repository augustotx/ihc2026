# Entrega 7 — Coleta de dados, necessidades e aspectos éticos

**Data:** 06/11/2026 (Revisado em 22/11/2026)

**Status:** 🟩 completa

**Responsabilidade:** João Pedro Bazoli Palma e Augusto Pereira Teixeira

## Objetivo da atividade

Planejar os dados necessários para compreender usuários e requisitos de IHC, escolher técnicas adequadas e documentar instrumentos de modo que a aplicação possa ser reproduzida por pessoas diferentes.

## Hipóteses e lacunas prioritárias herdadas da Entrega 1

| ID | Hipótese/lacuna | Evidência atual | Decisão que depende da resposta | Prioridade |
| ------ | ------ | ------ | ------ | ------ |
| **H01** | Gestores técnicos (P01) e desenvolvedores precisam de gráficos comparativos diretos (tempo de execução vs. uso de memória) para escolher a linguagem de um novo projeto de forma objetiva. | **[H]** Hipótese de que decisões muitas vezes se apoiam em tendências de mercado ou familiaridade por falta de comparativos diretos (Entrega 1). | Definir quais gráficos aparecem em destaque no Dashboard Comparativo (T01). | Alta |
| **H02** | Pesquisadores (P02) precisam ver os detalhes do ambiente (versão do compilador, flags -O3, hardware e scripts Guix) para confiar nos dados antes de usá-los em artigos. | **[H]** Ferramentas atuais não mostram compilador e ambiente com clareza (Entrega 2). | Incluir a tela de auditoria de reprodutibilidade e exibição do manifesto Guix. | Alta |
| **H03** | Filtrar por categoria de problema (ex: uso de CPU vs. uso de memória) é o caminho preferido de quem quer explorar opções sem ter um algoritmo específico em mente. | **[H]** Apenas a busca por nome exato não atende quem está explorando alternativas (Entrega 5). | Organizar os filtros por tipo de processamento na Página Inicial. | Média |
| **H04** | Oferecer opções para baixar dados em CSV e copiar citações em BibTeX/ABNT economiza tempo na escrita de trabalhos acadêmicos. | **[H]** Suposição de que pesquisadores despendem esforço considerável formatando dados e referências manualmente (Entrega 3). | Colocar botões de exportação de dados e cópia de citação na tela do benchmark. | Alta |

---

## Parte A — necessidades e requisitos de IHC

### A01 — João Pedro Bazoli Palma

**Autor(a):** João Pedro Bazoli Palma — 24.123.041-6

#### Que dados coletar?

| Dado/informação | Hipótese/lacuna relacionada | Por que é necessário | Qual decisão de design pode afetar |
| ------ | ------ | ------ | ------ |
| Informações e métricas mais importantes na escolha de uma linguagem para projetos reais | H01 | Entender se o tempo de execução e o uso de memória são suficientes para tomar uma decisão técnica ou se há outras variáveis de ecossistema. | Escolher quais gráficos e métricas devem aparecer primeiro na tela de comparação. |
| Preferência entre gráficos visuais e tabelas com números exatos | H01 | Descobrir a forma mais fácil e rápida de mostrar as diferenças de desempenho. | Definir se o layout da tela destaca gráficos de dispersão ou tabelas de dados. |
| Utilidade da busca por categorias de problema (ex: CPU vs. Memória) | H03 | Saber se a divisão por tipo de processamento ajuda na navegação. | Ajustar as opções de filtro na Página Inicial. |

#### De quem coletar?

| Perfil/stakeholder | Critério de inclusão e amostragem | Relação com persona/público |
| ------ | ------ | ------ |
| Líderes técnicos, gestores de TI, arquitetos e desenvolvedores | Profissionais que participam ativamente da escolha de linguagens e tecnologias em projetos de software.<br />**Meta amostral:** 15 a 25 respostas em 10 dias (mínimo de 10 válidas do perfil-alvo). Participantes sem envolvimento em decisões técnicas são descartados na triagem. | Representantes diretos da persona **P01 (Rafael Mendes — Gestor Técnico)**. |

#### Aspectos éticos

* **Voluntariedade e Consentimento:** A participação é voluntária. O formulário online apresenta na tela inicial o Termo de Consentimento Livre e Esclarecido (TCLE), condicionando o início das respostas ao aceite explícito.
* **Minimização de Dados e Privacidade:** Serão coletadas apenas informações profissionais gerais (papel e tempo de experiência). Nenhum dado pessoal identificável, e-mail de login ou nome de empresa será solicitado (LGPD).
* **Riscos e Recusa Parcial:** Riscos mínimos associados ao tempo de resposta (3 a 5 minutos). O participante pode interromper o preenchimento ou recusar-se a responder perguntas opcionais.
* **Anonimização e Descarte:** As respostas serão identificadas nos relatórios por códigos anônimos (**Q01, Q02...**). Os dados brutos serão mantidos em pasta segura da equipe e excluídos ao final da disciplina.
* **Contatos institucionais:** augusto.teixeira03@proton.me e jpbazolip@gmail.com

---

### A02 — Augusto Pereira Teixeira

**Autor(a):** Augusto Pereira Teixeira — 24.123.008-5

#### Que dados coletar?

| Dado/informação | Hipótese/lacuna relacionada | Por que é necessário | Qual decisão de design pode afetar |
| ------ | ------ | ------ | ------ |
| Nível de detalhe exigido sobre o ambiente do teste (compilador, flags, hardware e script Guix) | H02 | Saber se mostrar os detalhes técnicos do teste aumenta a confiança nos dados apresentados. | Definir o conteúdo e a organização da tela de reprodutibilidade e código (P03). |
| Formatos mais usados para baixar dados e copiar referências acadêmicas | H04 | Entender como os pesquisadores transferem dados para programas de análise (R, Python) e editores de texto (LaTeX). | Definir quais botões de exportação criar (CSV, JSON, BibTeX ou ABNT). |
| Maiores dificuldades ao usar plataformas atuais de benchmark | H02 / H04 | Descobrir problemas em ferramentas existentes que nossa interface pode resolver. | Garantir uma navegação mais simples e acesso direto às informações importantes. |

#### De quem coletar?

| Perfil/stakeholder | Critério de inclusão e amostragem | Relação com persona/público |
| ------ | ------ | ------ |
| Pesquisadores, professores e alunos de pós-graduação ou graduação em Ciência da Computação / Engenharia de Software | Pessoas com experiência em escrita de artigos científicos ou experimentos práticos em computação.<br />**Meta amostral:** 3 a 5 participantes entrevistados individualmente. | Representantes diretos da persona **P02 (Mariana Costa — Pesquisadora Acadêmica)**. |

#### Aspectos éticos

* **Voluntariedade e Consentimento:** Exposição clara do objetivo da pesquisa antes de começar, garantindo que o participante possa desistir a qualquer momento sem penalidades.
* **Privacidade em Entrevistas:** A gravação de áudio só será realizada com autorização prévia por escrito no termo de consentimento. Caso recusada, a entrevista é registrada exclusivamente por anotações.
* **Riscos e Liberdade de Interrupção:** Riscos mínimos (tempo despendido de 15 a 20 minutos). O participante pode pular perguntas ou solicitar encerramento a qualquer momento.
* **Anonimização e Descarte:** Os participantes serão identificados nos relatórios apenas por códigos (**E01, E02, E03...**), sem conflitar com os IDs das personas. Áudios e anotações serão mantidos em pasta restrita da equipe e excluídos após o encerramento do semestre.
* **Contatos institucionais:** augusto.teixeira03@proton.me e jpbazolip@gmail.com

## Parte B — ferramentas de coleta

Cada integrante preparou um instrumento de coleta completo e distinto. O **Questionário** foi definido para a abordagem quantitativa/qualitativa de larga escala (P01), e a **Entrevista Semiestruturada** para o aprofundamento qualitativo (P02).

---

### Instrumento I01 — Questionário sobre escolha técnica de linguagens

**Autor(a):** João Pedro Bazoli Palma — 24.123.041-6

**Técnica:** Questionário online

**Objetivo:** Identificar métricas prioritárias, preferência entre gráficos e tabelas, e utilidade dos filtros por categoria.

**Público:** Líderes técnicos, gestores de TI, arquitetos e desenvolvedores (P01).

**Link de Acesso ao Formulário Online:** [https://forms.gle/2HkcwNeukKMDtPb2A](https://forms.gle/2HkcwNeukKMDtPb2A) *(formulário ativo, público e pronto para resposta)*.

#### Procedimento padronizado de aplicação

1. **Preparação e Teste Piloto:** Formulário construído no Google Forms, configurado para acesso público sem necessidade de login e submetido a teste piloto prévio para validação do tempo de preenchimento (< 5 min) e clareza textual.
2. **Apresentação e Consentimento:** A Seção 1 apresenta o TCLE com os objetivos acadêmicos da pesquisa, garantia de sigilo e pergunta obrigatória de consentimento ("Concorda em participar voluntariamente?"). A seleção de "Não" redireciona diretamente ao encerramento sem coletar respostas.
3. **Aplicação:** Divulgação do link via redes profissionais (LinkedIn) e comunidades técnicas por 10 dias.
4. **Encerramento e Triagem:** Mensagem automática de agradecimento ao enviar a resposta. Respostas de respondentes sem envolvimento em decisões técnicas são filtradas e descartadas da análise principal.
5. **Armazenamento e Anonimização:** Exportação das respostas para planilha restrita e anonimização com códigos (**Q01, Q02...**).

#### Estrutura das Seções do Formulário Online

O formulário online acessível pelo link acima está estruturado nas seguintes seções:

* **Seção 1 — Apresentação e TCLE:** Exposição dos objetivos, termos de privacidade, voluntariedade e pergunta mandatória de consentimento.
* **Seção 2 — Perfil Profissional e Triagem:** Tempo de atuação, papel principal (Gestor, Líder, Arquiteto ou Desenvolvedor) e confirmação de participação na escolha de tecnologias.
* **Seção 3 — Critérios de Escolha e Métricas:** Fatores considerados na escolha de linguagens, métricas prioritárias de desempenho e informações indispensáveis para confiar no benchmark.
* **Seção 4 — Visualização e Exploração:** Preferência entre representação visual e dados tabulares, forma de busca quando não há algoritmo em mente e pergunta aberta sobre carências das ferramentas atuais.

#### Como os dados serão analisados

* **Quantitativa:** Distribuição de frequências e porcentagens apresentadas em gráficos, permitindo comparação entre os diferentes papéis profissionais.
* **Qualitativa:** Agrupamento temático das respostas abertas enviadas na questão final.

---

### Instrumento I02 — Entrevista Semiestruturada (Reprodutibilidade e Exportação)

**Autor(a):** Augusto Pereira Teixeira — 24.123.008-5

**Técnica:** Entrevista semiestruturada

**Objetivo:** Investigar em profundidade como pesquisadores avaliam a reprodutibilidade de experimentos, a transparência do ambiente (compiladores, hardware e scripts) e o fluxo de trabalho com dados e citações.

**Público:** Pesquisadores, professores e pós-graduandos em computação (P02).

**Amostra planejada:** 3 a 5 participantes.

#### Procedimento padronizado de aplicação

1. **Preparação e Piloto:** Agendamento prévio de sessão de 15 a 20 minutos (presencial ou online via Google Meet) e execução de 1 entrevista-piloto para calibrar tempo e fluidez do roteiro.
2. **Papéis na Condução:** Augusto atua como moderador principal da conversa; João Pedro atua como observador e anotador de pontos-chave.
3. **Apresentação e Consentimento:** Leitura dos objetivos e assinatura/aceite do TCLE com autorização opcional de gravação em áudio.
4. **Aplicação:** Condução da entrevista investigando primeiramente as práticas e rotinas atuais do pesquisador, aprofundando posteriormente em requisitos de reprodutibilidade e ferramentas.
5. **Encerramento e Tratamento:** Agradecimento, transcrição das notas/áudio, descarte da gravação original e anonimização com códigos (**E01, E02, E03...**).

#### Instrumento (Roteiro)

1. Como costuma ser sua rotina quando você precisa obter dados de benchmark para fundamentar uma pesquisa ou publicação?
2. O que faz você confiar ou duvidar de dados de desempenho que encontra publicados na internet ou em artigos?
3. Quais detalhes sobre as condições experimentais (compilador, flags de otimização, arquitetura de hardware) você considera indispensáveis para aceitar um resultado?
4. Quais são as maiores barreiras que você já enfrentou ao tentar reproduzir experimentos computacionais de outros autores?
5. Que ferramentas ou abordagens você costuma utilizar para garantir a reprodutibilidade dos seus próprios testes (ex: scripts, contêineres, receitas declarativas, documentação manual)?
6. Como é o seu processo atual para extrair dados brutos e gerar referências/citações nos seus artigos? Onde ocorrem dificuldades?
7. De modo geral, o que tornaria uma plataforma de benchmarks verdadeiramente confiável e útil sob a perspectiva acadêmica?

#### Como os dados serão analisados

* **Análise de Conteúdo:** Categorização temática das respostas transcritas em três eixos: *Fatores de Confiança e Auditabilidade*, *Gargalos de Reprodutibilidade Experimental* e *Rotinas de Extração e Referenciação*.

## Síntese

As técnicas (Questionário I01 para gestores/líderes e Entrevista I02 para pesquisadores) buscam compreender práticas reais e verificar a plausibilidade das hipóteses da Entrega 1:

* **H01 (Gráficos comparativos):** sustentada se tempo e memória forem determinantes na decisão; refinada se outros fatores de arquitetura e equipe forem predominantes.
* **H02 (Transparência do ambiente e Guix):** sustentada se detalhes de compilador e automação forem vitais para a confiança; refinada se a comunidade exigir níveis diferentes de documentação.
* **H03 (Busca por categorias):** refinada para definir se a organização inicial deve priorizar gargalo de processamento, domínio ou busca direta.
* **H04 (Exportação CSV e BibTeX):** sustentada se eliminar esforço manual de transcrição; refutada se os pesquisadores preferirem compilar seus próprios dados brutos.

Os achados consolidados serão integrados ao arquivo `RASTREABILIDADE.md`.

## Checklist

* [x] Hipóteses/lacunas prioritárias da Entrega 1 foram revisitadas como hipóteses a testar.
* [x] Se o escopo de IHC foi derivado de TCC técnico, a coleta investiga a plausibilidade do usuário, tarefa e contexto adotados.
* [x] Perguntas investigam práticas e necessidades reais sem pressupor soluções prontas.
* [x] Cada dado a coletar responde uma dúvida concreta do projeto ou justifica outra necessidade de informação.
* [x] Parte A identifica dados, perfis de coleta e metas amostrais de forma específica.
* [x] Aspectos éticos são contextualizados para o projeto, incluindo riscos mínimos e recusa parcial.
* [x] Há uma técnica completa por integrante e técnicas distintas (Questionário e Entrevista).
* [x] Questionário online construído e disponibilizado por link funcional e testável.
* [x] Cada instrumento possui objetivo, público, procedimento e conteúdo integral reproduzível.
* [x] Perguntas evitam indução e foram formuladas de forma neutra.
* [x] Está claro como os dados serão analisados para sustentar, refinar ou refutar hipóteses.
