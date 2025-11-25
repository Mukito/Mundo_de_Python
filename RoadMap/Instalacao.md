# Introdução

## O que é Flet 
Flet é um framework que permite criar aplicações web, desktop e mobile em Python sem experiência prévia em desenvolvimento frontend.

Você pode criar uma interface de usuário para seu programa com os controles Flet , baseados no Flutter do Google. O Flet vai além de simplesmente encapsular widgets do Flutter. Ele adiciona seu toque pessoal combinando widgets menores, simplificando complexidades, implementando as melhores práticas de interface do usuário e aplicando valores padrão adequados. Isso garante que seus aplicativos tenham uma aparência elegante e refinada sem exigir esforços adicionais de design da sua parte.

Ambiente Virtual
```
md projeto
cd projeto
py -m venv .venv
.venv\Scripts\activate

```
Ambiente Virtual Ativado `(.venv)`

Agora pode a instalação do **Flet**

Win
```
pip instal flet
```
versão
```
flet --version
```

# Criando um aplicativo FLET
venv
```
flet create
```
O comando criará a seguinte estrutura de diretórios:
```
├── README.md
├── pyproject.toml
├── src
│   ├── assets
│   │   └── icon.png
│   └── main.py
└── storage
    ├── data
    └── temp

```
>**OBSERVAÇÃO**
>1. O original `pyproject.toml` foi criado por `uv init` ou `poetry init` será substituído pelo modelo do aplicativo Flet.
>2. Caso encontre o erro `Error creating the project from a template: 'git' is not installed.`, significa que você não tem o *Git* instalado. Acesse git-scm.com/downloads e instale a versão mais recente do *Git* . Para verificar a instalação, digite o seguinte comando gitno terminal: `git checkout`. Observe que o Git não é o mesmo que o GitHub CLI , que não é uma alternativa para uso com o Flet.


# Create

Este comando é usado para criar um novo aplicativo Flet a partir de um modelo.
```
usage: flet create [-h] [-v] [--project-name PROJECT_NAME] [--description DESCRIPTION] [--template {app,extension}] output_directory

Create a new Flet app from a template.

positional arguments:
  output_directory      project output directory

options:
  -h, --help            show this help message and exit
  -v, --verbose         -v for detailed output and -vv for more detailed
  --project-name PROJECT_NAME
                        project name for the new Flet app
  --description DESCRIPTION
                        the description to use for the new Flet project
  --template {app,extension}
                        template to use for new Flet project; the default is app
```

# Execultando

Para executar o aplicativo Flet como um aplicativo de desktop, use o seguinte comando:
```
flet run
```

na Web
```
flet run --web [script]
```

# Run

Este comando é usado para executar um aplicativo Flet no modo de recarregamento a quente.
```
usage: flet run [-h] [-v] [-p PORT] [--host HOST] [--name APP_NAME] [-m] [-d] [-r] [-n] [-w] [--ios] [--android] [-a ASSETS_DIR] [--ignore-dirs IGNORE_DIRS] [script]

Run Flet app.

positional arguments:
  script                path to a Python script

options:
  -h, --help            show this help message and exit
  -v, --verbose         -v for detailed output and -vv for more detailed
  -p PORT, --port PORT  custom TCP port to run Flet app on
  --host HOST           host to run Flet web app on. Use "*" to listen on all IPs.
  --name APP_NAME       app name to distinguish it from other on the same port
  -m, --module          treat the script as a python module path as opposed to a file path
  -d, --directory       watch script directory
  -r, --recursive       watch script directory and all sub-directories recursively
  -n, --hidden          application window is hidden on startup
  -w, --web             open app in a web browser
  --ios                 open app on iOS device
  --android             open app on Android device
  -a ASSETS_DIR, --assets ASSETS_DIR
                        path to assets directory
  --ignore-dirs IGNORE_DIRS
                        directories to ignore during watch. If more than one, separate with a comma.
```


