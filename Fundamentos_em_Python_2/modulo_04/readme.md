# Geradores:

**Gerador** – com o que associamos esta palavra? Talvez com algum dispositivo eletrônico. Ou talvez a algum maquinário pesado, projetado para fornecer energia, elétrica ou não.

Um gerador Python é um fragmento de código especializado para produzir uma série de valores e para controle o processo de iteração. 
É por esse motivo que os geradores são frequentemente chamados de iteradores e, embora algumas pessoas encontrem diferenças bastante sutis entre os dois, para fins deste material os tratamos como o mesmo tipo.

```
for i in range(5):
print(i)
```

# Função `Lambda`
A função **lambda** é um conceito emprestado da matemática, mais especificamente, de uma parte dela chamada *cálculo* Lambda, mas esses dois fenômenos não são iguais.

Matemáticos usam o *cálculo Lambda* em diversos sistemas formais conectados com lógica, recursão ou demonstração de teoremas. Programadores usam a função **lambda** para simplificar o código, torná-lo mais claro e mais fácil de ser compreendido.

Uma função **lambda** é uma função sem um nome (que também pode ser chamada de uma função anônima). Logicamente, tal instrução levanta a dúvida: como usamos algo que não pode ser identificado?

Felizmente, não é um problema, uma vez que podemos nomear uma função caso seja realmente necessário mas, na verdade, em muitos casos a função **lambda** pode existir e funcionar enquanto permanece totalmente anônima.

A declaração da função **lambda** não parece nem um pouco com uma declaração de função normal, veja você mesmo:
```
lambda parameters: expression
```

Tal cláusula **retorna o valor da expressão levando em conta o valor atual do argumento** `lambda` atual.

Como sempre, um exemplo será muito útil. Nosso exemplo usa três funções `lambda`, mas as fornecem nomes. Observe cuidadosamente:
```
two = lambda: 2
sqr = lambda x: x * x
pwr = lambda x, y: x ** y

for a in range(-2, 3):
    print(sqr(a), end=" ")
    print(pwr(a, two()))
```
Vamos analisá-lo:

  * a primeira `lambda` é uma **função sem parâmetros** e anônima que sempre retorna `2`. Como **atribuímos a ela uma variável chamada** `two`, podemos dizer que a função não é mais anônima e podemos usar o nome para chamá-la.
  * a segunda é uma **função anônima com um parâmetro** que retorna o valor de seu argumento ao quadrado. Nós também a nomeamos como tal.
  * a terceira `lambda` **recebe dois parâmetros** e retorna o valor da primeira, elevada à potência da segunda. O nome da variável que carrega o `lambda` fala por si só. Não usamos pow para evitar a confusão com a função integrada do mesmo nome e com o mesmo propósito.

O programa produz o seguinte resultado:
```
4 4
1 1
0 0
1 1
4 4
```
