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

### Métodos (Os Comportamentos)
Métodos são funções criadas dentro da classe que definem as ações que o objeto pode realizar. Eles sempre recebem o parâmetro `self` como primeiro argumento, que representa o próprio objeto que está chamando o método.

```python
class Carro:
    def __init__(self, marca, modelo):
        self.marca = marca
        self.modelo = modelo
        self.ligado = False

    # Este é um método
    def ligar(self):
        if not self.ligado:
            self.ligado = True
            print(f"O {self.modelo} ligou: Vrum Vrum!")
        else:
            print(f"O {self.modelo} já está ligado.")

# Usando o método
meu_carro = Carro("Chevrolet", "Onix")
meu_carro.ligar()  # Saída: O Onix ligou: Vrum Vrum!

```

### Os 4 Pilares da POO (Resumo Direto)
Para dominar POO, você também precisa conhecer estes quatro conceitos:

  1. **Encapsulamento**: Esconder partes internas do código para proteger os dados. Em Python, usamos um prefixo de dois underlines (__) para tornar um atributo ou método "privado" (ex: self.__saldo).
  2. **Herança**: Criar uma classe nova reutilizando características de uma classe existente.
```Python
class CarroEletrico(Carro):  # Herda tudo de Carro
    def carregar_bateria(self):
        print("Carregando...")
```

  3. **Polimorfismo**: Permite que classes diferentes tenham métodos com o mesmo nome, mas com comportamentos diferentes (ex: o método voador() se comporta de um jeito na classe Passaro e de outro na classe Aviao).
  4. **Abstração**: Isolar a complexidade do mundo real, focando apenas no que é essencial para o sistema (ex: para um sistema de trânsito, a cor do carro importa, mas o tipo de estofado do banco não).





