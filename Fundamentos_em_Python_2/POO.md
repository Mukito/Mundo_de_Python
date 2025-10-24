## Fundamentos

### Conceitos
Na **abordagem procedural**, é possível distinguir dois mundos diferentes e completamente distintos: **o mundo dos dados e o mundo do código**. O mundo dos dados é composto por variáveis de diferentes tipos, enquanto o mundo do código é composto por código agrupado em módulos e funções.

As funções são capazes de usar dados, mas o contrário não é possível. Além disso, as funções são capazes de usar dados de maneira inválida, ou seja, usar o valor de maneira não autorizada (por ex., quando a função seno recebe o saldo de uma conta corrente como parâmetro).

No passado, dissemos que os dados não podem usar funções. Mas será que isso é totalmente verdadeiro? Existem tipos especiais de dados que podem usar funções?

Sim, existem, e são chamados de métodos. Essas funções são chamadas de dentro dos dados e não junto a eles. Se conseguir entender essa diferença, você deu o primeiro passo na programação por objetos.

A **abordagem de objetos** sugere uma maneira completamente diferente de se pensar. Os dados e o código são colocados juntos no mesmo universo, divididos por classes.

Cada classe é **como uma receita que pode ser usada quando desejar criar um objeto útil** (é graças a isso que a abordagem tem esse nome). É possível produzir quantos objetos forem necessários para resolver seu problema.

Cada objeto possui um conjunto de características (chamadas de propriedades ou atributos – as duas palavras têm o mesmo significado em nosso material) e é capaz de realizar um conjunto de atividades (chamadas de métodos).

As receitas podem ser modificados caso não sejam adequadas para um determinado propósito e, além disso, é possível criar novas classes. Essas novas classes herdam propriedades e métodos das originais e geralmente recebem alguns novos criando, portanto, ferramentas mais novas e específicas.

----------------------------------------------------------------------------------

**Objetos são representações** de ideias expressas em classes, como um bolo em seu prato que é a representação da ideia presente em um livro de receitas antigo.

Os objetos interagem entre si, trocando dados ou ativando seus métodos. Uma classe bem construída (e portanto, seus objetos) são capazes de proteger os dados confidenciais e ocultá-los de modificações não autorizadas.

Não existe um limite claro entre dados e código; eles coabitam objetos.

Todos esses conceitos não são tão abstratos como parecem em um primeiro momento. Pelo contrário, são todos retirados de experiências reais e, portanto, extremamente úteis em programação de computadores: não criam vida artificial e sim **refletem fatos, relacionamentos e circunstâncias reais**.

<br>

<img width="539" height="511" alt="image" src="https://github.com/user-attachments/assets/645feb65-1ca9-4c4b-b660-754f18aabea9" />


---------------------------------------------------------------------------------

## Hierarquias de classe

A palavra *classe* possui diversos significados, mas nem todos são compatíveis com as ideias que gostaríamos de discutir aqui. 
A classe de qual estamos falando é como uma categoria como resultado de similaridades definidas com precisão.

Tentaremos mostrar algumas classes que são bons exemplos desse conceito.


<img width="1316" height="698" alt="image" src="https://github.com/user-attachments/assets/35d9c497-210e-4afa-bd46-f6972856d192" />


Vamos voltar nossa atenção por um momento para veículos em geral. Todos os veículos existentes (e aqueles que ainda não existem) estão **ligados por uma característica** importante: a capacidade de locomoção. Você pode argumentar que um cachorro também se locomove; um cão é um veículo? Não, não é. Precisamos melhorar a definição, enriquecê-la com mais critérios para distinguir veículos de outros seres e criar uma conexão mais forte. Vamos levar as seguintes circunstâncias em consideração: veículos são entidades criadas artificialmente, usadas para transporte, movidas pela força da natureza e direcionadas (dirigidas) por seres humanos.

Com base nessa definição, um cão não é um veículo.

A classe *veículos* é bastante ampla. Ampla demais. Sendo assim, precisamos definir **classes especializadas**. As classes especializadas são as subclasses. A classe veículos será a superclasse para todas elas.

Observação: a hierarquia cresce de baixo para cima como raízes, em vez de galhos, de uma árvore. A classe mais geral e mais abrangente está sempre no topo (a superclasse), enquanto suas descendentes estão localizadas abaixo (as subclasses).

A esta altura, você provavelmente já sabe indicar algumas possíveis subclasses para a superclasse Veículos. Existem diversas classificações que podem ser usadas. Escolhemos subclasses baseadas no ambiente; digamos existem (pelo menos) quatro subclasses:

  * veículos terrestres;
  * veículos aquáticos;
  * veículos aéreos;
  * veículos espaciais. <br>
  
Neste exemplo, discutiremos apenas a primeira subclasse, veículos terrestres. Se desejar, você poderá prosseguir com as demais classes.

Os veículos terrestres podem ser divididos em mais classes, dependendo do método que afetam o solo que percorrem. Portanto, podemos enumerar:

  * veículos com rodas;
  * veículos com esteiras;
  * hovercrafts.

A hierarquia que criamos é ilustrada pela figura.

Observe a direção das setas, pois sempre apontam para a superclasse. A classe mais alta é a exceção, pois não possui sua própria superclasse.


Outro exemplo é a hierarquia presente nos reinos da taxonomia dos animais.

Podemos dizer que todos os animais (nossa classe inicial) pode ser dividida em cinco subclasses:

  * mamíferos;
  * répteis;
  * pássaros;
  * peixes;
  * anfíbios.

Vamos usar a primeira em nossa análise detalhada.

Identificamos as seguintes subclasses:

  * mamíferos selvagens;
  * animais domesticados.


<img width="1120" height="563" alt="image" src="https://github.com/user-attachments/assets/1a93c8fd-06df-4c72-a4c6-ba7de2c429c2" />



### O que é um objeto?

Uma classe (entre outras definições) é um **grupo de objetos**. Um objeto é um **ser pertencente a uma classe**.

Um objeto é uma **representação dos requisitos, traços e qualidades designados a uma classe específico**. Isto pode parecer simples, mas observe as circunstâncias importantes a seguir. Classes formam uma hierarquia.

Isto pode significar que um objeto que pertence a uma classe específica pertence a todas as superclasses ao mesmo tempo. Isto também pode significar que um objeto que pertence a uma superclasse pode não pertencer a nenhuma de suas subclasses.

Por exemplo: qualquer veículo pessoal é um objeto pertencente à classe *veículos com rodas*. Isso também significa que o mesmo carro pertence a todas as superclasses de sua classe inicial; portanto, ele também é um membro da classe veículos.

Seu cão (ou gato) é um objeto presente na classemamíferos domesticados, que significa explicitamente que ele também está presente na classe *animais*.

Cada **subclasse é mais especializada** (ou mais concreta) que sua superclasse. Por outro lado, cada **superclasse é mais geral** (mais abstrata) que qualquer uma de suas subclasses.

Observe que presumimos que uma classe pode ter apenas uma superclasse, mas isso não é necessariamente verdade; discutiremos essa questão em mais detalhes em breve.


# Herança
Vamos definir um dos conceitos fundamentais da programação por objetos, conhecido como **herança**. Qualquer objeto ligado a um nível específico de uma hierarquia de classe herda todas as características (além dos requisitos e qualidades) definido dentro de qualquer uma das superclasses.
A classe inicial do objeto pode definir novas características (além dos requisitos e qualidades) que serão herdadas por qualquer uma de suas subclasses.
Associar essa regra a exemplos específicos é algo simples, não importa se ela se aplica a animais ou a veículos.

<img width="534" height="463" alt="image" src="https://github.com/user-attachments/assets/6fcd91d3-2857-42f1-a501-553db6f96c4d" />


## O que um objeto possui?

A convenção da programação por objetos presume que todo objeto existente pode ser equipado com três grupos de atributos:

  * um objeto possui um nome que o identifica de maneira exclusiva dentro de seu próprio namespace (embora a existência de alguns objetos anônimos também seja possível)
  * um objeto possui um conjunto de propriedades individuais que o tornam original, exclusivo ou o destaca (apesar disso, existem objetos que não possuem nenhuma propriedade)
  * um objeto possui um conjunto de habilidades para desempenhar atividades específicas, capaz de alterar o próprio objeto ou alguns dos outros objetos.

Existe uma dica (embora nem sempre funcione) que pode ajudá-lo a identificar qualquer uma das três esferas acima. Sempre que descrever um objeto e usar:

  * um substantivo: você provavelmente está definindo o nome do objeto;
  * um adjetivo: está definindo a propriedade do objeto;
  * um verbo: a atividade do objeto.

Essas duas frases são bons exemplos:

  * Um Cadillac cor-de-rosa dirigiu velozmente.

Nome do objeto = Cadillac
Classe inicial = Veículos com rodas
Propriedade = Cor (cor-de-rosa)
Atividade = Dirigir (velozmente)

  * Rodolfo é um gato grande que dorme o dia inteiro.

Nome do objeto = Rodolfo
Classe inicial = Gato
Propriedade = Tamanho (grande)
Atividade = Dormir (o dia inteiro)


<img width="1293" height="621" alt="image" src="https://github.com/user-attachments/assets/310822bc-be40-4370-905d-8c89f00ad089" />



### 1° Classe
Uma classe é um modelo de uma parte bastante específica da realidade, que refletem propriedades e atividades presentes no mundo real.
Não existe nenhum obstáculo para definir subclasses novas e mais precisas. Elas herdarão tudo de suas superclasses; sendo assim, o trabalho realizado em sua criação não será perdido.

A nova classe poderá incluir as novas propriedades e novas atividades e, portanto, podem ser mais úteis em aplicações específicas. Obviamente, ela pode ser usada como superclasse para qualquer quantidade de novas classes criadas.
O processo não precisa ter um fim. Você pode criar quantas classes forem necessárias.

A classe que você define não está relacionada ao objeto: a existência de uma classe não significa que algum dos objetos compatíveis será criado automaticamente. 
A classe em si não é capaz de criar um objeto, você terá de criá-lo, ação permitida pelo Python.

Exemplo
```
class TheSimplestClass:
    pass
```

Definimos uma classe. A classe é insuficiente: não possui propriedades ou atividades. Está vazia, na verdade, mas isso não importa no momento. 
Quanto mais simples a classe, melhor ela será para nosso propósito.

A definição começa com a palavra-chave `class`. A palavra-chave é seguida por um **identificador que irá nomear a classe** 
(observação: não o confunda com o nome do objeto – são duas coisas diferentes).

Em seguida, inclua dois-pontos (`:`), pois classes, como funções, formam seus próprios blocos aninhados. O conteúdo dentro desse bloco define todas as propriedades e atividades da classe.

A palavra-chave `pass` preenche a classe com vazio. Ela não inclui nenhum método ou propriedade.

### 1° Objeto
A classe recém-definida se torna uma ferramenta que poderá criar novos objetos. A ferramenta precisa ser usada explicitamente, sob demanda.

Imagine que deseja criar um (exatamente um) objeto da classe `TheSimplestClass`.
Para fazer isso, será necessário designar uma variável para armazenar o objeto criado dessa classe, além de criar um objeto ao mesmo tempo.

Para fazer isso:

```
my_first_object = TheSimplestClass()
```
**Observação**:

  * o nome da classe tenta fingir que é uma função; você consegue enxergar isso? Falaremos disso em breve;
  * o objeto recém-criado é equipado com tudo o que é trazido pela classe: uma vez que a classe está completamente vazia, o objeto também estará vazio.

O ato de criar um objeto da classe selecionada também é conhecido como **instanciação** (pois o objeto se torna uma **instância da classe**).

### RESUMO DA SEÇÃO

1. Uma classe é uma ideia (mais ou menos abstrata) que pode ser usada para criar diversas representações; tais representações são conhecidas como objetos.

2. Quando uma classe é derivada de outra classe, sua relação é chamada de herança. A classe derivada de outra classe é conhecida como subclasse. O outro lado dessa relação é chamado de superclasse. Uma maneira de apresentar essa relação é um diagrama de herança, em que:

  * superclasses são sempre apresentadas acima de suas subclasses;
  * as relações entre classes são indicadas como setas partindo da subclasse em direção à sua superclasse.

3. Objetos são equipados com:

  * um nome que os identifica e permite fazer a distinção de cada um;
  * um conjunto de propriedades (o conjunto pode estar vazio)
  * um conjunto de métodos (também pode estar vazio)

4. Para definir uma classe Python, é necessário usar a palavra-chave `class`. Por exemplo:

```
class This_Is_A_Class:
    pass
```
5. Para criar um objeto da classe definida anteriormente, precisamos usar a classe como se fosse uma função. Por exemplo:

```
this_is_an_object = This_Is_A_Class()
```

