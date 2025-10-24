## O que é pilha?
É uma estrutura desenvolvida para armazenar dados de maneira bastante específica.

Imagine uma pilha de moedas. 
Não é possível **colocar** uma nova moeda em nenhum lugar que não seja no **topo da pilha**.

De maneira parecida, não conseguimos **tirar** uma moeda da pilha, a não ser que seja do **topo da pilha**. 
Se quiser pegar a moeda que fica na parte de baixo, você terá que remover todas as moedas de cima dela.

O nome alternativo para uma pilha (somente em terminologia de TI) é **LIFO**
É uma abreviação do comportamento claro da pilha: 
***Last In – First Out*** (ou o "último a entrar é o primeiro a sair", em tradução livre). 
A moeda que chegou por último na pilha será a primeira a ser retirada.

<img width="542" height="546" alt="image" src="https://github.com/user-attachments/assets/ed95161d-f6ed-4b9f-acb0-e3d13b5a5aab" />


Uma pilha é um objeto com **duas operações elementares**, convencionalmente chamadas de 
***push*** (quando um novo elemento é **colocado no topo**) e ***pop*** (quando um elemento existente é **retirado do topo**).

As pilhas são usadas com frequência em diversos algoritmos clássicos, e é difícil imaginar a implementação de diversas ferramentas conhecidas sem o uso de pilhas.
Vamos implementar uma pilha no Python. 

Esta será uma pilha bastante simples e mostraremos como fazê-lo por meio de duas abordagens independentes: 
**procedural e objetiva**.

Vamos começar pela primeira.

### PROCEDURAL - Pilha
É necessário decidir como armazenar os valores que serão recebidos pela pilha. 
Sugerimos usar o método mais simples e usar uma lista para esta tarefa. 
Vamos presumir que o tamanho da pilha não é limitado de nenhuma maneira. 
Também iremos presumir que o último elemento da lista armazena o elemento no topo.

A pilha em si também já está criada:
```
stack = []
```

Estamos prontos para definir uma função que **coloca valores na pilha**. Estes são os pressupostos:

  * o nome da função é `push`;
  * a função recebe um parâmetro (este é o valor para ser colocado na pilha)
  * a função não retorna nada;
  * a função anexa o valor do parâmetro ao fim da pilha;
```
def push(val):
  stack.append(val)
```

Agora é hora de uma função **retirar valores da pilha**. Podemos fazer isso da seguinte maneira:

  * o nome da função é `pop`;
  * a função não recebe nenhum parâmetro;
  * a função retorna o valor retirado da pilha
  * a função lê o valor da parte superior da pilha e o remove.
```
def pop():
  val = stack[-1]
  del stack[-1]
  return val
```
**Observação**: a função não verifica se existe algum elemento na pilha.
Vamos juntar todas as peças para acionar a pilha. O programa completo faz o push de três números na pilha, 
os retira e imprime seus valores na tela. Podemos vê-lo no editor.

-------------------------------------------------------

### Procedual x OO
A pilha procedural está pronta. Logicamente, existem alguns pontos fracos; além disso, a implementação pode ser melhorada de várias maneiras 
(recomendamos usar exceções), mas em geral a pilha está totalmente implementada e pode ser usada se você desejar.

Mas quanto mais você usar, mais desvantagens você irá encontrar. Aqui estão algumas delas:

-   * a variável essencial (a lista de pilha) é altamente **vulnerável**; qualquer um pode modificá-la de maneira incontrolável,
      destruindo a pilha; isto não significa que será feito de maneira maliciosa, pelo contrário, ela pode acontecer devido a
      descuido; por exemplo, quando alguém confunde nomes de variáveis: imagine que você escreveu algo da seguinte maneira:
```
stack[0] = 0
```

-   * o funcionamento da pilha será completamente desorganizado;
-   * isso pode acontecer justamente quando mais precisar da pilha, será necessário criar outra lista para armazenamento da ilha,
      além de provavelmente outras funções `push` e `pop` também;
-   * pode também ser que você não precise apenas das funções `push` e `pop` , mas também de outras conveniências; você conseguiria implementá-las,
      mas tente imaginar o que aconteceria se você tivesse dezenas de pilhas implementadas separadamente.

A abordagem orientada por objeto oferece soluções para cada um desses problemas. Primeiramente, vamos aprender seus nomes:
  *   a capacidade de ocultar (proteger) valores selecionados contra acesso não autorizado é chamado de encapsulamento;
      os valores encapsulados **não podem ser acessados** ou **modificados** caso deseje usá-los de maneira exclusiva;

  *   quando uma classe estiver implementando todos os comportamentos de pilha necessários, você pode produzir quantas pilhas desejar;
      não é necessário copiar ou replicar qualquer parte do código;

  *   a capacidade de enriquecer a pilha com novas funções vem da herança; você pode criar uma nova classe (subclasse),
      que herda todas as características  existentes da superclasse, além de incluir algumas novas.


### Procedural vs Objetiva
Vamos criar uma nova implementação de pilha do zero. 
Desta vez, usaremos a abordagem por objetos, orientando passo a passo no mundo da programação orientada por objetos.

### Pilha - abordagem orientada a objetos
Usaremos uma lista como armazenamento da pilha. Apenas precisamos descobrir como colocar a lista na classe.

Vamos começar aprendendo como a pilha do objeto começa:
```
class Stack:
```
Esperamos que aconteça duas coisas:
  *  queremos que a classe tenha uma propriedade como o armazenamento da pilha – precisamos "**instalar**" uma lista dentro de
     cada objeto da classe (observação: cada objeto precisa ter sua própria lista e ela não pode ser compartilhada entre várias pilhas)
  *  em seguida, queremos que a lista seja oculta do usuário da classe.


Como fazer isso?

Em comparação com outras linguagens de programação, o Python não permite declarar uma propriedade dessa maneira.
Em vez disso, é necessário incluir uma declaração ou instrução específica. As propriedades devem ser incluídas na classe manualmente.

Como garantir que tal atividade ocorra toda vez que uma nova pilha é criada?

Existe uma maneira simples de fazer isso, precisamos equipar a classe com uma função específica sua especificidade é dupla:

  * ela precisa ser nomeada de maneira específica;
  * ele é chamado de maneira implícita quando o novo objeto é criado.

Tal função é chamada de **construtor** e seu propósito é **construir um novo objeto**. 
O construtor deve saber tudo sobre a estrutura do objeto, e deve realizar todas as inicializações necessárias.

Vamos incluir um construtor bastante simples na nova classe. Dê uma olhada no snippet:
```
class Stack:
  def __init__(self):
    print("Oi!")

stack_object = Stack()
```


e Agora:
  * O nome do construtor sempre será `__init__`;
  * Ele precisa ter pelo menos um parâmetro (falaremos sobre isso posteriormente); o parâmetro é usado para representar o objeto recém-criado,
    o parâmetro pode ser usado para manipular o objeto e para enriquecê-lo com as propriedades necessárias. Faremos uso disso em breve;
  * Obs: o parâmetro obrigatório geralmente é chamado `self` e é apenas uma **convenção**, mas você deve segui lo - pois ele simplifica o processo de leitura e compreensão do seu código.

```
class Stack: # Definindo a classe Stack.
  def __init__(self):   # Definindo a função contrutora.
    print("Oi!")

stack_object = Stack()  # Instanciando o objeto.
```

**Observação**: não existe nenhum rastro da chamada do construtor dentro do código. Ele foi chamado de maneira implícita e automática. Vamos usar isso agora.

Qualquer mudança feita dentro do construtor que modifique o estado do parâmetro `self` será refletido no objeto recém-criado.
Isto significa que você pode incluir qualquer propriedade no objeto e a propriedade permanecerá lá até que o 
objeto encerre sua vida útil ou que propriedade seja removida de maneira explícita.
Agora iremos **incluir apenas uma propriedade no novo objeto**, uma lista para a pilha. A chamaremos de `stack_list`


```
class Stack:
    def __init__(self):
        self.stack_list = []

stack_object = Stack()
print(len(stack_object.stack_list))
```

**Observação**:

  * Usamos **notação de ponto**, como na chamada de métodos; esta é a convenção geral para acessar as propriedades do objeto  será necessário nomear o objeto, inserir um ponto (`.`) logo após e especificar o nome desejado da propriedade; não use parênteses! Não é necessário chamar um método, você quer acessar uma propriedade;
  * se você configurar o valor de uma propriedade pela primeira vez (como no construtor), você estará criando essa propriedade; desse momento em diante, o objeto recebeu a propriedade e está pronto para usar seu valor;
  * fizemos algo a mais no código, tentamos acessar a propriedade `stack_list` da classe externa imediatamente após a criação do objeto; queremos verificar o comprimento atual da pilha. Será que tivemos sucesso nessa tarefa?

Isto não é o que queremos que a pilha faça. Preferimos que `stack_list` fique escondida do mundo exterior. Será que é possível?

Sim e é algo simples, mas não é bem intuitivo.

Dê uma olhada: incluímos dois sublinhados antes do nome de stack_list e nada mais:
```
class Stack:
    def __init__(self):
        self.__stack_list = []


stack_object = Stack()
print(len(stack_object.__stack_list))
```

A mudança invalida o programa.

O motivo?

Quando qualquer componente de classe possui um **nome que começa com dois sublinhados** (__), ele se torna **privado**, ou seja, ele pode ser acessado apenas a partir da própria classe.
Não é possível acessá-lo de fora. É dessa maneira que o Python implementa o conceito de **encapsulamento**.
Execute o programa para testar nossas suposições; uma exceção `AttributeError` será gerada.


## Abordagem por objetos: criando uma pilha do zero

Agora é hora das duas funções (métodos) implementarem as operações *push* e *pop*. Python presume que uma função desse tipo (uma atividade de classe) deve ser **imersa dentro do corpo da classe**, como se fosse um construtor.
Queremos chamar essas funções como valores de `push` e `pop` . Isto significa que ambas devem estar acessíveis para cada usuário da classe (em comparação com a lista construída anteriormente, que está oculta dos usuários da classe comum).

Esse componente é chamado de **público**, portanto seu nome não pode começar **com dois (ou mais) sublinhados**. Existe um outro requisito: **o nome não pode ter mais de um sublinhado no fim**. Como nenhum sublinhado à direita atende a esse requisito, podemos presumir que esse nome é aceitável.

As funções em si são simples. Dê uma olhada:

```
class Stack:
    def __init__(self):
        self.__stack_list = []


    def push(self, val):
        self.__stack_list.append(val)


    def pop(self):
        val = self.__stack_list[-1]
        del self.__stack_list[-1]
        return val


stack_object = Stack()

stack_object.push(3)
stack_object.push(2)
stack_object.push(1)

print(stack_object.pop())
print(stack_object.pop())
print(stack_object.pop())

```


Ambas as funções possuem um parâmetro chamado `self` na primeira posição da lista de parâmetros.

Ele é necessário? Sim, é.

Todos os métodos precisam ter esse parâmetro. Ele tem o mesmo papel do primeiro parâmetro construtor.

**Ele permite que o método acesse entidades (propriedades e atividades/métodos) realizadas pelo objeto em si**. 
Não é possível omiti-lo. Toda vez que Python chama um método, ele envia o objeto atual de forma implícita como o primeiro argumento.

Isto significa que um método é obrigado a ter pelo menos um parâmetro, usado pelo próprio Python, você não tem nenhuma influência sobre ele.
Se o seu método não precisar de nenhum parâmetro, este precisa ser especificado mesmo assim. Se ele tiver sido projeto para 
processar apenas um parâmetro, será necessário especificar dois; a função do primeiro continuará a mesma.

Existe mais um fator que exige explicação: a maneira com que os métodos são chamados de dentro de `__stack_list`.

Felizmente, é muito mais simples do que parece:

  * a primeira etapa entrega o objeto como um todo → `self`;
  * em seguida, é preciso obter a lista `__stack_list` → `self.__stack_list`;
  * como `__stack_list` está pronta para ser usada, é possível executar a terceira e última etapa → `self.__stack_list.append(val)`.

A declaração de classes está completa, todos os componentes foram listados. A classe está pronta para uso.

Ter essa classe abre um leque de novas possibilidades. Por exemplo, agora você pode ter mais de uma pilha se comportando da mesma maneira. 
Cada pilha terá sua própria cópia de dados privados, mas irá utilizar o mesmo conjunto de métodos.

É exatamente isso que queremos para este exemplo.

Analise o código:
```
class Stack:
    def __init__(self):
        self.__stack_list = []

    def push(self, val):
        self.__stack_list.append(val)

    def pop(self):
        val = self.__stack_list[-1]
        del self.__stack_list[-1]
        return val


stack_object_1 = Stack()
stack_object_2 = Stack()

stack_object_1.push(3)
stack_object_2.push(stack_object_1.pop())

print(stack_object_2.pop())
```

Existem duas pilhas criadas da mesma classe base. Elas funcionam de maneira independente. 
Você pode criar mais se quiser.
Execute o código no editor e veja o que acontece. 
Fique à vontade para fazer seus próprios experimentos!


Analise o snippet (fragmento) abaixo, criamos três objetos da classe `Stack`. Em seguida, os embaralhamos. 
Tente prever o valor que será mostrado na tela.
```
class Stack:
    def __init__(self):
        self.__stack_list = []

    def push(self, val):
        self.__stack_list.append(val)

    def pop(self):
        val = self.__stack_list[-1]
        del self.__stack_list[-1]
        return val


little_stack = Stack()
another_stack = Stack()
funny_stack = Stack()

```

E então, qual é o resultado? Execute o programa e confirma se está certo.

Agora vamos um pouco mais longe. Vamos incluir uma nova classe para lidar com pilhas.
A nova classe deve ser capaz de avaliar a soma de todos os elementos armazenados na pilha.

Não queremos modificar a pilha definida anteriormente. Ela já é boa o suficiente para o que será usada e não queremos alterá-la. 
Queremos uma nova pilha com novos recursos. Em outras palavras, queremos construir uma subclasse da classe Stack.

A primeira etapa é simples: basta definir uma nova subclasse indicando a classe que será usada como superclasse.

Este será o resultado:
```
class AddingStack(Stack):
    pass
```

A classe ainda não define nenhum novo componente, mas isso não significa que esteja vazia. 
Todos os seus componentes são definidos por sua superclasse, o nome da superclasse é criado 
antes da vírgula que vem logo após o novo nome de classe.

Isto é o que queremos da nova pilha:
  *  queremos que o método `push` não apenas envie o valor por push na pilha, mas que também inclua o valor na variável `sum`;
  *  queremos que a função `pop` não somente desempilhe o valor da pilha mas também que subtraia o valor da variável `sum`.

Primeiramente, iremos incluir uma nova variável na classe. Ela será uma **variável privada**, como a lista da pilha. 
Não queremos ninguém manipulando o valor de `sum`.

Como você já deve saber, incluir uma nova propriedade na classe é feito pelo construtor. 
Você já sabe como fazer isso, mas existe algo bastante interessante dentro do construtor. Dê uma olhada:
```
class AddingStack(Stack):
    def __init__(self):
        Stack.__init__(self)
        self.__sum = 0

```

A segunda linha do corpo do construtor cria uma propriedade chamada `__sum`, ela irá armazenar o total de todos os valores da pilha.

Mas a linha antes dela parece diferente. O que ela faz? Ela é mesmo necessária? Sim, é.
Ao contrário de muitas linguagens, Python força você a chamar de maneira explícita o **construtor de uma superclasse**. 
Omitir este ponto terá efeito prejudiciais, pois o objeto será privado da lista `__stack_list`. Essa pilha não irá funcionar da maneira desejada.

Este é o único momento que você pode chamar qualquer um dos construtores disponíveis de maneira explícita, 
o que pode ser feito a partir de dentro do construtor da subclasse.

Observe a sintaxe:

  *  você especifica o nome da superclasse (esta é a classe cujo construtor você deseja executar)
  *  colocamos um ponto (`.`) após o nome;
  *  você especifica o nome do construtor;
  *  você precisa apontar para o objeto (a instância da classe) que precisa ser inicializado pelo construtor;
     por isso é necessário especificar o argumento e usar a variável `self` aqui;
     observação: **chamar qualquer método (incluindo construtores) de fora da classe nunca requer que você coloque o argumento `self` na lista do argumento**,
     pois chamar um método de dentro da classe exige uso explícito do argumento `self` e ele precisa ser colocado em primeiro na lista.

**Observação**: recomenda-se chamar o construtor da superclasse antes de qualquer inicialização que você deseja realizar dentro da subclasse. 
Essa é a regra que seguimos no snippet.

```
class Stack:
    def __init__(self):
        self.__stack_list = []

    def push(self, val):
        self.__stack_list.append(val)

    def pop(self):
        val = self.__stack_list[-1]
        del self.__stack_list[-1]
        return val


class AddingStack(Stack):
    def __init__(self):
        Stack.__init__(self)
        self.__sum = 0
```






### RESUMO DA SEÇÃO
1. Uma pilha é um objeto criado para armazenar dados por meio do modelo LIFO. A pilha geralmente realiza pelo menos duas operações, chamadas de push() e pop().
2. A implementação da pilha em um modelo procedural gera uma série de problemas que podem ser resolvidos pelas técnicas oferecidas pela POO (Object Oriented Programming, ou Programação Orientada a Objetos).
3. Um método de classe é na verdade uma função declarada dentro da classe e capaz de acessar todos os componentes da classe.
4. A parte da classe Python responsável por criar novos objetos é chamada de construtor e é implementada como um método de nome __init__.
5. Cada declaração de método de classe deve conter pelo menos um parâmetro (sempre o primeiro), geralmente conhecido como selfe é usado pelos objetos para identificar a si mesmos.
6. Se quisermos ocultar qualquer um dos componentes de uma classe do mundo exterior, o nome deve começar com __. Esses componentes são chamados de privados.
