# ERROS

Vamos analisar algumas constantes específicas, úteis para detectar erros de fluxo:

`errno.EACCES` → Permissão negada

O erro ocorre quando você tenta, por exemplo, abrir um arquivo com o atributo somente leitura para gravação.

`errno.EBADF` → Número de arquivo inválido

O erro ocorre quando você tenta, por exemplo, operar com um fluxo que não foi aberto.

`errno.EEXIST` → Arquivo existe

O erro ocorre quando você tenta, por exemplo, renomear um arquivo com seu nome anterior.

`errno.EFBIG` → Arquivo muito grande

O erro ocorre quando você tenta criar um arquivo maior do que o máximo permitido pelo sistema operacional.

`errno.EISDIR` → É um diretório

O erro ocorre quando você tenta tratar um nome de diretório como o nome de um arquivo comum.

`errno.EMFILE` → Muitos arquivos abertos

O erro ocorre quando você tenta abrir, simultaneamente, mais fluxos do que o número aceitável para o seu sistema operacional.

`errno.ENOENT` → Não existe tal arquivo ou diretório

O erro ocorre quando você tenta acessar um arquivo/diretório não existente.

`errno.ENOSPC` → Não há espaço restante no dispositivo

O erro ocorre quando não há espaço livre na mídia.
A lista completa é muito maior (também inclui alguns códigos de erro não relacionados ao processamento de fluxo).
