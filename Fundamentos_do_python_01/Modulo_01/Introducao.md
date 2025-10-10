### Programa de computador

Imagine que você quer saber a velocidade média que atingiu durante uma longa jornada. Você sabe a distância, você sabe o tempo, você precisa da velocidade.

Naturalmente, o computador poderá calcular isso, mas não está ciente de coisas como distância, velocidade ou tempo. Portanto, é necessário instruir o computador para:

aceitar um número que represente a distância;
aceitar um número que represente o tempo de viagem;
divida o valor anterior pelo último e armazene o resultado na memória;
exibem o resultado (representando a velocidade média) em um formato legível.
Essas quatro ações simples formam um programa. Obviamente, esses exemplos não são formalizados e estão muito longe do que o computador pode entender, 
mas são bons o suficiente para serem traduzidos para um idioma que o computador possa aceitar.


### O que faz uma linguagem?

 * **Alfabeto** - Conjunto de simbolos para criar palavras
 * **Lexis** - (Dicionário) Conjunto de palavras que o idioma oferece (Exemplo: "Computador" - "Cmoptrue". o termo "Chat" esta no inglês e francês mas com significado diferente)
 * **Sintaxe** - Conjunto de Regras (formais ou informais, escritas ou intuitivamente)
 * **Semântica** - Conjunto de Regras (por exemplo, "comi uma rosquinha" faz sentido, mas "uma rosquinha me comeu" não faz)


*Um programa escrito em uma linguagem de programação de alto nível é chamado de código-fonte (em contraste com o código de máquina executado por computadores). Da mesma forma, o arquivo que contém o código-fonte é chamado de arquivo-fonte.*


**Compilação** - O Programa é convertido uma vez, (Deve ser repetido toda vez que modificado) o programa que converte é chamado de compilador ou tradutor.
**Interpretação** - Vc pode traduzir o programa de origem toda vez que ele for execultado. O programa que execulta esse tipo de transformação pe chamado de **interpretador** 

| Aspecto | Compilação | Interpretação |
|------------|------------|---------------|
| Vantagens  | ✅ A execução do código convertido é mais rápida. | ✅ O código pode ser executado imediatamente após ser escrito — não há etapas extras de conversão. |
|            | ✅ Apenas o desenvolvedor precisa ter o compilador — o usuário final pode executar o programa sem ele. | ✅ O código é armazenado na própria linguagem de programação, o que permite executá-lo em diferentes máquinas sem precisar recompilar para cada arquitetura. |
|            | ✅ O código é traduzido para linguagem de máquina e armazenado dessa forma, o que torna mais difícil entendê-lo. Assim, truques e técnicas do programador permanecem em segredo. |    |
|            | 
| Desvantagens | ❌ O processo de compilação pode ser demorado — é necessário recompilar o código após qualquer alteração antes de executá-lo. | ❌ A execução tende a ser mais lenta, já que o código é interpretado em tempo real e o intérprete consome recursos do computador. |
|              | ❌ É preciso ter compiladores específicos para cada plataforma de hardware onde se deseja rodar o programa. | ❌ O desenvolvedor e o usuário precisam ter o intérprete instalado para rodar o programa. |
