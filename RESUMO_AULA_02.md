# Resumo da Aula 02

Na nossa segunda aula, falamos sobre os seguintes assuntos:
- Conversões com int(), float() e str().
- Operadores Relacionais e Lógicos.
- Estruturas condicionais.

Para acessar os Repls desta aula, clique [aqui](https://repl.it/@ProgParaTodes/KindBigheartedTwintext#main.py) e [aqui](https://repl.it/@ProgParaTodes/TerribleAmusedCrypto#main.py).

## Conversões com int(), float() e str()

Podemos converter um tipo de variável em outro desde que faça sentido, por exemplo, quando uma idade - número inteiro - por algum motivo foi lida como uma string e precisamos utilizá-la como número inteiro.

```python
idade_string = "37"
idade = int(idade_string)
# Exemplo: com o valor inteiro de 37 na variável idade você pode fazer contas.

codigo_numerico = 9
codigo = str(codigo_numerico)
# Exemplo: passando o código numérico para uma string, você poderá concatenar com outras strings.

quantidade_do_pacote = 45
quantidade = float(quantidade_do_pacote)
# Exemplo: uma quantidade em gramas geralmente é um número decimal, ou seja, um float.
```
## Operadores Relacionais

Para podermos estudar estruturas condicionais para **tomada de decisão**, precisamos aprender os operadores relacionais e os operadores lógicos.

### Operadores relacionais

São aqueles famosos operadores que nós já conhecemos da matemática e que vamos utilizar para **comparar** valores.

**Atenção:** O resultado de uma comparação de valores é sempre **True** ou **False**.

| Operador |    Operação    | Símbolo matemático |
|:--------:|:--------------:|:------------------:|
|    ==    |    igualdade   |          =         |
|     >    |    maior que   |          >         |
|     <    |    menor que   |          <         |
|    !=    |    diferente   |          ≠         |
|    >=    | maior ou igual |          ≥         |
|    <=    | menor ou igual |          ≤         |

**Atenção:** Não confundir o operador **==** com o símbolo de atribuição **=**! 

Por exemplo, **3 == 4** significa que estamos **comparando** os números 3 e 4 (o resultado, neste caso, é False). 

E se fizermos **a = 3** e **b = 4** significa que estamos *atribuindo os valores* 3 e 4 às variáveis a e b respectivamente.

### Operadores lógicos

Quando fazemos comparações, podemos querer colocar mais condições. Para isso, utilizamos operadores lógicos.

| Operador Python | Operação |
|:---------------:|:--------:|
|       not       |    não   |
|       and       |     e    |
|        or       |    ou    |

Basicamente, o operador **not** é a **negação** de algo, o operador **and** é a **conjunção** e o operador **or** é a **disjunção**. Vamos ver isso em exemplos:

**not:** inverte o valor.

| Valor | not Valor |
|:-----:|:---------:|
|  True |   False   |
| False |    True   |

Você pode testar isso no interpretador:

```python
print(not True)     # imprime False
print(not False)    # imprime True
```

**and:** basta que um valor seja False para que as combinações de valores sejam False.

| Valor 1 | Valor 2 | Valor 1 and Valor 2 |
|:-------:|:-------:|:-------------------:|
|   True  |   True  |         True        |
|   True  |  False  |        False        |
|  False  |   True  |        False        |
|  False  |  False  |        False        |

Você pode testar isso no interpretador:

```python
print(True and True)    # imprime True
print(True and False)   # imprime False
print(False and True)   # imprime False
print(False and False)  # imprime False
```

**or:** basta que um dos valores seja True para que as combinações de valores sejam True.

| Valor 1 | Valor 2 | Valor 1 or Valor 2 |
|:-------:|:-------:|:------------------:|
|   True  |   True  |        True        |
|   True  |  False  |        True        |
|  False  |   True  |        True        |
|  False  |  False  |        False       |

```python
print(True or True)    # imprime True
print(True or False)   # imprime True
print(False or True)   # imprime True
print(False or False)  # imprime False
```

## Estruturas Condicionais

Na aula, vimos a estrutura condicional *if* acompanhada do *else*. Basicamente, quando precisamos avaliar uma condição para tomar uma decisão, utilizaremos essa estrutura.

Em português, temos algo do tipo:

    SE A CONDIÇÃO TESTADA FOR VERDADEIRA:
        FAÇA X
    CASO CONTRÁRIO:
        FAÇA Y

Em Python, teremos algo assim:

```python
idade = int(input("Digite sua idade: \n"))

if idade >= 18:
  print("Maior de idade")
else: 
  print("Menor de idade") 
```

**Obs.:** O \n pula linha ;)

Fazemos a leitura da idade que será salva na variável *idade* e em seguida fazemos a verificação da condição.

Aqui temos duas possibilidades ao avaliar a idade: ou a pessoa é maior de idade ou a pessoa é menor de idade, não existe uma terceira possibilidade.

Por isso, aqui a condição *if* acompanhada de *else* se encaixa perfeitamente.

Se a condição *idade >= 18* é verdadeira, o bloco de código executado é o imediatamente abaixo do *if* (atenção para a indentação). 

Se a condição *idade >= 18* é falsa, o bloco de código executado é o imediatamente abaixo do *else*.

**Atenção:** A indentação no Python é obrigatória e ajuda a limitar os blocos de código!

**Observação:** Existem situações que vamos utilizar somente o *if*. Por exemplo, quando um perfil é do tipo "Verificado" em alguma rede social como Instagram ou Twitter. Possivelmente, em algum lugar do código, existe uma verificação de algum atributo que indica se aquele perfil é verificado e isso não requer nenhum tipo de ação que se encaixaria no "caso contrário". O perfil verificado ganha um ícone específico enquanto o perfil não verificado permanece o mesmo. Então é como se houvesse uma variável lá dentro do código *verified_profile* que, tendo o valor True dentro dela faz com que seja exibido um ícone diferente para aquele usuário.

Existem casos em que temos mais de duas possibilidades na tomada de decisão. Vamos ver o exemplo a seguir.

Em português, podemos ter uma situação assim:

    SE A CONDIÇÃO 1 TESTADA FOR VERDADEIRA:
        FAÇA X
    CASO CONTRÁRIO, SE A CONDIÇÃO 2 FOR VERDADEIRA:
        FAÇA Y
    CASO CONTRÁRIO:
        FAÇA Z

Vamos traduzir isso para o Python com o exemplo a seguir:

```python
codigo_promo = int(input("Digite o código para saber o desconto: "))

if codigo_promo == 1:
    print("Desconto de 20%")
elif codigo_promo == 2: 
    print("Desconto de 35%")
else: 
    print("Desconto de 10%")
```

A primeira condição é codigo_promo ser igual a 1. Se o usuário digitar o número 2, esse teste falhará e a próxima condição a ser testada é codigo_promo ser igual a 2. 

A cada nova condição que desejamos testar, acrescentamos *elif* seguido da condição e, por fim, o *else*. Veja como o mesmo exemplo fica com mais condições:

```python
codigo_promo = int(input("Digite o código para saber o desconto: \n"))

if codigo_promo == 1:
    print("Desconto de 20%")
elif codigo_promo == 2: 
    print("Desconto de 35%")
elif codigo_promo == 3: 
    print("Desconto de 40%")
elif codigo_promo == 4:
    print("Desconto de 50%")
else: 
    print("Não há desconto para esse código.")
```

Em tomadas de decisão dentro do código, é importante pensarmos bem nas opções e também colocarmos alguma ação no *else* para contemplar casos que fujam das opções possíveis.

**Uma observação importante sobre *elif* e os operadores lógicos:** Podemos ter avaliações combinadas no *elif* com o *and* e com o *or*, sendo assim, precisamos escrever da seguinte maneira (veja o último *elif*):

```python
codigo_promo = int(input("Digite o código para saber o desconto: \n"))

if codigo_promo == 1:
    print("Desconto de 20%")
elif codigo_promo == 2: 
    print("Desconto de 35%")
elif codigo_promo == 3: 
    print("Desconto de 40%")
elif codigo_promo == 4 or codigo_promo == 19:
    print("Desconto de 50%")
else: 
    print("Não há desconto para esse código.")
```

# Exercício

Escreva um programa que peça para digitar a média e o número de faltas em uma determinada disciplina de um(a) estudante. O programa deverá 
exibir na tela:
- APROVADE se a média for igual ou maior que 7.0 e o número de faltas for inferior a 4.
- EM PROVA FINAL se a média estiver entre 4.0 e 6.9 e o número de faltas for inferior a 4.
- REPROVADE POR FALTA se o número de faltas for igual ou maior que 4.
- REPROVADE POR MÉDIA se a média estiver abaixo de 4.0.
- REPROVADE POR FALTA E MÉDIA se o número de faltas for igual ou maior que 4 e a média estiver abaixo de 4.0.
