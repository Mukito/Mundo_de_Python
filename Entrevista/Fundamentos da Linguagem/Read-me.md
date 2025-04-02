## 📌 Qual a diferença entre listas e tuplas em Python?

A principal diferença entre **listas** e **tuplas** em Python está na **mutabilidade**:

* **Listas** (`list`) são **mutáveis**, ou seja, podem ser modificadas após a criação. Você pode adicionar, remover ou alterar elementos.

* **Tuplas** (`tuple`) são **imutáveis**, ou seja, depois de criadas, seus elementos não podem ser alterados.

### Exemplo de lista (mutável)

```
lista = [1, 2, 3]
lista.append(4)  # Adiciona um elemento
lista[0] = 99    # Modifica um elemento
print(lista)  # Saída: [99, 2, 3, 4]
```

### Exemplo de tupla (imutável)

```
tupla = (1, 2, 3)
tupla[0] = 99  # Erro! Tuplas não podem ser modificadas
```

### Saída:

```
TypeError: 'tuple' object does not support item assignment
```

## Outras diferenças importantes<br>


|**Característica**	 |  **Lista** (`list`)	 |  **Tupla** (`tuple`)  |
|--------------------|-----------------------|-----------------------|
|**Mutabilidade**	 |  Mutável	 |  Imutável  |
|**Velocidade**  |  Mais lenta	 |  Mais rápida (menos sobrecarga de memória)  |
|**Uso de memória**  |  Ocupa mais espaço  |  Ocupa menos espaço  |
|**Segurança**  |  Pode ser alterada acidentalmente	 |  Protege dados contra modificações  |
|**Métodos**  |  `.append()`, `.remove()`, `.sort()`, etc.	|  Apenas `.count()` e `.index()` |

### Quando usar cada uma?
* Use **listas** quando precisar modificar os dados com frequência.

* Use **tuplas** quando precisar garantir que os dados permaneçam inalterados (exemplo: coordenadas de um ponto, dias da semana, chaves de dicionário).


## 📌 O que são dicionários e como funcionam?

Os **dicionários** (`dict`) em Python são estruturas de dados que armazenam pares **chave-valor**. Eles são **mutáveis**, ou seja, podem ser alterados após a criação, e permitem acesso rápido aos valores através de suas chaves.

### 🔹 Sintaxe de um dicionário  
```python
# Criando um dicionário
dados = {
    "nome": "Alice",
    "idade": 25,
    "cidade": "São Paulo"
}

# Acessando valores
print(dados["nome"])  # Saída: Alice

# Adicionando um novo par chave-valor
dados["profissao"] = "Engenheira"

# Modificando um valor existente
dados["idade"] = 26

# Removendo um item
del dados["cidade"]

# Verificando se uma chave existe
if "nome" in dados:
    print("Nome está presente!")
```

### 🔹 Principal características

- ✅ **Mutáveis** → Você pode adicionar, modificar e remover elementos.
- ✅ **Chaves únicas** → Cada chave deve ser única dentro do dicionário.
- ✅ **Acesso rápido** → O acesso aos valores é feito via chave, e não por índices como em listas.
- ✅ **Não ordenados (até Python 3.6)** → A partir do Python 3.7, a ordem de inserção das chaves é mantida.

### 🔹 Métodos úteis
```
dados.keys()   # Retorna todas as chaves
dados.values() # Retorna todos os valores
dados.items()  # Retorna pares chave-valor
dados.get("nome", "Não encontrado") # Evita erro se a chave não existir
dados.pop("idade")  # Remove um item e retorna o valor removido
dados.clear()  # Apaga todos os elementos do dicionário
```
### 🔹 Exemplo de uso em um loop
```
for chave, valor in dados.items():
    print(f"{chave}: {valor}")

```
 **Saída**

```
nome: Alice  
profissao: Engenheira  

```

### 🔹 Comparação entre dicionários e outras estruturas

| **Característica**	 |  Lista (`list`)	|  Tupla (`tuple`)  |	Dicionário (`dict`) |
|----------------------|----------------|-----------------|-------------------|
| **Mutabilidade**  |  Mutável  |	Imutável  |	 Mutável  |
| **Velocidade**	 |  Média	 | Rápida	| Muito rápida para acesso por chave |
| **Uso de memória**  | 	Ocupa mais espaço |	Ocupa menos espaço |	Ocupa mais espaço devido à indexação |
| **Acesso aos dados**	 |  Via índice (`list[0]`) |	Via índice (`tuple[0]`)	| Via chave (`dict["chave"]`) |
| **Ordem garantida**	 |  Sim (desde Python 3.7)	| Sim	 | Sim (desde Python 3.7) |
| **Casos de uso**	 |  Listas de itens variados	| Dados constantes, coordenadas |	Estruturas associativas (JSON, APIs) |

Os dicionários são muito úteis para armazenar dados estruturados, como JSONs, e são amplamente usados em APIs e manipulação de dados.

## 📌 Qual a diferença entre `deepcopy` e `copy` no módulo *copy*?
O módulo `copy` do Python fornece duas formas de copiar objetos:

* `copy.copy(obj)` → Faz uma **cópia rasa (shallow copy)**

* `copy.deepcopy(obj)` → Faz uma **cópia profunda (deep copy)**
-------------------------------------------------------------

### 🔹 1. Cópia rasa (`copy.copy()`)
A **shallow copy** copia apenas a **estrutura externa** do objeto. Se o objeto contiver referências a outros objetos (listas dentro de listas, por exemplo), essas referências não são copiadas, apenas reutilizadas.

#### Exemplo de copy.copy()

```
import copy

lista_original = [[1, 2, 3], [4, 5, 6]]
lista_copiada = copy.copy(lista_original)

lista_copiada[0][0] = 99  # Modificando um elemento dentro da lista

print(lista_original)  # Saída: [[99, 2, 3], [4, 5, 6]]
print(lista_copiada)   # Saída: [[99, 2, 3], [4, 5, 6]]
```
✅ **Conclusão**: Como `copy.copy()` copia apenas a referência para os subelementos, modificar um subelemento em uma das listas reflete na outra.

------------------------------------------------------------------------------------

### 🔹 2. Cópia profunda (`copy.deepcopy()`)
A **deep copy** copia **toda a estrutura do objeto**, incluindo objetos aninhados, garantindo que as cópias sejam totalmente independentes.

### Exemplo de `copy.deepcopy()`

```
import copy

lista_original = [[1, 2, 3], [4, 5, 6]]
lista_copiada = copy.deepcopy(lista_original)

lista_copiada[0][0] = 99  # Modificando um elemento dentro da lista copiada

print(lista_original)  # Saída: [[1, 2, 3], [4, 5, 6]]
print(lista_copiada)   # Saída: [[99, 2, 3], [4, 5, 6]]

```
✅ **Conclusão**: Como `copy.deepcopy()` copia **toda a estrutura** do objeto, a modificação na cópia **não afeta o original**.

--------------------------------------------------------------------------------

### 🔹 Resumo das diferenças

|Método	|Tipo de Cópia	|Cópia dos Subobjetos?	|Independente?|
|-------|---------------|-----------------------|-------------|
|`copy.copy()`	|Cópia rasa (shallow)	|Não (mantém referências)	|Não, pois objetos aninhados ainda são compartilhados|
|`copy.deepcopy()`	|Cópia profunda (deep)	|Sim (cria novos objetos)|	Sim, pois toda a estrutura é copiada|

-------------------------------------------------------------------------------------
### Quando usar cada um?
* Use `copy.copy()` → Quando seu objeto **não contém objetos mutáveis internos** ou você quer apenas copiar a estrutura principal.

* Use `copy.deepcopy()` → Quando seu objeto contém **listas, dicionários ou outras estruturas mutáveis** dentro dele e você precisa garantir que as cópias sejam independentes.

## 📌Como funciona o gerenciamento de memória no Python?

----------------------------------------------------------------------
O **Python gerencia a memória automaticamente** através de um sistema que inclui **alocação dinâmica**, **contagem de referências** e um **coletor de lixo (Garbage Collector - GC)**.

### 🔹 1. Como a memória é alocada no Python?
O Python organiza a memória em **duas grandes áreas**:

1. **Stack (Pilha)**:

 * Usada para armazenar variáveis locais e chamadas de função.

 * O gerenciamento é feito automaticamente quando funções entram e saem da execução.

2. **Heap (Montante)**:

 * Onde ficam armazenados objetos e estruturas de dados dinâmicos (listas, dicionários, instâncias de classes, etc.).

 * O Python usa um sistema de **pools de memória** para reutilizar pequenos objetos e evitar fragmentação.

------------------------------------------------------------------------------------------------

## 🔹 2. Contagem de Referências (`refcount`)
Cada objeto em Python tem um **contador de referências**, que indica quantas variáveis ou estruturas estão apontando para ele.

### Exemplo:
```
import sys

a = [1, 2, 3]  # Criação da lista
b = a          # 'b' agora aponta para a mesma lista de 'a'

print(sys.getrefcount(a))  # Saída: 3 (a, b e a chamada do método contam)

```

* Se a contagem de referências chegar a **zero**, o objeto é removido da memória.

---------------------------------------------------------------------------------------------------

## 🔹 3. Coletor de Lixo (Garbage Collector)
O Python possui um **coletor de lixo automático** (`gc`), que remove objetos órfãos da memória.
Isso ocorre principalmente em **casos de referências circulares**, onde objetos apontam uns para os outros, impedindo a liberação automática.

### Exemplo de referência circular (problema):
```
import gc

class A:
    def __init__(self):
        self.ref = None

obj1 = A()
obj2 = A()

obj1.ref = obj2  # obj1 aponta para obj2
obj2.ref = obj1  # obj2 aponta para obj1

del obj1
del obj2

gc.collect()  # Força a remoção de objetos órfãos
```
* Sem o `gc.collect()`, os objetos poderiam ficar presos na memória.

---------------------------------------------------------------------------------------------------

## 🔹 4. Otimizações do Python
####📍 Small Object Pooling
O Python reutiliza pequenos inteiros e strings imutáveis para melhorar a performance.

### Exemplo:
```
a = 10
b = 10
print(a is b)  # Saída: True (mesmo objeto na memória)

x = 300
y = 300
print(x is y)  # Saída: False (inteiros maiores podem ser alocados separadamente)

```
* Inteiros de -5 a 256 são reutilizados.

------------------------------------------------------------------------------------------------

#### 📍 String Interning
Strings imutáveis pequenas e sem espaços podem ser armazenadas no cache.

### Exemplo:
```
s1 = "Python"
s2 = "Python"
print(s1 is s2)  # Saída: True (mesmo objeto)

```
---------------------------------------------------------------------------------------------------

## 🔹 5. Como melhorar o uso da memória no Python?
#### ✅ Evite referências desnecessárias:
```
a = [1, 2, 3]
b = a
del a  # 'b' ainda mantém a lista na memória
```
#### ✅ Use `del` e `gc.collect()` para liberar memória:
```
import gc
del obj
gc.collect()
```

#### ✅ Prefira gerenciadores de contexto (`with`)
```
with open("arquivo.txt") as f:
    dados = f.read()  # Arquivo fechado automaticamente
```

#### ✅ Utilize __slots__ para otimizar classes
```
class Pessoa:
    __slots__ = ['nome', 'idade']  # Reduz o uso de memória ao evitar dicionários internos

p = Pessoa()
p.nome = "Alice"
p.idade = 25

```

----------------------------------------------------------------------------------------------------

## 🔹 **Resumo**

| Mecanismo                  | Função                                                    |
|----------------------------|-----------------------------------------------------------|
| **Stack (Pilha)**          | Armazena variáveis locais e chamadas de função           |
| **Heap (Montante)**        | Armazena objetos e estruturas de dados dinâmicas         |
| **Contagem de Referências** | Libera automaticamente objetos sem referências          |
| **Garbage Collector (`gc`)** | Remove objetos órfãos para evitar vazamento de memória |
| **Small Object Pooling**   | Reutiliza pequenos inteiros e strings para otimizar o uso de memória |

O gerenciamento de memória do Python é automático, mas **boas práticas podem ajudar a otimizar o desempenho e evitar consumo excessivo**. 🚀


## 📌O que são List Comprehensions e como usá-las?

**List Comprehension** é uma forma concisa e eficiente de criar listas em Python. Em vez de usar loops `for` convencionais, podemos gerar listas em **uma única linha de código**, tornando o código mais **limpo** e **performático**.

____________________________

## 🔹 1. Sintaxe Básica
A sintaxe de uma List Comprehension é:
```
[expressão for item in iterável if condição]
```
* `expressão` → Define como cada elemento será processado.

* `for item in iterável` → Percorre a estrutura de dados.

* `if condição (opcional)` → Filtra os elementos.

__________________________________

## 🔹 2. Exemplos Práticos
#### 📍 Criando uma lista sem List Comprehension
```
numeros = []
for i in range(10):
    numeros.append(i * 2)

print(numeros)  # [0, 2, 4, 6, 8, 10, 12, 14, 16, 18]
```
#### 📍 Criando a mesma lista com List Comprehension

```
numeros = [i * 2 for i in range(10)]
print(numeros)  # [0, 2, 4, 6, 8, 10, 12, 14, 16, 18]
```

#### ✅ Resultado idêntico, mas com menos código!

_______________________________________________

## 🔹 3. Usando if para Filtragem
#### 📍 Pegando apenas números pares de 0 a 9
```
pares = [i for i in range(10) if i % 2 == 0]
print(pares)  # [0, 2, 4, 6, 8]
```
#### 📍 Pegando números maiores que 5 de uma lista
```
numeros = [1, 5, 8, 12, 3, 7]
maiores = [n for n in numeros if n > 5]
print(maiores)  # [8, 12, 7]
```
________________________________________________________
## 🔹 4. Usando if...else Dentro da List Comprehension
#### 📍 Convertendo números em "Par" ou "Ímpar"
```
resultado = ["Par" if i % 2 == 0 else "Ímpar" for i in range(5)]
print(resultado)  # ['Par', 'Ímpar', 'Par', 'Ímpar', 'Par']
```

## 🔹 5. List Comprehension com Múltiplos for
#### 📍 Criando pares de números de duas listas
```
pares = [(x, y) for x in range(3) for y in range(3)]
print(pares)
# [(0, 0), (0, 1), (0, 2), (1, 0), (1, 1), (1, 2), (2, 0), (2, 1), (2, 2)]
```

## 🔹 6. List Comprehension com Funções
#### 📍 Convertendo palavras para maiúsculas
```
palavras = ["python", "lista", "comprehension"]
maiusculas = [palavra.upper() for palavra in palavras]
print(maiusculas)  # ['PYTHON', 'LISTA', 'COMPREHENSION']
```
#### 📍 Calculando o quadrado de números
```
def quadrado(n):
    return n ** 2

quadrados = [quadrado(x) for x in range(6)]
print(quadrados)  # [0, 1, 4, 9, 16, 25]
```

_____________________________________________________________


## 🔹 7. Comparação de Performance
#### 📍 List Comprehension é mais rápida do que loops tradicionais!
```
import time

# Usando um loop for
inicio = time.time()
lista1 = []
for i in range(10**6):
    lista1.append(i * 2)
print("Loop for:", time.time() - inicio)

# Usando List Comprehension
inicio = time.time()
lista2 = [i * 2 for i in range(10**6)]
print("List Comprehension:", time.time() - inicio)
```
#### ✅ **Resultado**: List Comprehension é significativamente mais rápida! 🚀

_______________________________________________________________________


## 🔹 8. Quando Usar List Comprehensions?
#### ✅ Quando melhora a legibilidade
#### ✅ Quando precisa de performance
#### ✅ Quando o código pode ser reduzido sem perder clareza

#### **Evite List Comprehensions quando a lógica for muito complexa**, pois pode reduzir a legibilidade do código.

_______________________________________________________________________

## 🔹 Resumo

| **Conceito**	 |  Explicação  |
|----------------|--------------|
| **Sintaxe** 	|  `[expressão for item in iterável if condição]`  |
| **Vantagens**  |	 Código mais limpo, legível e eficiente  |
| **Com `if`**	 |  `[x for x in lista if x > 5]`  |
| **Com `if...else`**  |	 `["Par" if x % 2 == 0 else "Ímpar" for x in lista]`  |
| **Com múltiplos loops**  |	 `[(x, y) for x in range(3) for y in range(3)]`  |
| **Com funções**  |	 `[função(x) for x in lista]`  |

#### 🔹 List Comprehension é uma das melhores técnicas para otimizar código Python! 🚀









