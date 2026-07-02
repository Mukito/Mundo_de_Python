# Python 
tem uma lista enorme de métodos de string. Para facilitar sua vida, dividi os principais e mais usados em categorias lógicas.

1. Métodos de Validação (Os que começam com is...) <br>
Esses métodos servem para checar o conteúdo da string e sempre respondem com True ou False.
  * **.isalpha()**: Retorna True se o texto contiver apenas letras.
  * **.isnumeric()** ou .isdigit(): Retorna True se o texto contiver apenas números.
  * **.isalnum()**: Retorna True se for alfanumérico (apenas letras e/ou números, sem símbolos como @, !, _).
  * **.isspace()**: Retorna True se a string contiver apenas espaços em branco.
  * **.isupper()**: Retorna True se todas as letras estiverem em maiúsculas.
  * **.islower()**: Retorna True se todas as letras estiverem em minúsculas.
  * **.istitle()**: Retorna True se o texto estiver capitalizado (Cada Palavra Com A Primeira Letra Maiúscula).

2. Métodos de Modificação (Transformação de Texto) <br>
Esses mudam a aparência do texto (mas lembre-se: eles não alteram a string original, eles geram uma string nova alterada).
  * **.upper()**: Transforma todo o texto em MAIÚSCULAS.
  * **.lower()**: Transforma todo o texto em minúsculas.
  * **.capitalize()**: Força apenas a primeira letra da frase a ser maiúscula e o resto minúscula.
  * **.title()**: Transforma o texto em formato de título (Primeira Letra De Cada Palavra Maiúscula).
  * **.swapcase()**: Inverte tudo (o que era maiúsculo vira minúsculo e vice-versa).

3. Métodos de Limpeza e Divisão <br>
Essenciais para tratar dados que o usuário digita errado. 
  * **.strip()**: Remove todos os espaços inúteis do início e do fim do texto.
  * **.split()**: Divide a string em uma lista de palavras (por padrão, divide onde tiver espaços).
  * **.join()**: Pega uma lista de palavras e as junta em uma única string, usando um separador que você escolher.
  * **.replace("antigo", "novo")**: Substitui um pedaço do texto por outro.

4. Métodos de Busca e Análise <br>
Para encontrar coisas dentro do texto.
  * **.count("a")**: Conta quantas vezes a letra ou palavra informada aparece no texto.
  * **.find("texto")**: Procura onde está uma palavra e devolve a posição (índice) dela. Se não achar, devolve -1.
  * **.startswith("Algo")**: Verifica se o texto começa com aquela palavra específica (True/False).
  * **.endswith("Algo")**: Verifica se o texto termina com aquela palavra específica (True/False).




