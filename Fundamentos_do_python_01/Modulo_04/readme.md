# Funções

Quando quiser que alguns dados sejam impressos no console, use `print()`. Quando você quiser ler o valor de uma variável, use `input()`, juntamente com `int()` ou `float()`.

Você também fez uso de alguns métodos, que são de fato funções, mas declarados de uma forma muito específica.

Muitas vezes acontece que um determinado código é **repetido várias vezes no programa**. 
É repetido literalmente ou com apenas algumas pequenas modificações, consistindo no uso de outras variáveis no mesmo algoritmo. 
Também acontece que um programador não resiste à simplificação do trabalho e começa a clonar esses pedaços de código usando as operações de transferência e copiar e colar.

Podemos agora definir a primeira condição que pode ajudá-lo a decidir quando começar a escrever suas próprias 
funções: **se um fragmento específico do código começar a aparecer em mais de um lugar, considere a possibilidade de isolá-lo na 
forma de uma função** chamada de os pontos onde o código original foi colocado antes.

Pode ser que o algoritmo que você vai implementar seja tão complexo que seu código comece a crescer de forma descontrolada, e de repente você percebe que não consegue mais navegar com facilidade.

Um desenvolvedor bom e atento **divide o código** (ou, mais precisamente: o problema) em partes bem isoladas e **codifica cada uma delas na forma de uma função**.

  * Isso simplifica consideravelmente o trabalho do programa, porque cada código pode ser codificado separadamente e testado separadamente. O processo descrito aqui é chamado de **decomposição**.
  * Podemos agora declarar a segunda condição: **se um código se tornar tão grande que a leitura e o subestimação podem causar um problema, divida-o em problemas menores e separados e implemente cada um deles na forma de uma função separada**.
  * Essa decomposição continua até que você obtenha um conjunto de funções curtas, fáceis de entender e testar.

### DECOMPOSIÇÃO

Muitas vezes acontece que o problema é tão grande e complexo que não pode ser atribuído a um único desenvolvedor, 
e uma **equipe de desenvolvedores** precisa trabalhar nisso. O problema deve ser dividido entre vários desenvolvedores de forma a garantir uma cooperação eficiente e perfeita.

Esse tipo de decomposição tem uma finalidade diferente da descrita anteriormente - não se trata apenas de **compartilhar o trabalho**, mas também de **compartilhar a responsabilidade** entre muitos desenvolvedores.

Isso nos leva diretamente à terceira condição: se você vai dividir o trabalho entre vários programadores, decomponha o problema para permitir que o produto seja 
implementado como um conjunto de funções escritas separadamente, reunidas em módulos diferentes.

---------------------------------------------------------------------------

## Resumo da seção
 
1. Uma **função** é um bloco de código que executa uma tarefa específica quando a função é chamada (chamada). Você pode usar funções para tornar seu código reutilizável, melhor organizado e mais legível. As funções podem ter parâmetros e valores de retorno.

2. Há pelo menos quatro tipos básicos de funções no Python:
 * **incorporadas** que são parte integrante do Python (como a função de print()). Você pode ver uma lista completa das funções integradas do Python em https://docs.python.org/3/library/functions.html.
 * os que vêm de módulos **pré-instalados** (você aprenderá sobre eles no curso Fundamentos do Python 2)
 * **funções definidas** pelo usuário que são escritas pelos usuários para os usuários - você pode escrever suas próprias funções e usá-las livremente no código,
as funções lambda (você aprenderá sobre elas no curso Fundamentos do Python 2.)

3. Você pode definir sua própria função usando a palavra-chave def e a seguinte sintaxe:

```
def your_function(optional parameters):
    # o corpo da função
```

<br>

```
def hello(name):    # definindo uma função
    print("Olá,", name)    # o corpo da função
 
 
name = input("Entre um valor: ")
 
hello(name)    # chamando a função
 
```
 
## Funções parametrizadas

O poder total da função se revela quando pode ser equipado com uma interface capaz de aceitar dados fornecidos pelo invocador. 
Esses dados podem modificar o comportamento da função, tornando-a mais flexível e adaptável às condições variáveis.

Um parâmetro é na verdade uma variável, mas há dois fatores importantes que tornam os parâmetros diferentes e especiais:

 * **parâmetros existem apenas dentro de funções nas quais eles foram definidos**, e o único lugar onde o parâmetro pode ser definido é um espaço entre um par de parênteses na declaração def;
 * **a atribuição de um valor ao parâmetro é feita no momento da chamada da função**, especificando o argumento correspondente.

Uma função pode ter quantos parâmetros você quiser, mas quanto mais parâmetros tiver, mais difícil será memorizar suas funções e propósitos.

Vamos modificar a função - ela tem dois parâmetros agora:
```
def message(what, number):
    print("Entrar", what, "número", number)
```

## Funções de Exemplo: avaliando o IMC

imc = (Peso em Kg) / (Altura em Metros) ** 2

```
def bmi(peso, altura):
  return altura / peso ** 2
print(bmi(100, 1.84))

```

### Funções de exemplo: triângulos

2L x B
```
def is_a_triangle(a, b, c):
  if a + b <= c:
  return False
  if b + c <= a:
  return False
  if c + a <= b:
  return False
  return True

print(is_a_triangle(1, 1, 1))
print(is_a_triangle(1, 1, 3))
```
--------------- or --------

```
def is_a_triangle(a, b, c):
  if a + b <= or b + c <= a or c + a <= b:
    return False
  return True

print(is_a_triangle(1, 1, 1))
print(is_a_triangle(1, 1, 3))

```

### Teorema Pitágoras
```
def is_a_triangle(a, b, c):
 return a + b > c and b + c > a and c + a > b


a = float(input('Digite o primeiro lado\'s comprimento: '))
b = float(input('Entre no segundo lado\'s comprimento: '))
c = float(input('Entre no terceiro lado\'s comprimento: '))

if is_a_triangle(a, b, c):
 print('Sim, pode ser um triângulo.')
else:
 print('Não, não pode ser um triângulo.')

```


`c² = a² + b²`

**A Hipotenusa e o lado mais longo**.

```
def is_a_triangle(a, b, c):
    return a + b > c and b + c > a and c + a > b
 
 
def is_a_right_triangle(a, b, c):
    if not is_a_triangle(a, b, c):
        return False
    if c > a and c > b:
        return c ** 2 == a ** 2 + b ** 2
    if a > b and a > c:
    if a > b and a > c:
        return a ** 2 == b ** 2 + c ** 2
print(is_a_right_triangle(5, 3, 4))
print(is_a_right_triangle(1, 3, 4))


```

### Factorial

```
def factorial_function(n):
  if n < 0:
    return None
  if n < 2:
    return 1

  product = 1
  for i in range(2, n + 1):
    product *= i
  return product

for n in range(1, 6):
  print(n, factorial_function(n))
```

### Fibonacci
```
def fib(n):
    if n < 1:
        return None
    if n < 3:
        return 1
 
    elem_1 = elem_2 = 1
    the_sum = 0
    for i in range(3, n + 1):
        the_sum = elem_1 + elem_2
        elem_1, elem_2 = elem_2, the_sum
    return the_sum
 
 
for n in range(1, 10):  # testando
    print(n, "->", fib(n))

```

### 2° Versão

```
def fib(n):
    if n < 1:
        return None
    if n < 3:
        return 1
    return fib(n - 1) + fib(n - 2)
 
```

---------------------------------
```
def factorial_function(n):
  if n < 0:
    return None
  if n < 2:
    return 1
  return n * factorial_function(n-1)

```

