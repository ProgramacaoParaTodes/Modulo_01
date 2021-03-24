# Aula 07

Na nossa sétima aula, falamos sobre os seguintes assuntos:

- Funções.

Para acessar os Repls dessa aula, clique [aqui](https://repl.it/@ProgParaTodes/PhonyBadDrawings#main.py), [aqui](https://repl.it/@ProgParaTodes/AnotherLightgreenMicrobsd#main.py), [aqui](https://repl.it/@ProgParaTodes/ZanyOpaqueDiscussion#main.py) e [aqui](https://repl.it/@ProgParaTodes/FrightenedDarkredProcedure#main.py).

🔴 Atualização - Repls referentes a parte de Tuplas: [aqui](https://replit.com/@ProgParaTodes/PaltryThankfulActivecontent#main.py), [aqui](https://replit.com/@ProgParaTodes/StarchyButteryAdmins#main.py) e [aqui](https://replit.com/@ProgParaTodes/KlutzyAcademicOctagons#main.py). 🔴

## Funções

Na última aula, aprendemos que podemos encapsular um bloco de código de modo que possamos reaproveitá-lo em outras partes do programa. Fazemos isso criando **funções**.

**Criando uma função**

Primeiro precisamos *declarar* a função. Colocamos as funções no início do nosso código porque, quando precisarmos utilizá-las, elas já estarão declaradas e **acessíveis**. 

```python
def nome_da_funcao():
    # tudo o que a 
    # função vai fazer
```

Toda função começa com a palavra reservada **def** seguida do **nome** que ela terá e **parênteses**.

Então, se quisermos declarar uma função que o único objetivo é mostrar "Bom dia!" na tela do interpretador, podemos fazer da seguinte maneira:

```python
def diga_bom_dia():
    print("Bom dia!")
```

Quando quisermos utilizar essa função, ou seja, quando quisermos **chamar a função**, basta escrever:

```python
diga_bom_dia()
```
**Atenção:** Parênteses vazios na declaração da função significa que ela não recebe argumentos.

**Funções com argumentos**

Vejamos o código a seguir:

```python
def validar(email):
  achou_arroba = False
  achou_ponto = False
  
  for letra in email:
    if letra == "@":
      achou_arroba = True
    if letra == ".":
      achou_ponto = True

  if achou_arroba == True and achou_ponto == True:
    print("E-mail válido")
  else:
    print("E-mail inválido")

validar("programacaoparatodes@gmail.com")

validar("emailerrado@blabla")
```

Temos uma função chamada *validar*. Repare que aqui o nome da função é seguido de parênteses e, dentro deles, temos a palavra *email*.

Isso significa que essa função possui um **argumento** que deverá ser **passado** quando ela for **chamada**.

Em outras palavras, quando quisermos utilizar essa função, não podemos simplesmente chamá-la escrevendo *validar()* porque ela **espera** que um argumento seja passado. Se chamarmos a função sem o argumento que ela espera, o código quebra! :(

Quando chamamos a função, colocamos entre parênteses o valor que deverá *ocupar* o lugar do argumento. 

Veja que utilizamos a função duas vezes nesse exemplo. 

Na 1a. utilização, chamamos a função *validar* passando a string *programacaoparatodes@gmail.com* como argumento. 

O resultado esperado é que apareça na tela a frase "E-mail válido".

Na 2a. utilização, chamamos a função *validar* passando a string *emailerrado@blabla* como argumento. 

O resultado esperado é que apareça na tela a frase "E-mail inválido".

Mas como isso aconteceu?

Quando chamamos a função e passamos um valor dentro dos parênteses, esse valor assume o lugar do argumento. Na declaração da função, o "nome" do argumento é *email*. 

Quando chamamos a função pela 1a. vez nesse código, o argumento *email* lá da declaração da função é substituido por "programacaoparatodes@gmail.com". 

Em outras palavras, quando a linha *validar("programacaoparatodes@gmail.com")* é executada, **dentro da função**, em todos os pontos onde pudermos ler *email*, é como se estivessemos lendo "programacaoparatodes@gmail.com". 

Vamos utilizar um exemplo mais enfático para perceber como isso funciona:

```python
def teste(banana):
  print("Vou imprimir o argumento aqui ó: %s" % banana)

teste("Meu argumento :)")
```

O resultado desse código meio nonsense é mostrar na tela "Vou imprimir o argumento aqui ó: Meu argumento :)".

Se o meu argumento é *banana*, todas as vezes que *banana* aparecer dentro do código da função significa que estou fazendo referência ao argumento. 

**Atenção:** Em funções com dois ou mais argumentos, devemos passá-los na mesma ordem em que foram colocados na definição da função. 

**Retornando valores**

Uma função pode simplesmente executar alguns comandos ou pode, além de executar comandos, **retornar um valor**.

Os exemplos vistos até agora são de funções que **não** retornam valores.

Vejamos o exemplo a seguir:

```python
def gerar_senha(nome, nascimento):
  parte1 = nome[0:3]
  parte2 = nascimento[6:10]
  return parte1 + parte2

senha = gerar_senha("Erika", "04/05/1983")

print(senha)      # mostra Eri1983
```

Analisando o código, temos uma novidade na função: a palavra **return**.

O objetivo dessa palavra no código da função é enviar "para fora" o valor que está à sua direita.

No caso do exemplo, a função **gerar_senha** recebe 2 argumentos (nome e nascimento no formato dd/mm/aaaa). 

Dentro da função, a variável *parte1* recebe as três primeiras letras do nome e a variável *parte2* recebe o ano de nascimento. 

Na última linha da função, temos o *return* seguido da concatenação das strings *parte1* e *parte2*. Ou seja, a função **retorna** uma string unindo essas duas informações.

Esse **retorno da função** é automaticamente salvo na variável *senha*.

Então, quando a linha *print(senha)* é executada, ela mostra *Eri1983*.

***Variável local x variável global***

Você deve ter reparado no código acima que dentro da função temos duas variáveis: *parte1* e *parte2*. Elas são **variáveis locais** porque existem somente **dentro** da função e **não podem** ser acessadas do lado de fora.

Depois que a última linha da função é executada, ou seja, quando ocorre o *return parte1 + parte2*, o valor dessa concatenação de strings é salvo na variável *senha* e as variáveis *parte1* e *parte2* "cumpriram seu papel".

Se tentarmos acessar essas variáveis, por exemplo, fazendo *print(parte1)* e/ou *print(parte2)* **fora** da função, o código quebra!

Já a variável *senha* pode ser acessada de qualquer ponto do código. Isso faz com que ela seja uma **variável global**.

Veja mais um exemplo para fixar o conceito:

```python
def adicao(x, y):
  soma = x + y
  print("Soma dentro da função: %d" % soma) # Soma dentro da função: 9
  return soma

resultado = adicao(4, 5)

print("Resultado: %d" % resultado)          # mostra Resultado: 9
print("Soma fora da função: %d" % soma)     # quebra
```

Aqui temos uma função **adicao** que recebe dois argumentos, que são os números que serão somados dentro dela. 

Ela também tem um retorno, ou seja, como atribuímos a função à variável *resultado*, ela retornará o valor da soma justamente para essa variável.

Note que dentro da função há uma variável chamada *soma*. Ela recebe *x + y* e depois é retornada na última linha de execução da função.

Dentro da função podemos utilizar essa variável tranquilamente para fazer o print que mostra na tela a informação *Soma dentro da função: 9*.

Do lado de fora da função, podemos utilizar o print para verificar o valor da variável *resultado*. Isso mostrará na tela *Resultado: 9*.

Porém, também do lado de fora da função, quando tentamos utilizar o print com a variável *soma*, **não** teremos sucesso. O código quebra! 

**Atenção:** Precisamos ter muito cuidado na utilização das variáveis. Não tente acessar variáveis locais fora da função! 

**Funções com atributos opcionais**

Até o momento, vimos duas possíveis situações para as funções: elas não terem argumentos e elas terem argumentos obrigatórios.

Existe a possibilidade de termos argumentos opcionais em uma função. Vejamos o exemplo a seguir:

```python
def cadastrar_contato(telefone, ddd="21"):
  completo = "(" + ddd + ") " + telefone
  return completo

tel_RJ = cadastrar_contato("99999-1234")
print(tel_RJ)     # mostra (21) 99999-1234

tel_SP = cadastrar_contato("99999-5678", "11")
print(tel_SP)     # mostra (11) 99999-5678
```

Temos uma função que recebe dois argumentos: *telefone* e *ddd*. Logo na definição da função, percebemos algo diferente: o argumento ddd já está com um valor.

Isso quer dizer que, ao chamarmos a função, se **não** passarmos um valor para *ddd*, ele vai assumir o valor que está pré-definido ali. Mas, se passarmos um valor para *ddd*, então será utilizado o valor que passarmos.

A variável *tel_RJ* recebe o retorno da função *cadastrar_contato("99999-1234")*. Não foi passado um valor para o *ddd*. Quando a linha *print(tel_RJ)* é executada, o valor "(21) 99999-1234" é mostrado.

Já a variável *tel_SP* recebe o retorno da função *tel_SP = cadastrar_contato("99999-5678", "11")*. Aqui está sendo passado o valor "11" para o *ddd*, então quando a linha *print(tel_SP)* é executada, o valor "(11) 99999-5678" é mostrado.

**Atenção:** Os argumentos obrigatórios devem vir primeiro na declaração da função.

## Tuplas

A maneira mais simples de definir o que são as tuplas é dizendo que são como as listas, porém, são imutáveis.

Uma vez que definimos uma tupla, **não** podemos mais adicionar, editar nem remover seus elementos.

Podemos utilizar os mesmos métodos que utilizamos para listas, como por exemplo, o *len()*. Mas **não** podemos utilizar o *append()* uma vez que esse é um método para alterar uma lista.

Veja o exemplo de uma tupla:

```python
meses = ("Janeiro", "Fevereiro", "Março", "Abril", "Maio", "Junho", "Julho", "Agosto", "Setembro", "Outubro", "Novembro", "Dezembro")
```

Repare que, diferente das listas, as tuplas utilizam parênteses. 

Por que definir uma tupla de meses e não uma lista? É simples! Os meses do ano são sempre os mesmos. Então, por que eu deveria utilizar uma estrutura de dado que permitisse alterações? 

A organização dos elementos dentro da tupla também segue a lógica das listas: o primeiro elemento ocupa a posição 0, o segundo ocupa a posição 1 e assim sucessivamente.

Veja o exemplo a seguir:

```python
def nome_do_mes(mes):
  meses = ("Janeiro", "Fevereiro", "Março", "Abril", "Maio", "Junho", "Julho", "Agosto", "Setembro", "Outubro", "Novembro", "Dezembro")
  mes = mes - 1
  return meses[mes]

mes = nome_do_mes(5)
print(mes)                    # mostra Maio

outro_mes = nome_do_mes(8)
print(outro_mes)              # mostra Agosto
```

Neste exemplo, temos uma função que recebe o número do mês e retorna seu nome. 

Se quisessemos obter o nome do mês 1, que é janeiro, precisaríamos chamar a função *nome_do_mes* passando o número 1 como argumento. 

Internamente, "Janeiro" ocupa a posição 0 da tupla *meses*. Por esse motivo, para acessarmos esse valor, precisamos tirar 1 unidade do valor passado através do argumento *mes*. 

Se não fizéssemos isso, ao chamar a função *nome_do_mes(1)*, o resultado seria "Fevereiro", que é o valor residente na posição 1 da tupla.

Nós também podemos utilizar as tuplas para retornar valores numa função. Veja:

```python
meses = ("Janeiro", "Fevereiro", "Março", "Abril", "Maio", "Junho", "Julho", "Agosto", "Setembro", "Outubro", "Novembro", "Dezembro")

def fatiar(data):
  dia = int(data[0:2])
  mes = int(data[3:5])
  ano = int(data[6:10])
  return (dia, mes, ano, meses[mes-1])

info = fatiar("04/05/1983")

print(info)   # mostra (4, 5, 1983, 'Maio')

# mostra Você nasceu no dia 4 de Maio de 1983
print("Você nasceu no dia %d de %s de %d" % (info[0], info[3], info[2]))
```

Aqui, o retorno da função é uma tupla. Isso faz com que o retorno não possa ser alterado. Caso eu queira obter um novo retorno, devo chamar a função novamente passando outros argumentos.

A função do exemplo recebe uma data no formato dd/mm/aaaa e devolve ao usuário uma tupla contendo a data "fatiada" em dia, mês e ano e também o nome do mês.

O dia está na posição 0, o mês na posição 1, o ano na posição 2 e o nome do mês na posição 3.

Quando fazemos *print(info)*, a tupla é mostrada na tela de maneira bem semelhante à lista só que com parênteses.

E quando fazemos *print("Você nasceu no dia %d de %s de %d" % (info[0], info[3], info[2]))*, três dos quatro valores da tupla são acessados para montar a frase.

### Exercício

Escreva um programa para digitar nomes de alunos em uma lista. O programa deverá pedir a quantidade de alunos que você deseja inserir o nome nessa lista. Através obrigatoriamente de uma função, os nomes deverão ser validados antes de serem adicionados à lista. 
Essa função deverá verificar: 
- Se o nome digitado contém algum número (que seria um erro de digitação, por exemplo). 
- Se o nome digitado não está "vazio" (o digitador pressionou Enter sem digitar alguma coisa). 

Se o nome digitado for válido, a função deverá retornar True e se for inválido, False. 
Você deverá obrigatoriamente utilizar esse resultado para definir se o nome será inserido na lista ou não.
