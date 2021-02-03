# Resumo da Aula 03

Na nossa terceira aula, falamos sobre os seguintes assuntos:
- Operações com o Python.
- Melhorando nossa saída de dados com o print().
- Concatenação de strings.
- Método len().
- Fatiamento de strings.
- Métodos de string: isnumeric(), isalpha(), isalnum() e isupper().

Para acessar os Repls desta aula, clique [aqui](https://repl.it/@ProgParaTodes/TraumaticLastingMatch#main.py) e [aqui](https://repl.it/@ProgParaTodes/DarkturquoiseWetCommunication#main.py).

## Operações com o Python

Vimos que o Python pode fazer contas:

```python
a = 5
b = 6

# soma
print(a + b) 

# subtração
print(a - b)
print(b - a) 

# multiplicação
print(a * b) 

# divisão
print(a / b)

# potenciação
# a elevado a b
print(a ** b)
# b elevado a a
print(b ** a)

# resto da divisão inteira
# 6 dividido por 5 dá resto 1
print(b % a)
```

**O que acontece se você dividir algum número por zero? Experimente fazer isso no Repl! ;)**

Você também pode utilizar parênteses para mudar a precedência das operações, por exemplo:

```python
(5 + 6) * 4
```

É diferente de:
```python
5 + 6 * 4
```

## Melhorando nossa saída de dados com o print()

Na aula, utilizamos o comando print() com alguns marcadores para *encaixar* os valores das variáveis na nossa saída de dados.

| Marcador |       Tipo       |
|:--------:|:----------------:|
|    %d    | Números inteiros |
|    %s    |      Strings     |
|    %f    | Números decimais |

Vamos pensar no seguinte exercício:

*Escreva um programa que pergunte ao usuário o nome e a idade, em seguida, escreva " _ _ _ _ tem _ _ anos" onde o primeiro espaço deverá trazer o nome e o segundo espaço a idade.*

Com a utilização de marcadores, a resolução fica assim:

```python
name = input("Digite seu nome: ")
age = int(input("Digite sua idade: "))
print("%s tem %d anos" % (name, age))
```

Estamos mostrando uma string na tela composta por uma variável (string) + texto + outra variável (inteiro) + texto. Essas variáveis estão representadas no comando *print* pelos marcadores *%s* e *%d* e que correspondem **respectivamente** às variáveis *name* e *age*. Precisamos colocar o *%* depois da string completa e, em seguida, precisamos colocar as variáveis depois dele. No exemplo, temos dois marcadores e duas variáveis, então foi necessário colocá-las entre parênteses: *(name, age)*. Se for apenas um marcador e uma variável, não é necessário colocar entre parênteses. 

Também podemos utilizar o marcador *%f* para formatar a exibição das casas decimais de um float. Veja no exemplo a seguir:

```python
grade1 = 7.75
grade2 = 8.0
grade3 = 6.35

average = (grade1 + grade2 + grade3)/3

print("Média SEM formatação de casas decimais: %f" % average)   # mostra 7.366667
print("Média COM formatação de casas decimais: %.2f" % average) # mostra 7.37
```

Veja que ao mostrar a média com a formatação de casas decimais, mudamos o marcador *%f* para *%.2f*. Isso quer dizer que estamos pedindo que o Python exiba somente duas casas decimais.

## Concatenação de strings

Podemos concatenar strings... Ou seja, podemos 'somar' e 'multiplicar' strings! 

```python
string1 = "ABC"
string2 = "DEF"

print(string1 + string) # exibe ABCDEF na tela

string = "Ai"
print(string*10) # exibe AiAiAiAiAiAiAiAiAiAi na tela
```

Combinando as duas coisas...

```python
hello = "Oi"
print((hello + "!\n")*3)

# exibe na tela
# Oi!
# Oi!
# Oi!
```

**Atenção:** Colocamos *hello + "!\n"* entre parênteses para que o "pacote" todo *Hello!* seja multiplicado 3x e pulando linha por causa do \n.

### Método len()

Como podemos descobrir o número de caracteres de uma string?

```python
big = "pneumoultramicroscopicossilicovulcanoconiótico"
size = len(big)
print(size) # mostra o número 46 na tela
```

O comando len() conta o número de caracteres incluindo os espaços, portanto...

```python
chokito1 = "Leite condensado, caramelizado com flocos crocantes e coberto com o delicioso chocolate Nestlé"
chokito1_size = len(chokito1)
print("Tamanho com espaços:", chokito1_size) # 94 caracteres

chokito2 = "Leitecondensado,caramelizadocomflocoscrocantesecobertocomodeliciosochocolateNestlé"
chokito2_size = len(chokito2)
print("Tamanho sem espaços:", chokito2_size) # 82 caracteres
