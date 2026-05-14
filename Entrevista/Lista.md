# Lista

é uma estrutura de dados mais fundamentais e versáteis na programação, especialmente em liguagem python.

Imagine uma lista com uma **fileira de armarios numerados**. Você pode colocar qualquer 
coisa dentro desse armários, muda o que está lá dentro, adicionar novos armários no final ou remove os que não precisa.

1. **Ordenação e indexação**
  * **Importante**: As linguagens(como Python, C, Java), a contagem começa no **0**
  * Se vc tiver uma lista de frutas ['Maçã', 'Banana', 'Laranja'], a 'Maçã' está no índice **0**
    
2. **Mutabilidade**
  As listas são **mutáveis**, pode alterar o conteúdo de um índice após a
lista ter sido criada, sem precisar criar uma lista totalmente nova. você pode subistituir um item,
apagar ou inserir elementos a qualquer momento

3. **Heterogeneidade**
 Diferente do "Array" em linguagens mais rígidas (como C++), uma lista em python pode conter **tipos de dados diferentes** ao mesmo tempo.
```python
minha_lista = [10, "Texto", 3.14, True] # Inteiro, String, Float e Booleano juntos.
```

4. **Operações Comuns**
  As listas permitem realizar diversas ações de forma simples:

  * **Append**: Adiciona um item ao FINAL da LISTA
  * **Insert** Adiciona um item em uma POSIÇÂO ESPECÍFICA.
  * **Pop/Remove**: Retira um item da lista.
  * **Slicing (Fatiamento)**: Permite pegar apenas uma "Fatia" ou pedaço da lista(ex: pegar do 2° ao 5° elemento).

---
### Por que as listas são importantes?
elas servem de base para estruturas mais complexas. Como vimos no exercícios que você
postou anteriormente, uma Pilha(Stack) é frequentemente implementada usando uma lista,
onde você restringe o uso para que as adiçoes e remoções aconteçam apenas no **"top"**
(o final da lista).

### Criando e Acessando
Para criar uma lista, usamos colchetes `[]`. Para acessar um item, usamos o número da posição (índice).

```
# Criando a lista
programadores = ["Alice", "Bob", "Carlos"]

# Acessando (Lembre-se: começa no 0)
print(programadores[0])  # Saída: Alice
```

### Adicionando Itens (`append` e `insert`)
O `append` é o que você viu no exercício: ele "joga" o elemento lá no final da fila. Se precisar colocar em um lugar específico, usamos o `insert`.
```
programadores.append("Daniela") # Vai para o final: ["Alice", "Bob", "Carlos", "Daniela"]
programadores.insert(1, "Beto") # Entra na posição 1: ["Alice", "Beto", "Bob", "Carlos", "Daniela"]
```

### Removendo Itens (`pop`, `remove` e `del`)
Existem três formas principais, dependendo do que você sabe sobre o item:

* **pop()**: Remove e te "entrega" o último elemento (comum em Pilhas).
* **remove("Nome")**: Procura pelo valor específico e o deleta.
* **del**: Deleta baseado no índice (foi o que a **Opção B** da sua questão usou).


### Utilidades Rápidas
Muitas vezes você vai precisar saber o tamanho da lista ou se ela está vazia (exatamente como o `if len(p1) == 0` do seu código):

```
tamanho = len(programadores) # Retorna quantos itens tem
print(tamanho) 

# Verificando se um item está na lista
if "Alice" in programadores:
    print("Ela faz parte do time!")
```

