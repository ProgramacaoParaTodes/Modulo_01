# Aula 04

Na nossa quarta aula, falamos sobre os seguintes assuntos:

- While.
- Aninhando outros blocos de código dentro do while.
- Utilizando uma variável como acumulador.
- Repetição indefinida e o comando break.
- Decréscimo de valores no contador.
- Mais métodos de string: upper(), lower(), count().

Para acessar os Repls desta aula, clique [aqui](https://repl.it/@ProgParaTodes/BlankGrayOop#main.py), [aqui](https://repl.it/@ProgParaTodes/DeadWaryMonads#main.py), [aqui](https://repl.it/@ProgParaTodes/KaleidoscopicWindyObjectmodel#main.py), [aqui](https://repl.it/@ProgParaTodes/IndigoUnsightlyDemoware#main.py) e [aqui](https://repl.it/@ProgParaTodes/GargantuanAnotherWorkspace#main.py).

## While

Utilizamos o while para fazer repetições. 

Vimos que podemos escrever uma repetição de comandos de uma maneira mais automatizada. Então, o problema de imprimir os números de 0 até 5 sem usar o *print()* cinco vezes pode ser resolvido da seguinte maneira:

```python
x = 0
while x <= 5: 
    print(x) 
    x = x + 1 
```

Onde *x = 0* é nosso **contador** que será incrementado dentro do *while*.

Enquanto a condição *x <= 5* for verdadeira, o programa continuará executando as linhas dentro do *while* (atenção para a indentação!).

Em um dado momento, o valor de x será 6. Sendo assim, a condição *x <= 5* deixa de ser verdadeira e o programa se encerra.

Se quisermos ampliar a resolução deste problema para "imprimir os números de 0 até ___", podemos pedir que o usuário digite um valor que será o nosso limite máximo:

```python
numero_maximo = int(input("Imprimir os números de 0 até: \n"))
print("\n")
x = 0

while x <= numero_maximo: 
    print(x) 
    x = x + 1

print("Fim")
```
A variável *numero_maximo* entra no lugar do 5 deixando a resolução genérica. 

Aqui, temos a linha *print("Fim")* para nos lembrar que ela só será impressa na tela quando todas as iterações dentro do *while* acabarem. 

E quando isso ocorre?

Da mesma maneira que no primeiro exemplo, a variável **x** é o **contador**. 

Isso significa que ela nos ajudará a controlar o fluxo do programa. A cada iteração, ela será incrementada e, em um dado momento, a condição *x <= numero_maximo* deixará de ser verdadeira. 

Neste momento, as iterações dentro do *while* terminam e a linha *print("Fim")* é executada.

## Aninhando outros blocos de código dentro do while

*Para o exemplo que eu quis colocar nestas notas de aula, utilizei uma operação que não ensinei na aula, mas vou deixar a explicação [aqui](https://repl.it/@ProgParaTodes/RestoDaDivisao#main.py), ok? Qualquer dúvida, falem comigo! ;)*

Podemos colocar outros blocos de código dentro do *while* como, por exemplo, o *if*.

No exemplo a seguinte, queremos mostrar na tela somente os números pares de 0 até um determinado número.

```python
numero_maximo = int(input("Mostrar na tela os números pares de 0 até: \n"))
print("\n")
contador = 0

while contador <= numero_maximo:
    if contador % 2 == 0:
        print(contador)
    contador += 1           # contador += 1 é um sinônimo de contador = contador + 1

print("\nPronto!")
```

Vamos entender o código passo-a-passo:

1. Primeiro eu peço para o usuário digitar o valor que limitará a execução do programa. Se ele digitar *9*, por exemplo, o programa deverá exibir na tela os números 0, 2, 4, 6 e 8.
2. A variável **contador** (nosso contador) inicia com o valor 0, afinal, queremos imprimir o zero! Dentro do *while* ela será incrementada até que a condição *contador <= numero_maximo* seja falsa.
3. Dentro do *while* temos um *if* que verifica se a divisão de  *contador* por 2 tem resto zero. (Lembram da operação com **%**?) Se o resto é zero, significa que o número é par; caso contrário, é ímpar.
4. Note que a variável **contador** sempre será incrementada dentro do *while*, independentemente do que ocorre no *if*. 
5. Quando a condição *contador <= numero_maximo* se tornar falsa, a linha *print("\nPronto!")* será executada.

Colocando a execução do código em uma tabela, temos o seguinte:

| Iteração | contador | contador <= numero_maximo |  contador % 2 == 0 | print(contador) | contador += 1 |
|:--------:|:--------:|:-------------------------:|:------------------:|:---------------:|:-------------:|
|    1a.   |    0     | 0 <= 6: True              | 0 % 2 == 0: True   |        0        |       1       |
|    2a.   |    1     | 1 <= 6: True              | 1 % 2 == 0: False  |        -        |       2       |
|    3a.   |    2     | 2 <= 6: True              | 2 % 2 == 0: True   |        2        |       3       |
|    4a.   |    3     | 3 <= 6: True              | 3 % 2 == 0: False  |        -        |       4       |
|    5a.   |    4     | 4 <= 6: True              | 4 % 2 == 0: True   |        4        |       5       |
|    6a.   |    5     | 5 <= 6: True              | 5 % 2 == 0: False  |        -        |       6       |
|    7a.   |    6     | 6 <= 6: True              | 6 % 2 == 0: True   |        6        |       7       |
|    8a.   |    7     | 7 <= 6: False             |                    |                 |               |

A 1a. iteração é a primeira vez que a execução do programa "bate" na linha do *while* e como *0 <= 6* é True, passará para a linha que tem o *if*.

A 8a. iteração é a última vez que a execução do programa "bate" na linha do *while* pois *7 <= 6* é False, portanto, a próxima linha a ser executada é *print("\nPronto!")*.

## Utilizando uma variável como acumulador

Vimos também a situação de queremos somar 10 números distintos e exibir o valor da soma na tela.

```python
contador = 1        
soma_total = 0     

while contador <= 10:
    numero = int(input("Digite o %do. número: " % contador)) 
    soma_total = soma_total + numero
    contador += 1

print("Soma: %d" % soma_total)
```

A variável *soma_total* é o nosso acumulador porque ela irá guardar o total da soma. A cada iteração no *while* ela receberá o valor dela mesma acrescido do número digitado.

Quando estamos acumulando valores somados, inicializamos nosso acumulador com 0. Caso o acúmulo seja feito através de uma multiplicação, inicializamos a variável com o valor 1.

O valor total da soma é exibido **fora** do *while*, **depois** que as iterações terminaram. 

## Repetição indefinida e o comando *break*

Até agora, vimos exemplos nos quais nós determinados a condição do *while*. 

Existe a possibilidade de termos o *while* combinado com True, isso fará com que a repetição ocorra indefinidamente até que **algo ocorra**. 

Vejamos o exemplo a seguir:

```python
soma_total = 0

while True:
    numero = int(input("Digite um número inteiro para somar ou digite 0 para encerrar a soma: ")) 
    if numero == 0:
        break 
    soma_total += numero          # soma_total += numero é um sinônimo de soma_total = soma_total + numero

print(soma_total)
```

Não há uma condição a ser verificada no *while*, apenas o True. 

Neste programa, o usuário deverá digitar um número inteiro para ser somado ou digitar 0 para encerrar a soma. Se ele digitar números inteiros diferentes de zero indefinidamente, a soma continuará ocorrendo.

Temos um *if* dentro do *while* que verifica se o número digitado é 0 e, caso seja isso mesmo, temos o comando **break** ali. 

Esse comando faz com que a execução do programa prossiga para fora do *while*. Ou seja: se o usuário digitar o número 0, a próxima linha a ser executada é a linha *print(soma_total)*.

Outro ponto imporante: assim como vimos que *contador = contador + 1* também pode ser escrito como *contador += 1*, temos aqui a linha *soma_total += numero* que significa exatamente *soma_total = soma_total + numero*.

## Decréscimo de valores no contador

Até o momento, vimos os contadores recebendo acréscimos. Podemos ter contadores que fazem decréscimos!

Vejamos o exemplo:

```python
inicio = int(input("Digite o início da contagem regressiva: \n"))

print("\n")

while 0 <= inicio:
    print(inicio)
    inicio -= 1           # análogo ao que vimos anteriormente para a soma: inicio = inicio - 1

print("\n")
print("Fogo! 🚀")
```

Este código faz uma contagem regressiva a partir do início estipulado pelo usuário. Veja que o valor inicial da contagem regressiva - a variável **inicio** - é o próprio contador.

Dentro do *while*, a variável **inicio** sofre um decréscimo de 1. Temos ali *inicio -= 1* que é análogo a *inicio = inicio - 1*.

## Mais métodos de string: upper(), lower(), count()

**upper()**

Transforma todas as letras em maiúsculas.

```python
message = "Fica em casa!"
message_uppercase = message.upper()
print(message_uppercase)    # mostra na tela: FICA EM CASA!
```

**lower()**

Transforma todas as letras em minúsculas.

```python
message = "HAHAHAHAHAHAHAHA"
message_lowercase = message.lower()
print(message_lowercase)    # mostra na tela: hahahahahahahaha
```

**count()**

Conta o número de vezes que um determinado texto aparece na string.

```python
email = "usuario@provedor.com.br"
at_sign = email.count("@")
print(at_sign)
```

Esses métodos podem ser úteis de diversas formas, por exemplo, em um programa que o usuário precise escolher a opção A ou B. Ao pegar o input do usuário, você pode converter com o método *upper()* e só depois verificar se foi A ou B que ele digitou.

O método *count()* pode ser útil para descobrir, como no exemplo mostrado, se o usuário digitou o e-mail mais próximo do valor válido, ou seja, com apenas uma @. 

### Primeiro Desafio 🏆

Você deverá criar uma calculadora que receberá dois números inteiros positivos e, em seguida, uma operação (+, -, * ou /). Quando for digitada a operação, o resultado deverá ser exibido na tela.

**Requisitos**

1. Só pode digitar números inteiros positivos, ou seja, a string digitada só poderá conter caracteres numéricos (0 até 9): 0, 1, 14, 35, 129...
1.1. Enquanto não for digitada uma string que possua somente caracteres numéricos para o **primeiro número**, o programa deverá exibir a crítica e solicitar novamente que o número seja digitado.
1.2. Enquanto não for digitada uma string que possua somente caracteres numéricos para o **segundo número**, o programa deverá exibir a crítica e solicitar novamente que o número seja digitado.
1.3. Enquanto não for digitada uma operação válida ou a letra S, o código deverá exibir a crítica e solicitar novamente que a operação ou o S seja digitado.
2. Se for digitado S (ou s) no momento em que a operação é solicitada, a execução do código deve parar.
3. Se o segundo número for zero e a operação escolhida for a divisão, a operação não deverá ocorrer. O programa deverá exibir a crítica e retornar automaticamente para a digitação dos números.
4. O resultado da operação deverá ser um float com 2 casas decimais para todas as operações, exceto para a divisão, quando deverá ter 3 casas decimais.
5. O resultado deverá ser exibido da seguinte maneira:
```sh
5 * 2 = 10.00
```
Neste caso, foi digitado 5 como primeiro número, 2 como segundo número, * como operação.

**Importante**

- Escolha bem os nomes das suas variáveis.
- Lembre-se que você pode ter blocos dentro de outros blocos, ou seja, você pode ter ifs dentro de um while, pode ter while dentro de um while e assim por diante.
- Resolva o desafio por partes, ou seja, primeiro crie a estrutura mais básica para a leitura dos números, sem fazer as verificações. Teste a estrutura e só então faça as modificações necessárias para que, por exemplo, a leitura do primeiro número seja solicitada novamente caso não seja digitada uma string com caracteres numéricos.
- Teste o seu código MUITAS vezes antes de entregar!

**Prazo de entrega**

Conforme as instruções, o desafio deverá ser entregue antes da 6a aula. Nossa 6a aula ocorrerá no dia 03/03 às 19:00, então o prazo limite para entrega é até 19:00 do dia 03/03. Todas as informações sobre entrega estão neste repositório do GitHub onde vocês consultam os resumos das aulas.

**IMPORTANTE**

Não deixe de entregar! Se não conseguir fazer funcionar 100%, entregue o que você fez, tente atingir pelo menos 75%. Para mim, é muito mais importante que você tente fazer, tire dúvidas, discuta com seus colegas, se esforce, etc. do que entregar um código funcionando 100%, beleza? 💜

**Aquela colher de chá...***

Seu código tem que fazer algo assim (ou parecido com isso) acontecer:

<img src="desafio01.gif">
