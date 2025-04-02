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
