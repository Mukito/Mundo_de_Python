# POO Programa Orientado a Objeto

### Classe (O Molde)
É uma planta ou um molde para criar objetos. Define características e comportamentos o objeto terá.
```python
class Carro:
  pass  # Uma classe vazia por enquanto
```

### Objeto (A Instância)
É o produto final criado a partir do modelo da classe. Representação real e concreta daquela estrutura da nemória.
```python
# Criando um objeto da classe Carro
meu_carro = Carro()
```

### Atributos (As Características) 
Atributos são as várias dentro de uma classe que guardam as características do objeto (ex: cor, modelo, ano).
se dividem em dois tipos:
  * **Atributos de Instância:** Pertencem a cada objeto individualmente. Definimos esses atributos dentro do método especial `__init__`(o contrutor).
  * **Atributos de Classe:** Pertencem à classe como um todo e são compartilhados por todas as instâncias.

```python
class Carro:
  # Atributo de Classe (todos os carros têm 4 rodas)
  rodas = 4

  def __init__(self, marca, modelo, cor):
    # Atributos de Instância (cada carro tem o seu)
    self.marca = marca
    self.modelo = modelo
    self.cor = cor

# Instanciando e acessando atributos
carro1 = Carro("Ford", "Mustang", "Vermelho")
print(carro1.modelo)  # Saída: Mustang
print(carro1.rodas)   # Saída: 4
```
