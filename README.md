#                      LISTA|PILHA|FILHA


##  1)A

- Programa criado utilizando a estrutura LISTA
- Criar uma lista A com 100 números aleatórios par e uma LISTA B com 100 números aleatórios impar
- Concatenar essas lista unindo listaA e listaB mantendo as posições
- Ex: {{L1[0], L2[0]},{L1[1], L2[1]}, . . . , {L1[99], L2[99]}}


Markdown is a lightweight markup language based on the formatting conventions
that people naturally use in email.
As [John Gruber] writes on the [Markdown site][df1]

### Construção

1) Inicialmente no main criase a lista A, que armazenará os números pares, a lista b que recebera os números impares e a lista de concatenação.

2) Usando a função de iniciação padrão de uma lista FLVazia(Lista *l), iniciasse as lista adicionando o bloco de memoria a ser armazenado futuramente.

3) Utilizando a função (rand() % 100), iremos gerar os números aleatórios para serem adicionado nas listas dentro as funções PreencheListaPar(Lista *l) e PreencheListaImpar(Lista *l).

4) Com as duas lista criadas, chama-se a função LConcatena(&listaC,&listaA,&listaB). No qual é usada uma lista com uma struct que armazena dois inteiros em 2 variáveis, juntando assim os valores de listaA e listaB das mesmo posições em uma mesma variavel struct.

###### Exemplo struct lista

´´´
struct Item{
	int dado;
};
struct Lista{
	int quantid;
	Item item[MAXTAM];
};
´´´
###### Exemplo struct lista Concatenada
struct ItemC{
	int dadoL1;
	int dadoL2;
};
struct Concatena{
	int quantid;
	ItemC item[MAXTAM];
};
´´´
##  1)B

### Construção

1) Programa criado utilizando Lista
2) Cria-se duas listas com uma struct de armazena um vetor de inteiros com 3 posições
3) Listas iniciados no main com a função padrao de Lista FLVazia(Lista *l);
4) Na função PreencheLista(Lista *l) logo iniciado apos a criação da lista, utiliza-se da função (rand() % 13) para armazenar os valores no vetor da struct das listas. Valores esses aleatórios entre 1 e 13;
5) Logo após, é criado um outro número aleatório, entre 1 e 13, recebido na variável num. 
6) Em seguida, a função SubtraiLista() uni os valores iguais dos vetores das duas listas, ou seja {{L1[0], L2[0]}, {L1[1], L2[1]}, {L1[2], L2[2]}}. e subtrai dessas duplas o valor de num ateriormente criado.
7) A função VerificaListaVencedora(&l1,&l2) pega os valores dessas lista apos a subtração de num e soma, a lista que tiver o maior valor vence.


## 1C

- Programa criado utilizando a estrutura LISTA
- Criação de 3 Lista diferentes
- Concatenar essas lista unindo listaA e listaB mantendo as posições
- Ex: {{L1[0], L2[0]},{L1[1], L2[1]}, . . . , {L1[99], L2[99]}}

### Construção


3) Listas iniciados no main com a função padrao de Lista FLVazia(Lista *l);
4) Na função PreencheLista(Lista *l) logo iniciado apos a criação da lista, utiliza-se da função (rand() % 13) para armazenar os valores no vetor da struct das listas. Valores esses aleatórios entre 1 e 13;
5) Logo após, é criado um outro número aleatório, entre 1 e 13, recebido na variável num. 
6) Em seguida, a função SubtraiLista() uni os valores iguais dos vetores das duas listas, ou seja {{L1[0], L2[0]}, {L1[1], L2[1]}, {L1[2], L2[2]}}. e subtrai dessas duplas o valor de num ateriormente criado.
7) A função VerificaListaVencedora(&l1,&l2) pega os valores dessas lista apos a subtração de num e soma, a lista que tiv
