# Resumão da Aula 01

Na nossa primeira aula, falamos sobre os seguintes assuntos:
- Comando print().
- Comando input().
- Comentários no código.
- Variáveis.

Para acessar o Repl desta aula, clique [aqui](https://repl.it/@ProgParaTodes/PeacefulUnacceptableSeptagon#main.py).

## Comando print()

Serve para exibir informações no console.

Podemos passar um texto (string) diretamente:

```python
print("Hello World")
```
Nesse caso a saída será:
```python
Hello World
```
Ou, podemos passar uma variável:
```python
um_texto = "Algum outro texto"
print(um_texto)
```
E, nesse caso, a saída será:
```python
Algum outro texto
```

## Comando input()

Serve para obter informações inseridas através do console.

Precisamos salvar o conteúdo digitado pelo usuário em algum "lugar", ou seja, em uma variável, caso contrário, o conteúdo simplesmente perderá.

Vamos pedir que o usuário digite seu nome e salvaremos em uma variável chamada **nome**.
Para verificar o conteúdo salvo na variável, utilizaremos o print().

```python
nome = input("Digite seu nome: ")
print(nome)
```
Então, ao rodar esse código, se eu digitar **Erika Bueno**, o resultado exibido na tela será:
```python
Erika Bueno
```

Se não atrelarmos o input() a uma variável, o conteúdo digitado pelo usuário não ficará acessível no decorrer da execução do código.

## Comentários no código

Podemos deixar anotações, lembretes e até explicações no nosso código. Fazemos isso utilizando comentários. 

Linhas comentadas são **ignoradas** pelo interpretador do Python. Para comentar uma linha, utilize a **#** na frente dela.

Vejamos um exemplo de código com comentário:

```python
# serve para obter dados digitados pela pessoa
cidade = input("Digite sua cidade: ")
```
A linha **# serve para obter dados digitados pela pessoa** é totalmente ignorada!

## Variáveis

Ao longo da execução do nosso código, precisamos guardar informações. E, para fazer isso, utilizamos as variáveis. 

Uma variável é um espaço na memória do computador e esse espaço tem um endereço único.

Não é possível guardar duas variáveis no mesmo endereço.

Quando criamos uma variável, precisamos dar a ela um nome - existem regras para esse nome, que veremos mais para frente - e um valor.

```python
email = "programacaoparatodes@gmail.com"
```

A palavra **email** é o nome da variável que, neste exemplo, recebe como valor a string **programacaoparatodes@gmail.com**.

Se tivermos executarmos o seguinte código:
```python
email = "programacaoparatodes@gmail.com"
email = "novo_email@provedor.com"
print(email)
```
O resultado exibido na tela será:
```python
novo_email@provedor.com
```
Isso ocorre porque, ao fazermos uma nova atribuição de valor à variável, o novo valor sobrescreve o antigo.

Temos alguns tipos de variáveis no Python:
- String (str) -> Textos
- Inteiro (int) -> Números inteiros
- Ponto flutuante (float) -> Números decimais
- Complexo (complex) -> Números complexos
- Booleano (bool) -> Verdadeiro ou falso

Exemplos:
```python
mensagem = "Olá, tudo bem?"
idade = 37
media = 9.75
numero_complexo = 4+5j 
tem_animal_de_estimacao = True 
```

**Observações importantes:**

- Quando criamos uma variável no Python, nós **não** precisamos informar seu tipo. Porém, é necessário ser coerente ao longo da escrita do código. Uma variável criada a partir da atribuição de uma string será do tipo string. Não podemos tentar, por exemplo, somar uma variável do tipo inteiro!
- Utilizaremos o snake_case para as nossas variáveis. Ou seja: elas começarão com letras minúsculas e o espaçamento entre as palavras, quando houver mais de uma, será feito com traço baixo (_).
- Nomes de variáveis podem começar com letras ou traço baixo. Os nomes podem ser acentuados (mas não faremos isso!), podem conter letras maiúsculas e minúsculas e também números. Os nomes de variáveis são sensíveis à letras maiúsculas e minúsculas.

Exemplos de nomes válidos para variáveis:

```python
nome = "Erika"
Nome = "Erika"                       
_nome = "Erika"         
nome_de_usuario = "erikacb"
```

**Importante:** a variável *nome* é diferente da variável *Nome*, hein!

# Exercício

Veja o código a seguir:

```python
input("Digite o CPF para iniciar: ")
input("Nome completo: ")
input("Qual é sua profissão? ")
print(cpf)
print(nome)
print(profissaodousuario)
```

**Não** execute esse código! Apenas analise e responda:

(1) O que você acha que vai acontecer quando o interpretador do Python tentar executar a linha do primeiro print? Por que você acha que isso acontecerá?

(2) Como você corrigiria o problema relatado na pergunta anterior?

(3) Reescreva o código da maneira que você acha mais correta.
