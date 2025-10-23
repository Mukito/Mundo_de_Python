## RESUMO DA SEÇÃO
1. Strings são ferramentas essenciais na era moderna de processamento de dados, uma vez que a maioria dos dados úteis são, na realidade, strings. Por exemplo, usar um mecanismo de busca na internet (algo extremamente trivial nos dias atuais) exige um processamento extremamente complexo de strings, envolvendo quantidades inimagináveis de dados.
2. A comparação de strings de maneira rigorosa (como faz o Python) pode ser bastante insatisfatória no que diz respeito a buscas avançadas(por ex., durante consultas extensivas a bancos de dados). Para responder a essa demanda, foram criados e implementados diversos algoritmos de comparação de strings por semelhança (fuzzy). Esses algoritmos são capazes de encontrar strings que não iguais nos padrões do Python, mas são similares.
Um desses conceitos é a distância de Hamming, usada para determinar a semelhança de duas strings. Se este problema lhe interessar, você poderá encontrar mais informações neste artigo: https://pt.wikipedia.org/wiki/Dist%C3%A2ncia_de_Hamming. Outra solução do mesmo tipo, mas baseada em outra suposição é a distância de Levenshtein, descrita aqui: https://pt.wikipedia.org/wiki/Dist%C3%A2ncia_Levenshtein.
3. Outra maneira de comparar as strings é encontrar sua semelhança acústica, que significa um processo para determinar se duas strings são foneticamente similares (como "cavaleiro" e "cavalheiro"). Essa semelhança precisa ser estabelecida para cada idioma (ou até mesmo dialeto) separadamente.
Um dos algoritmos usados para realizar essa comparação para o idioma inglês é chamado Soundex e foi inventado, por incrível que pareça, em 1918. Mais informações estão disponíveis neste artigo: https://en.wikipedia.org/wiki/Soundex.
4. Devido à precisão nativa limitada de dados float e integer, em certos casos faz sentido armazenar e processar valores numéricos grandes como strings. Essa é a técnica usada pelo Python ao forçar você a fazer operações em um número inteiro composto por uma quantidade muito grande de dígitos.



## Cifra de César
A cifra de César original troca os caracteres um a um: a se torna b, z se torna a e assim por diante. Vamos torná-lo um pouco mais complexo e permitir o valor alterado esteja no intervalo 1..25, inclusive.

Além disso, iremos permitir que o código preservar a caixa das letras (minúsculas permanecerão dessa maneira, por exemplo) e todos os caracteres não alfabéticos devem ser mantidos, sem alterações.

Sua tarefa é criar um programa que:

  * peça ao usuário uma linha de texto para criptografar;
  * solicita ao usuário um intervalo de troca (um número inteiro de 1..25 - observação: você deve forçar o usuário a digitar um valor de troca válido (não desista e não deixe dados ruins o enganem!)
  * mostra o texto codificado.


|     Entrada     |     Saida     |
|-----------------|---------------|
| abcxyzABCxyz 123 | cdezabCDEzab 123 |
| The die is cast 25 | Sgd chd hr bzrs |
                                    


```
# Insira o texto que deseja criptografar.
text = input("Enter message: ")

# Insira um valor válido de shift (repetir até o êxito).
shift = 0

while shift == 0:
    try:    
        shift = int(input("Enter the cipher shift value (1..25): "))
        if shift not in range(1,26):
        	raise ValueError
    except ValueError:
        shift = 0
    if shift == 0:
        print("Incorrect shift value!")

cipher = ''

for char in text:
    # É uma letra?
    if char.isalpha():
        # Shift its code.
        code = ord(char) + shift
        # Localizar o código da primeira letra (maiúscula ou minúscula)
        if char.isupper():
            first = ord('A')
        else:
            first = ord('a')
        # Fazer correção.
        code -= first
        code %= 26
        # Anexar o caractere codificado na mensagem.
        cipher += chr(first + code)
    else:
        # Anexar o caractere original na mensagem.
        cipher += char

print(cipher)
    
```

### Palíndromos
É uma palavra que permanece a mesma se lida de trás para frente. Por exemplo, "radar" é um palíndromo, mas"leal", não.
Sua tarefa é criar um programa que:
 * solicite que o usuário insira um texto;
 * verifica se o texto digitado é um palíndromo e mostra o resultado.
**Observação**
 * supõe-se que uma string vazia não é um palíndromo;
 * trata-se maiúsculas e minúsculas igualmente;
 * espaços não são levados em conta durante a verificação e são tratados como não existentes;
 * existe mais de uma solução correta, tente encontrar várias.


| Entrada | Saída | 
|---------|--------|
| A mala nada na lama | É palíndromo | 
| As malas nadam na lama | Não é palíndromo |


```
text = input("Digite o texto: ")

# Remove todos os espaços...
text = text.replace(' ','')

# ... e verifica se a palavra é igual à sua versão inversa
if len(text) > 1 and text.upper() == text[::-1].upper():
	print("É palíndromo")
else:
	print("Não é palíndromo")
```

### Anagramas
É uma nova palavra formada ao reordenar as letras de uma palavra, usando todas as letras originais exatamente uma vez. Por exemplo, as palavras "terno" e "norte" são anagramas, enquanto "Eu sou" e "você é", não.

Sua tarefa é criar um programa que:

 * peça ao usuário dois textos diferentes;
 * verifica se os textos digitados são anagramas e mostra o resultado.
**Observação:**
 * supõe-se que duas strings vazias não são anagramas;
 * trata-se maiúsculas e minúsculas igualmente;
 * espaços não são levados em conta durante a verificação e são tratados como não existentes


| Entrada | Saída | 
|---------|--------|
| Listen Silent | Anagramas | 
| modern norman | Não são anagramas |


### O número de vida
Alguns dizem que o *Número de Vida* é um número avaliado usando a data de nascimento de alguém. É simples, basta somar todos os números da data. Se o resultado contiver mais de um número, será necessário repetir a soma até obter apenas um número. Por exemplo:

 * 1 de janeiro de 2017 = 2017 01 01
 * 2 + 0 + 1 + 7 + 0 + 1 + 0 + 1 = 12
 * 1 + 2 = 3
3 é o número que estávamos procurando.

Sua tarefa é criar um programa que:

 * solicite a data de aniversário do usuário (no formato AAAAMMDD, AAAADDMM ou MMDDAAAA; na realidade, a ordem dos dígitos não importa)
 * mostre o Número de Vida resultante.
Teste seu código usando os dados que fornecemos.

| Entrada | Saida |
|---------|-------|
| 19991229 | 6 |
| 20000101 | 4 | 

### Encontre uma palavra
Vamos participar de um jogo. Daremos duas strings: uma com uma palavra (por ex., "gafe") e a segunda, uma combinação de quaisquer caracteres.

Sua tarefa é criar um programa que responda à seguinte pergunta: os caracteres da primeira palavra estão presentes na segunda string**?

Por exemplo:

 * se a segunda string fornecida for "vgcxzxdauybfdsobywues", a resposta é `sim`;
 * Se a segunda string for "vcxzxdcybfdstbywuefsas", a resposta é `não` (uma vez que as letras "g", "a", "f" ou "e" não aparecem nessa ordem)
Dicas:
 * recomendamos usar variações das funções pos() com dois argumentos em seu código;
 * não se preocupe com maiúsculas ou minúsculas.

| Entrada | Saida |
|---------|-------|
| donor Nabucodonosor | Yes |
| donut Nabucodonosor| NO | 

```
word = input("Digite a palavra que deseja encontrar: ").upper()
strn = input("Digite a string onde realizar a busca: ").upper()

found = True
start = 0

# Escreva o restante do código aqui.
```

### Sudoku
Sudoku
Como você provavelmente sabe, Sudoku é um quebra-cabeça de colocação de números, jogado em uma grade 9x9. O jogador precisa preencher a grade de uma maneira bastante específica:

 * cada linha da grade precisa conter todos os dígitos de 0 a 9 (a ordem não importa)
 * cada coluna da grade precisa conter todos os dígitos de 0 a 9 (mais uma vez, em qualquer ordem)
 * cada uma das "áreas" 3x3 (as chamaremos de "subquadrados") da grade devem conter todos os dígitos de 0 a 9.
 
Se precisar de mais detalhes, consulte esta página.
Sua tarefa é criar um programa que:

 * leia 9 linhas do Sudoku, cada uma contendo 9 dígitos (verifique, com atenção, se os dados inseridos são válidos)
 * mostra `Sim` caso o Sudoku seja válido e `Não` quando não for.
Teste o seu código com os dados que fornecemos.


| Entrada | Saida |
|---------|-------|
| 295743861
431865927
876192543
387459216
612387495
549216738
763524189
928671354
154938672 | Yes |
| 195743862
431865927
876192543
387459216
612387495
549216738
763524189
928671354
254938671| NO | 

```
# Uma função que verifica se uma lista passada como argumento contém
# nove dígitos de '1' a '9'.
def checkset(digs):
    return sorted(list(digs)) == [chr(x + ord('0')) for x in range(1, 10)]


# Uma lista com as linhas que representam o sudoku.
rows = [ ]
for r in range(9):
    ok = False
    while not ok:
        row = input("Digite o núm. da linha" + str(r + 1) + ": ")
        ok = len(row) == 9 or row.isdigit()
        if not ok:
            print("Dados incorretos, são necessários 9 dígitos")
    rows.append(row)

ok = True

# Verifica se todas as linhas são válidas.
for r in range(9):
    if not checkset(rows[r]):
        ok = False
        break

# Verifica se todas as colunas são válidas.	
if ok:
    for c in range(9):
        col = []
        for r in range(9):
            col.append(rows[r][c])
        if not checkset(col):
            ok = False
            break

# Verifica se todos os subquadrados (3x3) são válidos.
if ok:
    for r in range(0, 9, 3):
        for c in range(0, 9, 3):
            sqr = ''
            # Cria uma string com todos os dígitos de um subquadrado.
            for i in range(3):
                sqr += rows[r+i][c:c+3]
            if not checkset(list(sqr)):
                ok = False
                break

# Print the final verdict.
if ok:
    print("Sim")
else:
    print("Não")
    
```

