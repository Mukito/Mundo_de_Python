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


+-----------+------------+
|  Entrada  |  Saida  |
+-----------+------------+
| abcxyzABCxyz 123 | cdezabCDEzab 123 |
|                  |                  |
