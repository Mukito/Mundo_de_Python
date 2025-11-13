# Introdução ao módulo datetime
Nesta seção, você aprenderá sobre um módulo Python chamado datetime.

Como você pode imaginar, ele fornece aulas sobre como trabalhar com data e hora. Se você acha que não precisa se aprofundar neste tópico, vamos falar sobre exemplos de uso de data e hora na programação.

Data e hora têm inúmeras utilizações e provavelmente é difícil encontrar um aplicativo de produção que não as utilize. Veja a seguir alguns exemplo:


 * **criação de logs de eventos** — graças ao conhecimento de data e hora, conseguimos determinar quando exatamente ocorre um erro crítico em nossa aplicação. Ao criar logs, você pode especificar o formato de data e hora;

 * **rastrear alterações no banco de dados** — às vezes é necessário armazenar informações sobre quando um registro foi criado ou modificado. O módulo datetime será perfeito para este caso;

 * **validação de dados** — em breve, você aprenderá a ler a data e a hora atuais no Python. Ao saber a data e hora atuais, você poderá validar vários tipos de dados, por exemplo, se um cupom de desconto inserido por um usuário em nosso aplicativo ainda é válido;

 * **armazenar informações importantes** — você consegue imaginar transferências bancárias sem armazenar as informações de quando elas foram feitas? A data e a hora de certas ações devem ser preservadas e devemos lidar com isso.

Data e hora são usadas em quase todas as áreas de nossas vidas, então é importante se familiarizar com o módulo datetime. Você está pronto para uma nova dose de conhecimento??

`date` - Os objetos desta classe representam uma data que consiste no ano, mês e dia <br>
`today` - obtenha a data local atual usando o método <br>


```
from datetime import date

today = date.today()

print("Today:", today)
print("Year:", today.year)
print("Month:", today.month)
print("Day:", today.day)

```

O método `today` retorna um objeto `date` que representa a data local atual. Observe que o objeto `date` tem três atributos: *year, month e day*.


Para criar um objeto `date` , você deve passar os parâmetros year, month e day conforme a seguir:
```
from datetime import date

my_date = date(2019, 11, 4)
print(my_date)
```

## Criação de um objeto de data a partir de um timestamp
A classe `date` nos dá a capacidade de criar um objeto *date* por meio de um *timestamp*.

No Unix, o timestamp expressa o número de segundos desde 1º de janeiro de 1970, 00:00:00 (UTC) Esta data é chamada de **época Unix**, porque foi quando a contagem do tempo começou nos sistemas Unix.

O timestamp é, na verdade, a diferença entre uma data específica (incluindo a hora) e 1º de janeiro de 1970, 00:00:00 (UTC), expressa em segundos.

Para criar um objeto de data a partir de um timestamp, precisamos passar um timestamp Unix para o método `fromtimestamp` .

Para isso, podemos usar o módulo `time` que fornece funções relacionadas ao tempo. Uma delas é uma função chamada `time()`, que retorna o número de segundos de 1º de janeiro de 1970 até o momento atual na forma de um número flutuante. Vamos observar o exemplo no editor.

```
from datetime import date
import time

timestamp = time.time()
print("Timestamp:", timestamp)

d = date.fromtimestamp(timestamp)
print("Date:", d)
```

### Replacers

```
from datetime import date

d = date(1991, 2, 5)
print(d)

d = d.replace(year=1992, month=1, day=16)
print(d)
    
```

### Que dia da semana é hoje?
Um dos métodos mais úteis que torna o trabalho com datas mais fácil é o método chamado `weekday`. Ele retorna o dia da semana como um inteiro, em que 0 é segunda-feira e 6 é domingo. Execute o código no editor.

```
from datetime import date

d = date(2019, 11, 4)
print(d.weekday())
```
`isoweekday`
```
from datetime import date
 
d = date(2019, 11, 4)
print(d.isoweekday())
```

| **Parâmetro** | **Restrições** |
|----------------|----------------|
| `hour` | O parâmetro `hour` deve ser maior ou igual a 0 e menor que 23. |
| `minute` | O parâmetro `minute` deve ser maior ou igual a 0 e menor que 59. |
| `second` | O parâmetro `second` deve ser maior ou igual a 0 e menor que 59. |
| `microsecond` | O parâmetro `microsecond` deve ser maior ou igual a 0 e menor que 1000000. |
| `tzinfo` | O parâmetro `tzinfo` deve ser um objeto de subclasse `tzinfo` ou `None` (padrão). |
| `fold` | O parâmetro `fold` deve ser 0 ou 1 (padrão 0). |


# Metodo
A classe `datetime` tem vários métodos que retornam a data e hora atuais. Esses métodos são:

`today()` — retorna a data e hora local atual com o atributo tzinfo configurado como None;
`now()` — retorna a data e hora local atual da mesma forma que o método today, a menos que passemos o argumento opcional tz para ele. O argumento deste método deve ser um objeto da subclasse tzinfo;
`utcnow()` — retorna a data e hora UTC atuais com o atributo tzinfo configurado como None.

## Formatação
```
from datetime import date

d = date(2020, 1, 4)
print(d.strftime('%Y/%m/%d'))
```

# Introdução ao módulo calendar

```
import calendar
ano = 2026
print(calendar.calendar(ano))
```

sem o ***PRINT***
```
import calendar
calendar.prcal(2020)
```
## Como verificar se um ano é bissexto?
O módulo `calendar` fornece duas funções úteis para verificar se os anos são bissextos.

O primeiro, chamado `isleap`, retorna True se o ano é bissexto ou False se não for. O segundo, chamado `leapdays`, retorna o número de anos bissextos no intervalo de anos fornecido.

Execute o código no editor.
```
import calendar

print(calendar.isleap(2020))
print(calendar.leapdays(2010, 2021))  # Até, mas sem incluir 2021.
```
No exemplo, obtemos o resultado 3, pois no período de 2010 a 2020 há apenas três anos bissextos (observação: 2021 não está incluso). São os anos 2012, 2016 e 2020.

---------------------------------------------------------------

## Classes para criação de calendários
As funções que mostramos até agora não são tudo o que o módulo `calendar` oferece. Além delas, podemos usar as seguintes classes:

 * ``calendar.Calendar – fornece métodos para preparar dados de calendário para formatação;
 * `calendar.TextCalendar` – é usado para criar calendários de texto regulares;
 * `calendar.HTMLCalendar` – é usado para criar calendários HTML;
 * `calendar.LocalTextCalendar` – é uma subclasse da classe `calendar.TextCalendar` . O construtor desta classe usa o parâmetro locale, que é usado para retornar os nomes apropriados dos meses e dias da semana.
 * `calendar.LocalHTMLCalendar` – é uma subclasse da classe `calendar.HTMLCalendar` . O construtor desta classe usa o parâmetro locale, que é usado para retornar os nomes apropriados dos meses e dias da semana.
Durante este curso, você já teve a oportunidade de criar calendários de texto ao discutir as funções do módulo `calendar` .

Agora é hora de tentar algo novo. Vamos analisar de maneira mais detalhada os métodos da classe `calendar` .

## Criando um objeto *Calendar*
O construtor de classe `Calendar` recebe um parâmetro opcional chamado `firstweekday`, por padrão igual a 0 (segunda-feira).

O parâmetro `firstweekday` deve ser um número inteiro entre 0 e 6. Para isso, podemos usar as constantes já conhecidas - veja o código no editor.
```
import calendar  

c = calendar.Calendar(calendar.SUNDAY)

for weekday in c.iterweekdays():
    print(weekday, end=" ")
    
```

https://docs.python.org/pt-br/3.13/library/calendar.html




