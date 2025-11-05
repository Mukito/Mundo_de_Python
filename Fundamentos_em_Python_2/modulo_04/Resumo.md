## RESUMO DA SEÇÃO
1. Um arquivo precisa ser **aberto** antes de poder ser processado por um programa e ele deve ser **fechado** quando o processamento for concluído.

A abertura do arquivo o associa ao **fluxo**, que é uma representação abstrata dos dados físicos armazenados na mídia. O método de processamento do fluxo é chamado de modo de abertura. Existem **três** modos de abertura:

 * **modo de leitura**: são permitidas apenas operações de leitura;
 * **modo de gravação**: são permitidas somente operações de gravação;
 * **modo de atualização**: são permitidas tanto leitura quanto gravação.

2. Dependendo do conteúdo do arquivo físico, podem ser usadas diferentes classes do Python para processar arquivos. Em geral, `BufferedIOBase` é capaz de processar qualquer arquivo, enquanto `TextIOBase` é uma classe especializada dedicada ao processamento de arquivos de texto (ou seja, arquivos que contêm textos visíveis para humanos, divididos em linhas, usando marcadores de nova linha). Portanto, os fluxos podem ser divididos em **binário** e **texto**.


3. A sintaxe da função `open()` é usada para abrir um arquivo:

open(file_name, mode=open_mode, encoding=text_encoding)
A chamada cria um objeto de fluxo e o associa ao arquivo chamado `file_name`, usando o `open_mode` especificado e definindo o `text_encoding` especificado, ou gera uma exceção no caso de erro.

4. Três fluxos **predefinidos** já estarão abertos na inicialização do programa:

 * `sys.stdin` – entrada padrão;
 * `sys.stdout` – entrada padrão;
 * `sys.stderr` – saída de erro padrão.

5. O objeto de exceção `IOError`, criado quando qualquer operação de arquivo falhar (incluindo operações de abertura), contém uma propriedade chamada `errno`, que contém o código de conclusão da ação com falha. Use esse valor para diagnosticar o problema.
