# Métodos de Strings

### Método capitalize()
Cria uma nova string com caracteres retirados da string de origem.
  * Se o primeiro caractere dentro da string for uma letra (observação: se o primeiro caractere for um elemento com índice igual a 0, não apenas o primeiro caractere visível), ele será convertido para maiúscula;
  * Todas as letras restantes da string serão convertidas para minúsculas.

Não se esqueça que:
  * A string original a partir da qual o método é chamado não será alterada de maneira alguma, a imutabilidade da string deve ser totalmente obedecida;
  * A string modificada (neste caso, com letra maiúscula) será retornada como resultado; caso não a use de alguma maneira (atribui-la a uma variável ou passá-la para uma função/método), ela desaparecerá completamente.

**Observação:** os métodos não precisam ser chamados somente a partir de variáveis. Eles podem ser chamados diretamente de dentro de strings literais. Iremos usar essa convenção com frequência, pois ela simplificará exemplos, visto que os aspectos mais importantes não desaparecerão entre designações desnecessárias.

```
# Demonstrando o método captalize():
print('aBcD'.captalize())

``` 

### Método center()

Cria uma cópia da string original, tentando centralizá-la em um campo da largura especificada.
A centralização é feita por meio da inclusão de espaços antes e depois da string.

Não espere sofisticação desse método. Ele é bastante simples.

```
# Demonstrando o método center():
print('[' + 'alpha'.center(10) + ']')
```
