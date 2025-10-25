# Metodos

método é uma função integrada em uma classe. - método é obrigado a ter pelo menos um parâmetro (não existem métodos sem parâmetro; um método pode ser chamado sem argumento, mas não pode ser declarado sem parâmetros).

O Primeiro parametro e chamado de `self`.
SELF sugere o propósito do parâmetro que ele identifica o objeto para qual o método é chamado.

Se você chamar um método, não use o argumento para o parâmetro self, pois o Python irá defini-lo para você.

O exemplo no editor mostra a diferença.
```
class Classy:
    def method(self):
        print("method")


obj = Classy()
obj.method()
    
```

Como seguir:

```
class Classy:
    def method(self, par):
        print("method:", par)
 
 
obj = Classy()
obj.method(1)
obj.method(2)
obj.method(3)

```
O parâmetro `self` é usado para conseguir acesso à instância do objeto e às variáveis de classe.

```
class Classy:
    varia = 2
    def method(self):
        print(self.varia, self.var)
 
 
obj = Classy()
obj.var = 3
obj.method()
 
```


# RESUMO DA SEÇÃO
1. Um método é uma seção integrada em uma classe. O primeiro (ou único) parâmetro de cada método geralmente é chamado self, projetado para identificar o objeto para qual o método foi chamado para acessar as propriedades objeto ou chamar seus métodos.

2. Se uma classe contiver um **construtor** (um método chamado `__init__`) ela não pode retornar nenhum valor e não pode ser chamada diretamente.

3. Todas as classes (mas não os objetos) contêm uma propriedade chamada `__name__`, que armazena o nome da classe. Além disso, uma propriedade chamada `__module__` armazena o nome do módulo em que a classe foi declarada, enquanto a propriedade chamada `__bases__` é uma tupla que contém as superclasses de uma classe.

```
class Sample:
    def __init__(self):
        self.name = Sample.__name__
    def myself(self):
        print("My name is " + self.name + " living in a " + Sample.__module__)


obj = Sample()
obj.myself()

```
