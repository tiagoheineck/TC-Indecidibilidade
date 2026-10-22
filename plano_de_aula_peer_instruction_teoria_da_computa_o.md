# PLANO DE AULA DETALHADO — PEER INSTRUCTION
**Disciplina:** Teoria da Computação  
**Público-Alvo:** Graduação em Ciência da Computação (Último Ano)  
**Carga Horária:** 2 Encontros de 100 minutos cada (22/10 e 23/10)  
**Docente:** Professor de Teoria da Computação  
**Metodologia:** *Peer Instruction* (Instrução pelos Pares) via Plataforma Digital (Mentimeter / Wooclap / Socrative)

---

## 1. Contexto e Objetivos Geral e Específicos

### Contexto:
Reorganização dos **Encontros 21, 22 e 23** do plano de ensino em duas sessões intensivas de 100 minutos, preparando a turma para a **Avaliação Escrita II** agendada para 29/10. Os alunos já possuem domínio sobre Máquinas de Turing, Computabilidade, Funções Recursivas e o Problema da Paragem ($A_{TM}$).

### Objetivo Geral:
Capacitar os estudantes a analisar e demonstrar a indecidibilidade de problemas computacionais através do uso da Diagonalização de Cantor, Redutibilidade Mapeada ($A \le_m B$), Teorema de Rice e Problema da Correspondência de Post (PCP).

### Objetivos Específicos:
1. **Diagonalização de Cantor:** Distinguir a cardinalidade de conjuntos contáveis ($\aleph_0$) e incontáveis ($2^{\aleph_0}$), justificando a existência intrínseca de problemas indecidíveis.
2. **Redutibilidade Mapeada ($A \le_m B$):** Aplicar corretamente o sentido da redução para a transferência de propriedades de indecidibilidade.
3. **Teorema de Rice:** Discernir entre propriedades semânticas (comportamento da linguagem $L(M)$) e propriedades sintáticas (estrutura da máquina $M$).
4. **PCP (Post Correspondence Problem):** Resolver instâncias combinatórias do PCP e compreender a sua aplicação em provas de indecidibilidade em Linguagens Livres de Contexto.

---

## 2. Recursos Necessários e Configuração Técnica

* **Projetor e Computador:** Exibição dos *slides* e da plataforma de votação.
* **Plataforma Digital de Votação (Mentimeter / Wooclap):**
  * Suporte a notação $\text{\LaTeX}$ ativado.
  * **Modo "Resultados Ocultos"** ativo para o Round 1 de cada questão (evita o efeito manada).
  * Questões duplicadas em pares de *slides* (ex: `Q1 - Votação Individual` e `Q1 - Re-votação Pós-Debate`).
* **Dispositivos dos Alunos:** *Smartphones* ou portáteis com acesso à Internet via QR Code.

---

## 3. Cronograma Detalhado

---

### SESSÃO 1: 22/10 (100 minutos)
**Tópicos:** Incontabilidade, Diagonalização de Cantor e Redutibilidade Mapeada ($A \le_m B$).

```
+-----------------------------------------------------------------------------------+
|  TEMPO  | ETAPA / TÓPICO            | ATIVIDADE / METODOLOGIA                     |
+---------+---------------------------+---------------------------------------------+
| 10 min  | Abertura e Conectividade  | Orientações gerais e acesso à plataforma    |
| 35 min  | Módulo I: Diagonalização  | Mini-exposição + ConcepTests 1 e 2          |
| 50 min  | Módulo II: Redutibilidade | Mini-exposição + ConcepTests 3 e 4          |
| 05 min  | Fecho da Sessão           | Resumo da regra de ouro das reduções        |
+-----------------------------------------------------------------------------------+
```

#### Detalhamento das Etapas (Sessão 1):

##### **00:00 – 00:10 | Abertura**
* Explicação das regras do *Peer Instruction* (Votação individual sem falar $\to$ Discussão em duplas $\to$ Re-votação).
* Leitura do QR Code de acesso à plataforma digital.

##### **00:10 – 00:45 | Módulo I: Diagonalização de Cantor**

**Introdução ao Módulo (Argumento de Diagonalização):**
O Argumento de Diagonalização de Cantor é uma prova contraintuitiva de que existem infinitos maiores do que outros. Por exemplo, para provar que existem mais números reais (decimais) do que números naturais (incontáveis vs contáveis):
1. **A Suposição:** Supõe-se que é possível listar todos os decimais infinitos, mapeando-os para números naturais (ex: $1 \to 0.[1]415...$, $2 \to 0.3[3]33...$, etc.).
2. **O Truque:** Constrói-se um novo número **X** observando a **diagonal** da lista e alterando cada dígito (ex: se o 1º dígito do 1º número é 1, muda-se para 2; o 2º do 2º número muda-se, etc.).
3. **A Conclusão:** O novo número **X** garantidamente não está na lista, pois difere do 1º número no 1º dígito, do 2º no 2º dígito, e assim por diante. Isso quebra a suposição inicial, provando ser impossível listar todos os reais (infinito incontável). Na teoria da computação, a mesma lógica prova que existem mais linguagens do que Máquinas de Turing, logo, existem problemas indecidíveis.

* **Exposição Curta (10 min):**
  * Comparação entre $\Sigma^*$ (contável, $\aleph_0$) e $\mathcal{P}(\Sigma^*)$ (incontável, $2^{\aleph_0}$).
  * Construção da tabela diagonal de Cantor e injeção de contradição para definir a linguagem $L_d$.
* **ConcepTest 1 (12 min):**
  * *Pergunta:* Suponha o alfabeto $\Sigma = \{0, 1\}$. Qual das seguintes afirmações sobre os conjuntos envolvidos na Teoria da Computação é correta?
    * A) O conjunto de todos os programas válidos em Python é incontável.
    * B) Existe uma bijeção entre o conjunto dos números inteiros ($\mathbb{Z}$) e o conjunto de todas as Máquinas de Turing possíveis.
    * C) Todas as linguagens no alfabeto $\Sigma$ são computavelmente enumeráveis.
    * D) A diagonalização de Cantor demonstra que o conjunto $[0,1] \subset \mathbb{R}$ tem o mesmo tamanho de $\mathbb{N}$.
  * *Gabarito:* **B** (Ambos são infinitos contáveis $\aleph_0$).
  * *Fluxo:* V1 (1,5 min) $\to$ Debate em Pares (3 min) $\to$ V2 (1 min) $\to$ Explicação (3 min).
* **ConcepTest 2 (13 min):**
  * *Pergunta:* Na matriz infinita onde cada linha é uma Máquina de Turing $M_i$ e cada coluna uma palavra $w_j$, o método da diagonalização constrói $L_d$ tal que $w_i \in L_d \iff M_i$ não aceita $w_i$. O que prova o facto de $L_d$ diferir de cada linha $i$ em pelo menos um elemento?
    * A) $L_d$ é uma linguagem finita.
    * B) Nenhuma Máquina de Turing $M_i$ pode reconhecer/decidir $L_d$.
    * C) $L_d$ é decidível por uma Máquina de Turing Universal.
    * D) $L_d$ pode ser decidida se expandirmos o alfabeto.
  * *Gabarito:* **B**.

##### **00:45 – 00:95 | Módulo II: Redutibilidade Mapeada ($A \le_m B$)**
* **Exposição Curta (10 min):**
  * Definição formal: $w \in A \iff f(w) \in B$, onde $f$ é uma função total e computável.
  * Transferência de propriedades: Se $A \le_m B$ e $A$ é indecidível $\implies B$ é indecidível.
* **ConcepTest 3 (20 min):**
  * *Pergunta:* Sabemos que o problema $A$ é indecidível e construímos uma redução mapeada tal que $A \le_m B$. O que podemos afirmar rigorosamente sobre $B$?
    * A) Nada se pode afirmar sobre $B$.
    * B) $B$ é obrigatoriamente decidível.
    * C) $B$ é obrigatoriamente indecidível.
    * D) $B$ é computavelmente enumerável, mas não decidível.
  * *Gabarito:* **C**.
* **ConcepTest 4 (20 min):**
  * *Pergunta:* Um estudante quer provar que um novo problema $X$ é indecidível. Sabendo que o Problema da Paragem $A_{TM}$ é indecidível, qual redução o estudante DEVE construir?
    * A) $X \le_m A_{TM}$
    * B) $A_{TM} \le_m X$
    * C) $X \le_m \emptyset$
    * D) Ambas as reduções A) e B) servem.
  * *Gabarito:* **B** (Reduz-se o problema conhecido $A_{TM}$ ao problema novo $X$).

##### **00:95 – 01:00 | Síntese do Dia**
* Fixação do conceito: Para provar que $X$ é difícil, mostramos como usar $X$ para resolver um problema sabidamente difícil ($A_{TM} \le_m X$).

---

### SESSÃO 2: 23/10 (100 minutos)
**Tópicos:** Teorema de Rice, Problema da Correspondência de Post (PCP) e Matriz de Decidibilidade para a Prova.

```
+-----------------------------------------------------------------------------------+
|  TEMPO  | ETAPA / TÓPICO            | ATIVIDADE / METODOLOGIA                     |
+---------+---------------------------+---------------------------------------------+
| 05 min  | Reativação                | Recapitulação da Sessão 1                   |
| 40 min  | Módulo III: Rice          | Mini-exposição + ConcepTests 5 e 6          |
| 40 min  | Módulo IV: PCP            | Mini-exposição + ConcepTest 7               |
| 15 min  | Fecho e Revisão P2        | Matriz de Decidibilidade e Alinhamento      |
+-----------------------------------------------------------------------------------+
```

#### Detalhamento das Etapas (Sessão 2):

##### **00:00 – 00:05 | Reativação**
* Ligação entre redução mapeada e a generalização promovida pelo Teorema de Rice.

##### **00:05 – 00:45 | Módulo III: Teorema de Rice**
* **Exposição Curta (10 min):**
  * Propriedades semânticas (relativas à linguagem $L(M)$) vs. propriedades sintáticas (relativas à estrutura de $M$).
  * Enunciado do Teorema: Qualquer propriedade não trivial da linguagem reconhecida por uma MT é indecidível.
* **ConcepTest 5 (15 min):**
  * *Pergunta:* Qual dos seguintes problemas sobre uma Máquina de Turing $M$ é **DECIDÍVEL** (onde o Teorema de Rice NÃO se aplica)?
    * A) Saber se $L(M) = \emptyset$.
    * B) Saber se $L(M)$ contém a palavra `"computacao"`.
    * C) Saber se o número de estados da Máquina de Turing $M$ é superior a 100.
    * D) Saber se $L(M)$ é uma linguagem regular.
  * *Gabarito:* **C** (Contar estados é uma análise sintática direta do código/grafo da máquina).
* **ConcepTest 6 (15 min):**
  * *Pergunta:* Considere a propriedade $P$: *"A Máquina de Turing $M$ aceita a palavra '101' em menos de 50 passos"*. Esta propriedade é indecidível pelo Teorema de Rice?
    * A) Sim, porque se refere ao comportamento da máquina.
    * B) Não, porque não é uma propriedade da linguagem $L(M)$ e pode ser simulada e decidida em tempo finito.
    * C) Sim, porque envolve palavras da linguagem.
    * D) Não, porque todas as propriedades de linguagens são decidíveis.
  * *Gabarito:* **B** (Simulável em no máximo 50 passos, garantindo paragem e decisão).

##### **00:45 – 01:25 | Módulo IV: Problema da Correspondência de Post (PCP)**
* **Exposição Curta (10 min):**
  * Formulação do PCP como um quebra-cabeça de dominós $\left[\frac{topo}{base}\right]$.
  * **O Teorema de Post e Caminhos Possíveis:** $L \text{ é decidível} \iff L \in \mathcal{RE} \land \overline{L} \in \mathcal{RE}$.
    - A busca em largura (BFS) avança por *caminhos possíveis* (onde uma cadeia é prefixo da outra). Se há solução finita, ela é encontrada $\implies PCP \in \mathcal{RE}$ (semi-decidível).
    - Se não há solução, caminhos infinitos podem continuar se ramificando sem nunca fechar $\implies \overline{PCP} \notin \mathcal{RE}$. Pelo Teorema de Post, o PCP é indecidível.
  * Importância teórica: Prova de indecidibilidade em problemas de Gramáticas Livres de Contexto (GLCs) via $A_{TM} \le_m PCP$.
  * **Provocação Pós-Simulador:** *"Tá bom, você é um cara muito inteligente e achou uma resposta..."* Desmistificar a ilusão do sucesso local: achar uma solução em uma instância particular não significa que o problema geral seja decidível. Se um conjunto não tiver solução, um programa testará infinitas combinações em um loop eterno sem conseguir provar a não existência — comportando-se exatamente como o Problema da Parada.
* **ConcepTest 7 / Atividade em Duplas (30 min):**
  * *Pergunta:* Considere as peças de Post: $t_1 = \left[\frac{b}{ca}\right]$, $t_2 = \left[\frac{a}{ab}\right]$, $t_3 = \left[\frac{ca}{a}\right]$, $t_4 = \left[\frac{abc}{c}\right]$. Ao testar a sequência $(2, 1, 3)$, obtemos Topo = $abca$ e Base = $abcaa$ (um caminho possível com prefixo compatível). Com base no **Teorema de Post** e nas propriedades do PCP, o que podemos afirmar?
    * A) A sequência $(2, 1, 3)$ já encerra a busca, pois no PCP basta que uma das cadeias seja prefixo da outra para configurar decisão.
    * B) A sequência $(2, 1, 3)$ é apenas uma correspondência parcial; a solução exata exige a extensão $(2, 1, 3, 2, 4)$ que gera "abcaaabc" em ambos. Pelo Teorema de Post, a busca por caminhos possíveis torna o PCP reconhecível, mas a existência de caminhos infinitos sem solução torna $\overline{PCP}$ não reconhecível (indecidível).
    * C) Como a base tem um caractere excedente em $(2, 1, 3)$, este caminho sofreu desalinhamento irrecuperável e nenhuma extensão finita poderá jamais fechar uma solução.
    * D) Pelo Teorema de Post, demonstrar que uma instância de dominós possui ao menos um caminho possível é condição matemática suficiente para provar que o complemento do problema é decidível por autômatos finitos determinísticos com fita bidirecional em tempo polinomial.
  * *Gabarito:* **B**
  * *Demonstração Rigorosa:*  
    No PCP, a condição de solução é a igualdade estrita: $\text{Topo} = \text{Base}$.  
    - A sequência parcial $(2, 1, 3)$ é um *caminho possível* ($abca \sqsubset abcaa$), mas não encerra a instância.  
    - A extensão $(2, 1, 3, 2, 4)$ atinge a igualdade:
      Topo: $t_2(a) + t_1(b) + t_3(ca) + t_2(a) + t_4(abc) = \mathbf{abcaaabc}$  
      Base: $t_2(ab) + t_1(ca) + t_3(a) + t_2(ab) + t_4(c) = \mathbf{abcaaabc}$  
      Ambas as palavras são idênticas ($\mathbf{abcaaabc}$, 8 caracteres).  
    - **Aplicação do Teorema de Post:** Como o algoritmo pode encontrar qualquer correspondência válida por BFS, o PCP é Turing-reconhecível. Contudo, na ausência de solução, caminhos possíveis podem crescer indefinidamente em loop infinito, impedindo o reconhecimento de $\overline{PCP}$. Pelo Teorema de Post, o PCP é indecidível.
    *(Nota de condução: Esclareça aos alunos a diferença entre um caminho viável na árvore de busca e um match completo).*
* **Laboratório Interativo 2: Simulação de Instância Indecidível (Loop Infinito):**
  * Teste interativo com o conjunto $\{[ab/a], [a/bac], [cab/a]\}$, que não possui correspondência finita.
  * Demonstração ao vivo da busca automática: o computador avança determinística e infinitamente ($t_1 \to t_2 \to t_3 \to t_2 \dots$) sem nunca igualar os comprimentos (diferem sempre em 1 caractere), evidenciando o loop eterno da não parada no PCP.

##### **01:25 – 01:40 | Fecho e Matriz de Síntese para a Prova de 29/10**
Projeção e discussão da tabela resumo no quadro:

| Problema / Propriedade | Classificação | Técnica de Prova / Motivação |
| :--- | :--- | :--- |
| **Existência de Linguagem Não Decidível** | Indecidível | Diagonalização de Cantor |
| **Problema da Paragem ($A_{TM}$)** | Indecidível | Diagonalização / Redução Mapeada |
| **Propriedade Semântica Não Trivial de $L(M)$** | Indecidível | Teorema de Rice |
| **Propriedade Sintática (ex: nº de estados, alfabeto)** | Decidível | Inspeção Direta do Grafo da MT |
| **Correspondência de Cadeias em Dominós (PCP)** | Indecidível | Redução a partir de Históricos de Computação |

---

## 4. Métricas e Avaliação Formativa

* **Indicador de Retenção:** Comparação dos percentuais globais entre V1 (Votação Individual) e V2 (Re-votação pós-discussão em pares). A meta esperada é uma evolução de 15% a 40% de incremento nos acertos em V2.
* **Ajuste de Reta Final:** Os conceitos que mantiverem taxa de acerto em V2 abaixo de 60% serão alvo dos minutos iniciais de revisão antes da prova do dia 29/10.

---

## 5. Referências Bibliográficas

1. **DIVERIO, Tiarajú Asmuz; MENEZES, Paulo Blauth.** *Teoria da computação: máquinas universais e computabilidade*. 3. ed. Porto Alegre: Bookman, 2011. (Capítulos 3, 4 e 5).
2. **HOPCROFT, John E.; ULLMAN, Jeffrey D.; MOTWANI, Rajeev.** *Introdução à teoria de autómatos, linguagens e computação*. 2. ed. Rio de Janeiro: Elsevier, 2003. (Capítulo 9).