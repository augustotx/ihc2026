### Entrega 9 — Modelo conceitual e design centrado na comunicação

**Data:** 15/11/2026

**Status:** 🟩 concluida

**Responsabilidade:** João Pedro Bazoli Palma e Augusto Pereira Teixeira

#### Objetivo da atividade

Passar dos cenários de problema para a concepção da interação, definindo objetivos, diálogos e signos da interface.

#### Transformando resultados técnicos em conceitos compreensíveis

A interface traduz medições de baixo nível e receitas do Linux/Guix em conceitos familiares ao usuário:

* **Gestor (Rafael):** Tempo de execução (s), consumo de memória (MB), perfil de carga (CPU vs. Memória) e comparação visual direta.
* **Pesquisadora (Mariana):** Código-fonte, flags de compilação (-O3), manifesto GNU Guix, dataset bruto (CSV) e citação (BibTeX).

---

#### 1. Cenários de interação

##### CI01 — Comparação de desempenho para decisão técnica

**Autor(a):** João Pedro Bazoli Palma — 24.123.041-6

**Origem:** Cenário problema C01 (Rafael Mendes — Gestor)

Rafael precisa definir a linguagem para um microsserviço de pagamentos sem depender de opiniões subjetivas ou tabelas estáticas confusas.

**[SOLUÇÃO: Rafael acessa a plataforma e filtra os benchmarks pela categoria "CPU-bound". Ele seleciona o algoritmo desejado e, no painel comparativo, escolhe Go, Rust e Java. O sistema exibe o gráfico de barras comparando tempo e memória lado a lado. Rafael avalia o trade-off de desempenho em segundos e exporta o resumo do gráfico para a ata da reunião.]**

###### Diferenças relevantes

| Alteração | Por que foi necessária | Evidência/artefato que justifica |
|---|---|---|
| Filtro por tipo de carga e busca | Reduz o tempo de procura por testes relevantes. | C01 (Entrega 4) e MU02 (Entrega 8). |
| Gráfico comparativo de barras | Permite visualizar o trade-off (tempo vs. memória) de imediato. | P01 (Entrega 3) e MU01 (Entrega 8). |

---

##### CI02 — Auditoria metodológica e exportação de dados

**Autor(a):** Augusto Pereira Teixeira — 24.123.008-5

**Origem:** Cenário problema C02 (Mariana Costa — Pesquisadora)

Mariana precisa de dados rigorosos sobre o algoritmo N-Queens para um artigo, mas não confia em números da internet que omitem compiladores e hardware.

**[SOLUÇÃO: Mariana pesquisa "N-Queens" na busca e abre o benchmark. Na aba de reprodutibilidade, ela inspeciona o código-fonte, a versão do compilador, as flags (-O3) e o manifesto GNU Guix. Segura do rigor metodológico, ela clica em baixar o dataset em CSV e copia a citação pronta em BibTeX para seu artigo no Overleaf.]**

###### Diferenças relevantes

| Alteração | Por que foi necessária | Evidência/artefato que justifica |
|---|---|---|
| Exposição do manifesto GNU Guix e flags | Garante a reprodutibilidade científica do experimento. | C02 (Entrega 4) e MU03 (Entrega 8). |
| Exportação em CSV e cópia de BibTeX | Elimina a transcrição manual de dados e a formatação de referências. | T02 (Entrega 5) e MU04 (Entrega 8). |

---

#### 2. Design centrado na comunicação

##### CI01 — Rafael (Comparação)

| Tópico > subtópico | Falas e signos envolvidos | Intenção/efeito esperado |
|---|---|---|
| **Localizar teste** | **D:** "Filtre por categoria ou busque pelo nome." <br />**Signos:** `filtro_categoria`, `campo_busca`, `card_algoritmo`. | Encontrar o benchmark rapidamente. |
| **Comparar métricas** | **U:** "Compare Go, Rust e Java em tempo e memória." <br />**D:** "Aqui está o gráfico comparativo." <br />**Signos:** `seletor_linguagens`, `grafico_barras`. | Avaliar o trade-off visualmente. |

##### CI02 — Mariana (Auditoria e Coleta)

| Tópico > subtópico | Falas e signos envolvidos | Intenção/efeito esperado |
|---|---|---|
| **Auditar teste** | **U:** "Quero ver como foi compilado e executado." <br />**D:** "Aqui estão o código, as flags e a receita Guix." <br />**Signos:** `aba_guix`, `bloco_codigo`. | Verificar a reprodutibilidade. |
| **Extrair dados** | **U:** "Baixar CSV e copiar citação." <br />**D:** "Download iniciado e BibTeX copiado." <br />**Signos:** `botao_csv`, `botao_bibtex`, `toast_feedback`. | Coletar dados para o artigo. |

---

#### 3. Mapa de objetivos
![Mapa consolidado](../assets/09_modelo_conceitual/Mapa2.jpg)

##### Dicionário de objetivos

| ID | Objetivo | Persona | Cenário | Prioridade |
|---|---|---|---|---|
| **O01** | Escolher linguagem com base em trade-off de desempenho | P01 (Rafael) | CI01 | Alta |
| **O02** | Auditar rigor dos dados e embasar artigo acadêmico | P02 (Mariana) | CI02 | Alta |
| **O03** | Localizar benchmark no catálogo (filtro/busca) | P01 e P02 | CI01 e CI02 | Alta |
| **O04** | Parametrizar linguagens e métricas de teste | P01 | CI01 | Alta |
| **O05** | Analisar trade-off nos gráficos de barras | P01 | CI01 | Alta |
| **O06** | Inspecionar código, flags e manifesto GNU Guix | P02 | CI02 | Alta |
| **O07** | Baixar dataset tabular em CSV (opcional) | P02 | CI02 | Média |
| **O08** | Copiar citação em BibTeX (opcional) | P02 | CI02 | Média |

---

#### 4. Esquema conceitual de signos

| Grupo | Signo | Origem | Observações/semântica | Tipo | Restrição | Padrão | Prevenção | Recuperação |
|---|---|---|---|---|---|---|---|---|
| **Busca** | `filtro_categoria` | Usuário | Filtra por CPU-bound ou Memory-bound. | Seleção | Opções fixas | "Todas" | **PP:** Botões com rótulo claro. | Botão "Limpar". |
| **Busca** | `campo_busca` | Usuário | Busca textual por nome do algoritmo. | Texto | Máx. 50 char | Vazio | **PP:** Texto de exemplo. | Botão "X" para limpar. |
| **Dashboard** | `seletor_linguagens` | Usuário | Linguagens exibidas no gráfico. | Checkboxes | De 2 a 5 opções | Go, Rust, Java | **PA:** Trava ao atingir 5 escolhas. | Desmarcar item. |
| **Dashboard** | `grafico_barras` | Sistema | Gráfico comparativo de tempo e memória. | Gráfico | Valores positivos | — | **PP:** Rótulo com número sobre a barra. | Atualização direta. |
| **Auditoria** | `bloco_guix` | Sistema | Exibe receita Guix e flags (`-O3`). | Código | Somente leitura | — | **PP:** Realce de sintaxe. | — |
| **Exportação** | `botao_csv` | Usuário | Baixa o arquivo CSV com dados brutos. | Botão | Clique único | — | **PP:** Ícone e texto "Baixar CSV". | Reclicar. |
| **Exportação** | `botao_bibtex` | Usuário | Copia a referência formatada. | Botão | Clique único | — | **PP:** Mensagem "Copiado!". | Reclicar. |

> **Prevenção:** **PP** = Passiva (dicas, rótulos claros); **PA** = Ativa (bloqueio de ações inválidas).

---

#### Síntese

Para a Entrega 10, a interação será modelada em **dois diagramas MoLIC** (um por integrante):

1. **MoLIC 01 — Rafael (João Pedro):** busca no catálogo e comparação no dashboard (`O01`, `O03`, `O04`, `O05`), com os signos `filtro_categoria`, `campo_busca`, `seletor_linguagens` e `grafico_barras`.
2. **MoLIC 02 — Mariana (Augusto):** localização do teste, auditoria na aba de reprodutibilidade e exportação (`O02`, `O03`, `O06`, `O07`, `O08`), com os signos `campo_busca`, `bloco_guix`, `botao_csv`, `botao_bibtex` e `toast_feedback`.
---

#### Checklist

* [x] Cenários mostram alterações em relação aos de problema.
* [x] Identifica autor e cenário de origem.
* [x] Conversas e signos coerentes com os objetivos.
* [x] Mapa consolidado unificado.
* [x] Esquema de signos em tabela única, enxuta e sem duplicações.
* [x] Nomes de signos serão reaproveitados na Entrega 10.
* [x] Signos refletem o domínio do usuário, não o código interno.
