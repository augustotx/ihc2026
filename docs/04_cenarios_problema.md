# Entrega 4 — Cenários de análise/problema

**Data:** 18/10/2026  
**Status:** completo 🟩   
**Responsabilidade:** 1 solução completa por integrante

## Objetivo da atividade

Descrever situações atuais em que o usuário tenta alcançar um objetivo e encontra dificuldades. O cenário de análise/problema deve tornar visível **o contexto, os atores, as ações e as rupturas**, sem antecipar a interface que será projetada.

> **Regra central:** cenário de problema é a “história do problema”. Se o texto já diz “o sistema mostra”, “o aplicativo resolve” ou descreve botões/telas futuras, provavelmente está misturando problema com solução.

Sempre que possível, o cenário deve aprofundar uma **situação concreta já registrada na Entrega 1**.

### Quando o TCC não possuía interface

O cenário continua sendo uma história de **problema/atividade humana**, não uma história do futuro sistema. Descreva como o profissional realiza hoje uma atividade semelhante ou como lida atualmente com dados, resultados, configurações, logs, decisões e limitações que o tema do TCC pretende apoiar.

Exemplo: em vez de “o DBA abre o novo dashboard e executa o algoritmo”, descreva “o DBA precisa investigar uma consulta lenta, reúne informações em ferramentas distintas, compara planos manualmente e tem dificuldade para estimar o impacto de uma mudança”.

A interface da disciplina aparecerá somente depois, nos cenários de interação.

Se o integrante escolher um novo problema/situação, explique por que ele passou a ser relevante e indique a evidência que motivou sua inclusão.

## Cenário C01 — Seleção e justificativa de linguagem de programação para um novo projeto

**Autor(a):** João Pedro Bazoli Palma — 24.123.041-6  
**Persona(s) relacionada(s):** P01 — Rafael Mendes  
**Necessidade relacionada:** N01 — Fundamentar a escolha da linguagem de programação com base em dados objetivos e comparáveis de desempenho  
**Situação concreta da Entrega 1 relacionada:** Seção 4.5 — Escolha de linguagem para um projeto específico  
**Hipóteses ainda presentes:** H01 — O uso de uma base objetiva de dados de desempenho auxilia na escolha de linguagens

## 1. Cenário inicial

Rafael Mendes é gestor de projetos e precisa definir a linguagem de programação ideal para um novo serviço de alto desempenho. Para evitar decisões baseadas em preferências pessoais ou modismos, ele pesquisa testes de desempenho na internet. Porém, encontra apenas dados dispersos, contraditórios e sem informações sobre o computador ou as versões utilizadas. Sem uma fonte padronizada, Rafael tenta organizar os dados em uma planilha manual, mas fica inseguro para defender a escolha técnica perante a equipe de desenvolvimento, que pressiona pelo uso de suas linguagens favoritas.

### 2. Questões de refinamento

| # | Questão | Por que precisa ser respondida | Fonte/forma de obter resposta |
| :--- | :--- | :--- | :--- |
| **Q1** | Quais métricas de desempenho são prioritárias para o projeto? | Identificar quais métricas devem ser comparadas. | Requisitos do projeto e conversa com o arquiteto de software. |
| **Q2** | Como Rafael verifica se os testes encontrados na web foram realizados em condições equivalentes? | Identificar como ele avalia a confiabilidade dos dados. | Entrevista com a persona (P01 — Rafael). |
| **Q3** | Quais questionamentos e preferências a equipe apresenta sobre a escolha da linguagem? | Compreender os conflitos e as pressões enfrentados pelo gestor. | Observação de reuniões com a equipe técnica. |
| **Q4** | Quanto tempo Rafael tem para pesquisar e definir a linguagem do projeto? | Avaliar o impacto da pesquisa no cronograma. | Cronograma do projeto e conversa com a diretoria. |

### 3. Cenário refinado

Rafael Mendes é gestor de projetos e precisa escolher a linguagem de programação ideal para um novo sistema. Com apenas dois dias antes da reunião com a diretoria, ele precisa focar na velocidade de execução e no consumo de memória. Para evitar decisões baseadas em gosto pessoal, ele pesquisa testes na internet. Porém, só encontra dados dispersos e contraditórios. Ele tenta procurar detalhes sobre os computadores usados nos testes, mas quase nunca encontra essas informações. Sem uma fonte confiável, Rafael tenta organizar tudo em uma planilha manual, mas fica inseguro. A equipe de programação duvida dos testes disponíveis na internet e pressiona para usar as linguagens com as quais tem mais familiaridade.

### 4. Elementos extraídos


| Elemento | Evidência no cenário |
| :--- | :--- |
| **Ator(es)** | Rafael Mendes (Gestor de Projetos). |
| **Objetivo(s)** | Escolher a linguagem de programação ideal para um novo sistema com base em velocidade e uso de memória. |
| **Contexto** | Empresa de software, com prazo apertado de 2 dias antes da reunião com a diretoria. |
| **Recursos/informações** | Artigos técnicos na internet, buscas web e planilha manual para organizar os dados. |
| **Ações** | Pesquisar testes na internet, tentar identificar o computador usado nos testes e montar uma planilha comparativa. |
| **Problemas/rupturas** | Dados dispersos e contraditórios na web; falta de detalhes sobre os testes; resistência e dúvida da equipe de programação. |
| **Consequências** | Perda de tempo, insegurança do gestor e dificuldade para justificar a escolha técnica para a equipe. |

### 5. Implicações para as próximas entregas

Este cenário mostra a necessidade de analisar como o gestor pesquisa e compara dados de desempenho no dia a dia. Nas próximas etapas, será preciso mapear quais informações sobre os testes (como tipo de computador, uso de memória e velocidade) são essenciais para gerar confiança e ajudar o gestor a justificar sua decisão para a equipe, sem ainda desenhar telas ou antecipar soluções.


## Cenário C02 — Comparação de linguagens para trabalho acadêmico

**Autor(a):** Augusto Pereira Teixeira — 24.123.008-5  
**Persona(s) relacionada(s):** P02 — Mariana Costa  
**Necessidade relacionada:** N02 — Acessar dados confiáveis e detalhados para embasar trabalhos e pesquisas  
**Situação concreta da Entrega 1 relacionada:** Seção 4.5 — Comparação de desempenho de linguagens para estudos  
**Hipóteses ainda presentes:** H01 — O uso de uma base objetiva de dados auxilia estudantes e pesquisadores

### 1. Cenário inicial

Mariana Costa é estudante de mestrado e precisa comparar a velocidade de diferentes linguagens de programação para um artigo. Ela pesquisa testes na internet, mas só encontra dados espalhados, pouco confiáveis e sem informações sobre qual computador foi usado. Sem fontes seguras, Mariana precisa baixar os códigos e rodar os testes manualmente no próprio computador, o que toma muito tempo e limita seus resultados.

### 2. Questões de refinamento

| # | Questão | Por que precisa ser respondida | Fonte/forma de obter resposta |
| :--- | :--- | :--- | :--- |
| **Q1** | Quais detalhes sobre o computador e os testes Mariana precisa para confiar nos dados? | Saber quais informações são essenciais para um trabalho acadêmico. | Conversa com o orientador da pesquisa. |
| **Q2** | Como Mariana tenta juntar e organizar os resultados de fontes diferentes hoje? | Mapear o esforço e a perda de tempo na organização manual dos dados. | Entrevista com a persona (P02 — Mariana). |
| **Q3** | Por que testar tudo no próprio computador atrapalha a pesquisa? | Entender a limitação de rodar testes em apenas um notebook. | Observação do dia a dia no laboratório. |
| **Q4** | Qual é o prazo final que Mariana tem para entregar o artigo? | Avaliar a urgência de obter esses dados rapidamente. | Cronograma do curso de pós-graduação. |

### 3. Cenário refinado

Mariana Costa é estudante de mestrado e precisa comparar a velocidade de diferentes linguagens para um artigo. Com o prazo de entrega do trabalho se aproximando, ela precisa urgentemente de dados confiáveis de tempo e memória. Ela pesquisa testes na internet, mas só encontra informações incompletas. Para seu artigo, é essencial saber qual computador e quais programas foram usados, mas os sites não mostram isso. Sem como confirmar os dados da web, Mariana tenta rodar tudo manualmente no próprio notebook. O processo leva horas e os resultados ficam limitados à capacidade da sua máquina pessoal.

### 4. Elementos extraídos

| Elemento | Evidência no cenário |
| :--- | :--- |
| **Ator(es)** | Mariana Costa (Estudante e Pesquisadora). |
| **Objetivo(s)** | Encontrar dados organizados e confiáveis sobre linguagens de programação para seu artigo. |
| **Contexto** | Pesquisa acadêmica na universidade, com prazo apertado para entregar o artigo. |
| **Recursos/informações** | Artigos na internet, notebook pessoal e códigos de teste. |
| **Ações** | Pesquisar na web, tentar descobrir como os testes foram feitos e rodar os programas manualmente. |
| **Problemas/rupturas** | Falta de detalhes nos testes da internet e perda de tempo testando tudo no próprio computador. |
| **Consequências** | Cansaço, atraso no trabalho e pesquisa limitada ao seu próprio notebook. |


### 5. Implicações para as próximas entregas

Este cenário evidencia a necessidade de entender detalhadamente quais dados metodológicos (como processador, sistema operacional e versão do compilador) são indispensáveis para dar validade acadêmica a uma pesquisa. Nas próximas entregas, deveremos mapear como essas informações devem ser organizadas para evitar que o pesquisador perca tempo com testes manuais, sem antecipar a interface do projeto.

## Checklist

- [x] Há um cenário completo por integrante.
- [x] Cada cenário tem título, ator, objetivo, contexto e problema.
- [x] O cenário possui origem rastreável na Entrega 1 ou justifica claramente a inclusão de uma nova situação.
- [x] O texto descreve a situação atual, sem antecipar a solução.
- [x] Para TCC sem interface original, o cenário descreve uma prática humana plausível relacionada à contribuição técnica, e não “a falta de uma tela”.
- [x] Questões de refinamento acrescentam informação nova.
- [x] O refinamento mostra claramente o que foi adicionado/alterado.
- [x] Cenários são diferentes o suficiente para cobrir objetivos/problemas relevantes.
- [x] Cada cenário está ligado a persona/necessidade na matriz de rastreabilidade.
