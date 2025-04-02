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

