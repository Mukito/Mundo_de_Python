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
 
