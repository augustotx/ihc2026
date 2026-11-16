### Roteiro de teste de usabilidade — BMML

#### 1. Antes da sessão

* Verificar se o protótipo com as telas (Catálogo, MergeSort, Código, About) está aberto e carregando normalmente.
* Preparar a planilha de observação aberta e o cronômetro zerado.
* Testar compartilhamento de tela e áudio (se for remoto via Google Meet).
* Ter a folha de tarefas neutras em mãos.

#### 2. Abertura padronizada

* *"Olá! Muito obrigado pela sua disponibilidade em nos ajudar hoje."*
* *"O objetivo desta sessão é testar a interface de uma ferramenta visual de benchmarks de linguagens de programação."*
* *"Gostaria de reforçar que estamos testando a interface, e não você. Não existem respostas certas ou erradas. Se algo parecer confuso ou difícil de achar, a falha é do design da ferramenta, nunca sua."*
* *"Pedimos que, na medida do possível, você tente 'pensar em voz alta' (think-aloud), nos dizendo o que está procurando ou achando confuso enquanto executa as tarefas."*
* *"Você é livre para interromper o teste a qualquer momento. Podemos começar?"*

#### 3. Perfil pré-teste (rápido - 1 minuto)

1. Qual seu curso e semestre / profissão atual?
2. Você já teve contato com linguagens de programação (C, Rust, Python, Zig, etc.)? ( ) Sim ( ) Não
3. Com que frequência você costuma ler gráficos cartesianos de dispersão ou tabelas de desempenho? ( ) Diariamente ( ) Ocasionalmente ( ) Raramente

#### 4. Tarefas neutras aplicadas

| ID | Instrução ao participante | O moderador pode esclarecer | O moderador não deve dizer |
| :--- | :--- | :--- | :--- |
| **UT01** | *"Acesse o benchmark 'MergeSort' e descubra qual linguagem teve o menor tempo médio de execução."* | Pode repetir o nome do benchmark caso o participante esqueça. | Não dizer para olhar a tabela de médias nem onde clicar. |
| **UT02** | *"No gráfico do MergeSort, deixe visíveis apenas as linguagens C e Rust e ative a escala logarítmica no eixo Y."* | Pode reforçar que o objetivo é ocultar as outras linguagens do gráfico. | Não apontar onde ficam os checkboxes nem onde fica o switch 'Log Y'. |
| **UT03** | *"Descubra qual é o modelo do processador (CPU) e o total de memória RAM da máquina em que os testes rodaram."* | Pode esclarecer que a informação é do ambiente físico de teste. | Não dizer para clicar no botão 'About' no topo. |
| **UT04** | *"Copie o comando necessário para reproduzir este ambiente de benchmark na sua máquina via terminal."* | Pode esclarecer que é a receita do GNU Guix / script de reprodução. | Não dizer para ir na aba 'Code' nem apontar o botão 'Copy'. |

#### 5. Durante a tarefa

* O moderador apenas observa e anota início, fim, erros e hesitações na planilha.
* Intervir apenas se o participante travar completamente por mais de 1 minuto em um beco sem saída.

#### 6. Pós-tarefa e Encerramento

* Aplicar a pergunta de facilidade imediata (1 a 5) ao término de cada tarefa.
* Aplicar o Questionário Pós-Teste breve.
* Agradecer a participação e encerrar a chamada/sessão.
