## Testes, testagem e testadores

A resposta é mais simples do que você imagina e um pouco decepcionante também. Python - como você deve ter certeza - é uma linguagem **interpretada**. Isso significa que o código fonte é analisado e executado ao mesmo tempo. Consequentemente, o Python pode não ter tempo para analisar as linhas de código que não estão sujeitas à execução. Como afirma um ditado antigo de desenvolvedor: "é um recurso, não um bug" (não use essa frase para justificar o comportamento estranho do seu código).

Você entende agora por que passar por todos os caminhos de execução é tão vital e inevitável?

Vamos supor que você tenha concluído seu código e que os testes realizados foram bem-sucedidos. Você entrega seu código para os testadores e - felizmente! - eles encontraram alguns bugs. Estamos usando a palavra *"felizmente"* de forma totalmente consciente. Você precisa aceitar que, em primeiro lugar, os testadores são os melhores amigos do desenvolvedor - não trate os bugs que eles descobrem como uma ofensa ou uma doença; e, em segundo lugar, cada bug encontrado pelos testadores é um bug que não afetará os usuários. Ambos os fatores são importantes e merecem atenção.

Você já sabe que seu código contém um bug ou bugs (o último é mais provável). Como você os localiza e como corrige seu código?

### Bug vs. depuração
A medida básica que um desenvolvedor pode usar contra bugs é, sem surpresa, um depurador, enquanto o processo durante o qual os bugs são removidos do código é chamado de **depuração**. 
De acordo com uma piada antiga, a depuração é um jogo de mistério complicado, no qual você é simultaneamente o assassino, o detetive e - a parte mais dolorosa da intriga - a vítima. Você está pronto para desempenhar todos esses papéis? Então você deve armar-se com um depurador.

Um depurador é um software especializado que pode controlar como o programa é executado. Usando o depurador, você pode executar seu código linha a linha, 
inspecionar todos os estados das variáveis e alterar seus valores sob demanda sem modificar o código-fonte, interromper a execução do programa quando 
determinadas condições são ou não atendidas e realizar várias ações outras tarefas úteis.

Podemos dizer que cada IDE está equipado com um depurador mais ou menos avançado. Até o IDLE tem um, embora você possa achar que ele é um pouco complicado e problemático. 
Se você quiser usar o depurador integrado do IDLE, deve ativá-lo usando a entrada “Debug” na barra de menu da janela principal do IDLE. 
É o ponto de partida para todas as instalações de depuração.

Clique aqui para ver as capturas de tela que mostram o depurador IDLE durante uma sessão de depuração simples. 
(Obrigado, Universidade de Kentucky!)

Você pode ver como o depurador visualiza variáveis e valores de parâmetro e observa a pilha de chamadas que mostra a cadeia de invocações 
que leva da função atualmente executada para o nível de intérprete.

Se quiser saber mais sobre o depurador IDLE, consulte a documentação do IDLE. - https://docs.python.org/3/library/idle.html

### Debugando print
Essa forma de depuração, que pode ser aplicada ao seu código usando qualquer tipo de depurador, às vezes é chamada de **depuração interativa**. 
O significado do termo é autoexplicativo: o processo precisa que sua interação (do desenvolvedor) seja realizada.

Algumas outras técnicas de depuração podem ser usadas para detectar bugs. É possível que você não consiga ou não queira usar um depurador (os motivos podem variar). 
Você está desamparado então? De jeito nenhum!

Você pode usar uma das táticas de depuração mais simples e as mais antigas (mas ainda úteis), conhecidas como depuração de impressão. 
O nome fala por si só - basta inserir várias invocações adicionais de print() dentro do código para gerar dados que ilustram o caminho que o código está negociando no momento. 
Você pode gerar os valores das variáveis que podem afetar a execução.

Essas impressões podem gerar textos significativos como "Estou aqui", "Entrei na função `foo()`", "O resultado é `0`" ou podem conter sequências de caracteres legíveis apenas para você. 
Por favor, não use palavras obscenas ou indecentes para esse fim, mesmo que você sinta uma forte tentação - sua reputação pode ser arruinada em um momento se essas travessuras vazarem para o público.

Como você pode ver, esse tipo de depuração não é realmente interativo, ou é apenas em pequena medida, quando você decide aplicar a função `input()` para interromper ou atrasar a execução do código.

Depois que os bugs forem encontrados e removidos, as impressões adicionais poderão ser comentadas ou removidas. Não deixe que eles sejam executados no código final, pois eles podem confundir testadores e usuários e causar um grande carma.
