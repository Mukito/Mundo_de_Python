### Mutabilidade 
é uma propriedade de qualquer dado Python que descreva sua disponibilidade para ser livremente alterado durante a execução do programa. Existem dois tipos de dados Python: mutáveis e imutáveis.

#### Os Dados mutáveis 
podem ser atualizados livremente a qual quer momento - chamamos isso de operação *in situ*.

***in situ*** é uma fase em latim que se traduz literalmente em POSIÇÂO. Por exemplo, a instrução a seguir modifica os dados *in situ*

`list.append(1)`

#### Os Dados imutáveis 
não podem ser modificados dessa maneira.
Imagine que uma lista so possa ser atribuída e reler. Você não pode acrescentar um elemento a ele nem remover nenhum elemento dele.

você precisa criar uma lista completamente nova.

**Tupla** - é um tipo de sequência imutável. pode se comportar como uma lista, mas não pode ser modificado ***in situ***

tuple_1 = (1, 2, 4, 8)
tuple_2 = 1., .5, .25, .125



## Dicionários
O dicionário é outra estrutura de dados Python. Não é um tipo de sequência (mas pode ser facilmente adaptado ao processamento de sequência) e é **mutável**.

```
dictionary = {"gato": "chat", "cachorro": "chien", "cavalo": "cheval"}
phone_numbers = {'chefe': 5551234567, 'Suzy': 22657854310}
empty_dictionary = {}
 
print(dictionary)
print(phone_numbers)
print(empty_dictionary)

```

As tuplas são ordenadas e coleções imutáveis (imutáveis) de dados. Eles podem ser vistos como listas imutáveis. Eles estão escritos entre colchetes:
```
my_tuple = (1, 2, True, "um barbante", (3, 4), [5, 6], None)
print(my_tuple)
 
my_list = [1, 2, True, "um barbante", (3, 4), [5, 6], None]
print(my_list)
 
```
