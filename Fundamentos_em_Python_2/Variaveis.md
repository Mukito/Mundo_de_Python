## RESUMO DA SEÇÃO
1. Uma **variável** de instância é uma propriedade cuja existência depende da criação de um objeto. Todo objeto possui um conjunto diferente de variáveis de instância.

Além disso, elas podem ser incluídas e removidas livremente de objetos durante seus ciclos de vida. Todas as variáveis de instância de objetos são armazenadas em um dicionário dedicado conhecido como `__dict__`, contido em todo objeto separadamente.


2. Uma variável de instância pode ser privada quando seu nome começar com `__`, mas não esqueça que tal propriedade ainda pode ser acessada de for ada classe usando um **nome codificado** construído como `_ClassName__PrivatePropertyName`.


3. Uma **variável de classe** é uma propriedade que existe em exatamente uma cópia e não precisa de nenhum objeto criado para estar acessível. Essas variáveis não são mostradas como conteúdo de `__dict__`.

Todas as variáveis de classe de uma classe são armazenadas em um dicionário dedicado chamado `__dict__`, contido em toda classe separadamente.


4. Uma função chamada `hasattr()` pode ser usada para determinar se algum objeto ou uma classe contém uma propriedade especificada.

Por exemplo:
```
class Sample:
    gamma = 0 # Class variable.
    def __init__(self):
 
        self.alpha = 1 # Instance variable.
        self.__delta = 3 # Variável de instância privada.
 
 
obj = Sample()
obj.beta = 2 # Outra variável de instância (que existe somente dentro da instância "obj".)
print(obj.__dict__)
```

