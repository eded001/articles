## Definição
De forma sintetizada, a ***ED*** (estrutura de dados) é usada para **armazenar ou agrupar dados**. Existem diferentes formas de organizar dados dependendo do tipo de dado que tivermos e como podemos ou queremos dispor.

## Importância
A ED é o **ingrediente essencial na criação de algoritmos rápidos e poderosos**. Desse modo, ajudam a **manusear e organizar os dados**, reduzindo sua complexidade e aumentando sua eficiência.

## Classificações e tipos
Estruturas de dados
- Linear
    - Estática
        1. Vetor (array)
    - Dinâmica
        1. Fila (queue)
        2. Pilha (stack)
        3. Lista lincada (linked list)
- Não linear
    1. Árvore (tree)
    2. Grafo (graph)

### Linear
#### Definição
Estrutura de dado em que os elementos são **dispostos sequencialmente ou linearmente**, isso é, **cada elemento que é adicionado ao seu último elemento**.
##### Estática
Isso quer dizer que estrutura segue com um **tamanho de memória fixo**. Logo, seu acesso aos elementos é mais fácil, como é o *vetor*.
###### Vetor
O vetor é uma estrutura de dado linear que guarda uma **coleção de elementos do mesmo tipo**. Uma das suas principais características é de que seus elementos podem ser localizados facilmente, visto que estes são **indexados a cada adição**. Então, **cada elemento possui um índice** - começando por 0.

![Representação de um array](https://raw.githubusercontent.com/eded001/articles/refs/heads/main/estrutura-de-dados/imgs/array.png)

##### Dinâmica
Diferente da estrutura de dado linear, a dinâmica **não possui um tamanho fixo**. É **totalmente aleatório** e **pode ser atualizado durante o processo de execução do programa**. Por exemplo: filas, pilhas e as listas lincadas.

###### Fila
A fila segue o princípio do ***FIFO*** (First-In-First-Out ou Primeiro a entrar, primeiro a sair), que é um método em que o **primeiro elemento que chegou vai ser processado e quaisquer elementos subsequentes serão processados**.

![Representação de uma fila](https://raw.githubusercontent.com/eded001/articles/refs/heads/main/estrutura-de-dados/imgs/queue.png)

##### Pilha
Diferente da fila, a pilha usa o princípio do **LIFO** (Last In, First Out ou Último a entrar, primeiro a sair) que, simplesmente, **o primeiro elemento é processado e o último elemento é processado primeiro**, ou seja, começa de trás pra frente.
![Representação de uma stack](https://raw.githubusercontent.com/eded001/articles/refs/heads/main/estrutura-de-dados/imgs/stack.png)

##### Lista lincada
A lista lincada, diferente da fila e da pilha, segue com uma particularidade muito peculiar: **seus elementos são armazenados em nós** (nodes), sendo estes conectados por *ponteiros* - endereços de memória que apontam para uma variável - e **só podem ser acessados de forma sequencial**. Logo, cada ponteiro aponta para o próximo nó.

![Representação de uma linked list](https://raw.githubusercontent.com/eded001/articles/refs/heads/main/estrutura-de-dados/imgs/linked-list.png)

### Não linear
#### Definição
A estrutura não linear diferente da linear, **os elementos não dispostos de forma sequencial e muito menos de forma linear**, o que implica dizer que **não se pode atravessar todos os elementos de uma vez**, como é o caso da árvore e dos grafos.
#### Árvore
A árvore segue uma organização baseada em uma **hierarquia que consiste em nós (nodes) interligados por bordas (edges)**. Sendo o **topo da árvore denominada "raiz" (root)** e essa **raiz possui nós filhos** - relação de parent e child nodes.

![Representação de uma tree](https://raw.githubusercontent.com/eded001/articles/refs/heads/main/estrutura-de-dados/imgs/tree.png)

#### Grafo
O grafo consiste em um **conjunto finito de vértices (ou nós)** e por um **conjunto de arestas (links) que conectam pares de nós**, representando um relacionamento entre entidades.

![Representação de um grafo](https://raw.githubusercontent.com/eded001/articles/refs/heads/main/estrutura-de-dados/imgs/graph.png)

## Extra
### Stack Overflow
Conhece a comunidade *[Stack Overflow](https://stackoverflow.com/)*? Duvido não conhecer, eu mesmo já tirei muitas fazendo pesquisas por lá. Bem, se você não conhece, o *Stack Overflow* é uma comunidade dentro do ramo da programação/computação que é dedicada exclusivamente a perguntas e respostas. Mas pra quem já conhece, você conhece a origem do nome?

![Representação de um grafo](https://raw.githubusercontent.com/eded001/articles/refs/heads/main/estrutura-de-dados/imgs/stack-overflow-logo.png)

### Stack overflow
Afinal, o que é esse tal ***stack overflow***? Agora referindo-se ao processo que ocorre, stack overflow, na sua tradução literal, equivale a **estouro de pilha**, o que quer dizer que a **pilha "vazou" ou "transbordou"**.
Continuando o tópico anterior, de forma simplificada, o stack overflow é um processo em que se aloca demasiada memória pra dentro de uma pilha e essa pilha "transborda", visto que a pilha não suportava essa quantidade toda de memória. E o que isso quer dizer? Simples, que **o programa tá alocando muita memória pra um espaço que não consegue armazenar o tanto de memória**. E isso pode ocorrer de várias formas e por diferentes fatores.

Por exemplo, imagine que você utiliza uma biblioteca ou instanciou um objeto de uma classe e quer usar as funções/métodos dessa ferramenta. Até aí tudo bem, mas imagine que há uma limitação na quantidade de funções que podem ser chamadas. Então, você chama uma função que chama outras três funções para executar tal processo, e isso vai ocorrendo ao longo do seu código. Parece tranquilo, certo? Não, não é. Quando você chama várias funções, cada chamada é armazenada na pilha de execução (stack). A pilha tem um **espaço limitado** e, se você fizer muitas chamadas aninhadas **sem liberar a memória** (ou seja, sem que as funções retornem), você pode acabar causando um **stack overflow**.

O stack overflow acontece quando a pilha de execução excede seu limite de memória, resultando em um ***erro fatal*** no programa. Se você estiver usando Windows, isso pode até causar a famosa ***tela azul da morte*** (BSOD ou Blue Screen of Death).

![BSOD](https://raw.githubusercontent.com/eded001/articles/refs/heads/main/estrutura-de-dados/imgs/bsod.jpg)

Portanto, é crucial gerenciar corretamente a memória e as chamadas de função para evitar esse problema e você também não gostaria que o seu programinha desse uma tela azul medonha como essa não é? Então, é importante estudar sobre alocação de memória, ponteiros e afins. Ou não... Hoje em dia, muitas linguagens de programação já cuidam disso. Diferentemente de linguagens mais robustas, como *C*, por exemplo ou o temido *Assembly*. Ainda assim, nós cuidamos do nosso "lixo" que, no contexto da programação, é chamado de ***GC*** ou ***Garbage Collection*** (coleta de lixo). Mas, ainda assim, é muito difícil fazer um stack overflow com linguagens modernas com JavaScript, PHP, Python e muitas outras. Mas não impossível...

## Referências
1. [GeeksforGeeks | Data Structures Tutorial](https://www.geeksforgeeks.org/data-structures/)
2. [GeeksforGeeks | FIFO (First-In-First-Out) approach in Programming](https://www.geeksforgeeks.org/data-structures/)
3. [GeeksforGeeks | LIFO (Last-In-First-Out) approach in Programming](https://www.geeksforgeeks.org/data-structures/)
4. [Intellectuale | Ponteiros em C](https://linguagemc.com.br/ponteiros-em-c/)
5. [GeeksforGeeks | Basic Terminologies of Linked List](https://www.geeksforgeeks.org/what-is-linked-list/)
6. [GeeksforGeeks | Introduction to Tree Data Structure - GeeksforGeeks](https://www.geeksforgeeks.org/what-is-linked-list/)
7. [W3Schools | Introduction  to Data Structures and Algorithms](https://www.w3schools.com/dsa/dsa_intro.php)
8. [Stack Overflow | How does a "stack overflow" occur and how do you prevent it?](https://stackoverflow.com/questions/26158/how-does-a-stack-overflow-occur-and-how-do-you-prevent-it)
