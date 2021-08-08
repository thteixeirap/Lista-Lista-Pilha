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

```sh
struct Item{
	int dado;
};
struct Lista{
	int quantid;
	Item item[MAXTAM];
};
```
###### Exemplo struct lista Concatenada
```sh
struct ItemC{
	int dadoL1;
	int dadoL2;
};
struct Concatena{
	int quantid;
	ItemC item[MAXTAM];
};
```
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

### Construção
1) Foi realizada a criação de 3 lista com structs diferentes
2)Lista1 armazena uma string para adicionar o nome do produto, um int para o identificador e um outro para a quantidade
3) Lista2 armazena uma string para adicionar o nome do mercado e um int para o identificador
4) Lista3 adiciona a struct da lista1 com dados do produto, adiciona a struct da lista2 com os dados do produto e um float para adicionar o valor do produto;

## Funcionalidade

1) Primeiro com a função AdicionaProduto(&lista1), ocorre a adição de todos os produtos, informando o nome, a identidicação e a quantidade. Usando um while para a opção de sair(No qual ira levar para adicionar o mercado), ou a função de adicionar novamente outro produto.
2) Logo após todo o incremento dos produtos, ocorre a adição dos mercados, com a adição do nome e do identificador, utilizando um while para a opção de sair e de adicionar novamente outro mercado
3) Após adicionar esses dados, iniciasse a função de adicionar preço, em que inicialmente aparece um menu com todos os produtos.Logo a escolha do produto, seleciona-se em qual mercado esse produto será cadastrado e seguindo qual valor nesse mercado o produto terá.
4) Na função de cadastro de preço, é utilizado um while no qual apos a ação apresentará um menu em que oferece a possibilidade de adicionar outro produto nesse mercado, escolher outro mercado, ou sair.
5)Escolhendo sair, aparece a opção carrinho no qual o usuário escolhe quais produtos ele deseja comprar, no qual será somados entre todos os mercados essas escolhas e apresentado qual mercado terá o menor preço dessa compra.

# Pilha

## 2A
- Programa criado utilizando a estrutura PILHA
- Identificar erros nos parenteses na equação

### Construção

1) O programa é iniciado com uma equação modelo "(2+7)5)8*9)(7/9(3-7"
2) Inicialmente no main iniasse uma Pilha com a função padrao FPVazia();
3) A função tokeniza() terá como parametro o tamanho da equação e qual é essa equação.

##### Função Tonekiza
```sh
void Tokeniza(const int size,Pilha *p,char equation[size]){
	Item item;
	int i;
	for(i=0;i<size;i++){
		if(equation[i] == '('){
			item.val = equation[i];
			Push(p,item);
			Confere(1,p);
		}else if(equation[i] == ')'){
			item.val = equation[i];
			Push(p,item);
			Confere(2,p);
		}
	}
}
```
- Explicando função Tokeniza

O for irá varrer toda a equação, identidicando sempre quando houver uma abertura ou fechamento de parentes. Ocorrendo uma dessa situações, ocorre o empilhamentos dessa parenteses e a chamanda da função Confere.

##### Função Confere

```sh
void Confere(int op,Pilha *p){
	
	if(p->cont.openClose <= 0 && op == 2){ //UM FECHADO SEM UM ABERTO DE PAR
		printf("ERRO DE PARENTESES NA EQUACAO!\n");
		exit(0);
	}else if(p->cont.openClose > 0 && op == 1){ //ABERTURA QUANDO CONT ZERADO
		p->cont.openClose++;
	}else if(p->cont.openClose >= 0 && op == 2){//
		p->cont.openClose--;
	}	
}
```
- Explicando função Confere

Se o char recebido for '(', ocorre a soma de +1 na variável de verificação, caso char recebido for ')' ocorre o decremento de -1 nessa variavél. Caso verficado um ')' e, a variavel de verificação esteja em 0, significa o fechamento de uma parenteses em uma aberta para anular. O programa ja printa o erro e termina o programa. 

4) Não ocorrendo o erro de parenteses fechada sem uma aberta para anular, o iniciasse a função Valida, na qual identifica erro de parenteses abertas sem fechar, na qual verifica se a função valida esta em 0 ou >0.

