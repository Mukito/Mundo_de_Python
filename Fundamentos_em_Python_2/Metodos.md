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

### Método endswith()
Verifica se a string fornecida termina com o argumento especificado e retorna `True` ou `False`, dependendo do resultado da verificação.
**Observação:** a substring deve aderir ao último caractere da string, ela não pode simplesmente estar localizada próximo ao final da string.

```
# Demonstrando o método endswith():
if "epsilon".endswith("on"):
    print("yes")
else:
    print("no")

```

### Método find()
Ele procura por uma substring e retorna o índice da primeira ocorrência desta substring, mas:
 * É mais seguro, pois não gera um erro para um argumento que contém uma substring não existente (ele retorna `-1`)
 * Ele funciona apenas com strings, não tente aplicá-lo em nenhuma outra sequência.

```
# Demonstrando o método find():
print("Eta".find("ta"))
print("Eta".find("mma"))
```

### Método isalnum()
Verifica se a string contém apenas dígitos ou caracteres alfabéticos (letras) e retorna `True` ou `False` de acordo com o resultado.

```
# Demonstrando o método isalnum():
print('lambda30'.isalnum())
print('lambda'.isalnum())
print('30'.isalnum())
print('@'.isalnum())
print('lambda_30'.isalnum())
print(''.isalnum())
```

### Método isalpha()
Ele se interessa apenas por letras.
```
# Exemplo 1: Demonstrando o método isapha():
print("Moooo".isalpha())
print('Mu40'.isalpha())
```

### Método isdigit()
Utiliza apenas dígitos qualquer outra entrada produz `False` como resultado.

```
# Exemplo 2: Demonstrando o método isdigit():
print('2018'.isdigit())
print("Year2019".isdigit())
```

### Método islower()
É uma variação mais complicada de `isalpha()` ele aceita somente letras minúsculas.
```
# Exemplo: Demonstrando o método islower():
print("Moooo".islower())
print('moooo'.islower())
```

### Método isspace()
Identifica somente os espaços em branco, ele ignora quaisquer outros caracteres (o resultado é False caso outros caracteres sejam usados).
```
# Exemplo: Demonstrando o método isspace():
print(' \n '.isspace())
print(" ".isspace())
print("mooo mooo mooo".isspace())
```

### Método isupper()
É a versão para maiúsculas de islower() e se concentra apenas em letras maiúsculas.
```
# Exemplo: Demonstrando o método isupper():
print("Moooo".isupper())
print('moooo'.isupper())
print('MOOOO'.isupper())
```


### Método join()
É bastante complicado, então iremos guiá-lo a cada passo:
 * como o nome sugere, o método executa uma **junção**, ele espera um argumento como uma lista; deve-se assegurar que todos os elementos da lista sejam strings, caso contrário o método irá causar uma exceção `TypeError` ;
 * todos os elementos da lista serão **unidos em uma string**, mas...
 * ...a string a partir da qual o método foi chamado será usada como **separador**, colocado entre as strings;
 * a string criada será retornada como resultado.

```
# Demonstrando o método join():
print(",".join(["omicron", "pi", "rho"]))
```

Vamos analisá-lo:

 * O método `join()` é chamado a partir de uma string contendo uma vírgula (a string pode ter um comprimento arbitrário, ou pode estar vazia)
 * O argumento de `join` é uma lista contendo três strings;
 * O método retorna uma nova string.

Output
```
omicron,pi,rho
```


### Método lower()
Faz uma cópia da string de origem, substitui todas as letras maiúsculas com suas equivalentes minúsculas e retorna a string como resultado. A string de origem permanece inalterada.
Se a string não possuir caracteres maiúsculos, o método retorna a string original.
**Observação**: O método `lower()` não aceita parâmetros.

```
# Demonstrando o método lower():
print("SiGmA=60".lower())
```


### Método lstrip()
Retorna uma nova string, formada a partir da original por meio da remoção de todos os espaços em branco iniciais.

```
# Demonstrando o método lstrip():
print("[" + " tau ".lstrip() + "]")
```

### Método replace()
Com dois parâmetros, retorna uma cópia da string original em que todas as ocorrências do primeiro argumento foram substituídas pelo segundo argumento.

```
# Demonstrando o método replace():
print("www.netacad.com".replace("netacad.com", "pythoninstitute.org"))
print("This is it!".replace("is", "are"))
print("Apple juice".replace("juice", ""))
```
Se o segundo argumento for uma string vazia, substituir na verdade significa remover a string do primeiro argumento. Que tipo de mágica acontece quando o primeiro argumento é uma string vazia?
A variante de três parâmetros de `replace()` usa o terceiro argumento (um número) para limitar o número de substituições.

```
print("This is it!".replace("is", "are", 1))
print("This is it!".replace("is", "are", 2))
```




