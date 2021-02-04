# Resumo da Aula 03

Na nossa terceira aula, falamos sobre os seguintes assuntos:
- Operações com o Python.
- Melhorando nossa saída de dados com o print().
- Concatenação de strings.
- Método len().
- Pegando um caractere da string.
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

## Método len()

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
```

## Pegando um caractere da string

Vamos entender como é numerada a posição de cada caractere na string.

```python
advice = "FICA EM CASA"
```

Cada caractere - incluindo os espaços - ocupa uma posição cuja numeração começa do ZERO e não do UM.

| F | I | C | A |   | E | M |   | C | A | S  | A  |
|:-:|---|---|:-:|---|---|---|---|---|---|----|----|
| 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 | 11 |

Portanto, se eu quiser pegar o primeiro caractere dessa string - que é a letra "F" - basta utilizar o seguinte comando:

```python
first_char = advice[0]
```

Estamos dizendo para o Python pegar o caractere na posição zero! Se fizermos o print do que foi salvo na variável *first_char*, teremos a letra "F".

## Fatiamento de string

Suponha que no meu cadastro de usuários o campo "celular" foi preenchido por padrão da seguinte maneira: *+55(21)999999999**. Como eu faço se eu quiser exibir somente a parte *(21)999999999*?

Podemos fazer isso "fatiando" a string! Mas antes, vamos lembrar de como numerar cada caractere da string:

| + | 5 | 5 | ( | 2 | 1 | ) | 9 | 9 | 9 | 9  | 9  | 9  | 9  | 9  | 9  |
|:-:|---|---|:-:|---|---|---|---|---|---|----|----|----|----|----|----|
| 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 | 11 | 12 | 13 | 14 | 15 |

Precisamos "fatiar" a string começando da posição 3 e terminando **depois** da posição 15, uma vez que queremos que o **primeiro (** e o **último 9** estejam contidos no resultado.

```python
mobile = "+55(21)999999999"
print(mobile[3:16])     # imprime (21)999999999 na tela
```

Quando fazemos isso, estamos dizendo "Python, pega a string mobile e corta o pedaço que vai do 3 até o 16, beleza?". 

No comando, escrevemos 16 porque o caractere que ocupa a posição 15 deve estar incluso.

## Métodos de string: isnumeric(), isalpha(), isalnum() e isupper()

**isnumeric()**

Retorna True se a string possuir somente os caracteres numéricos de 0 a 9 e retorna False se a string possuir qualquer outra coisa.

```python
print("1234".isnumeric())   # True
print("abcd".isnumeric())   # False
print("ab12".isnumeric())   # False
print("123!".isnumeric())   # False
```

**isalpha()**

Retorna True se a string possuir somente os caracteres abcdefghijklmnopqrstuvwxyz (maiúsculos ou minúsculos) e retorna False se a string possuir qualquer outra coisa.

```python
print("1234".isalpha())   # False
print("abcd".isalpha())   # True
print("ab12".isalpha())   # False
print("123!".isalpha())   # False
```

**isalnum()**

Retorna True se a string possuir os caracteres de 0 a 9 e os caracteres abcdefghijklmnopqrstuvwxyz (maiúsculos ou minúsculos) e retorna False se a string possuir qualquer outra coisa como espaços e caracteres especiais.

```python
print("1234".isalnum())   # True
print("abcd".isalnum())   # True
print("ab12".isalnum())   # True
print("123!".isalnum())   # False
print("a_23".isalnum())   # False
```

**isupper()**

Retorna True se as letras da string forem maiúsculas e False se forem minúsculas.

```python
print("1234".isupper())   # False
print("ABcD".isupper())   # False
print("AB12".isupper())   # True
print("123!".isupper())   # False
print("A_23".isupper())   # True
```

### Exercício

Escreva um programa que verifique o nível de segurança da senha digitada por uma pessoa de acordo com as seguintes regras:
- A senha deverá ter exatamente 5 caracteres;
