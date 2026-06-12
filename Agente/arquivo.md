# Codigo

```python
import os 
from crewai import Agent, Crew, Task

# 1. Configurando a API Key
os.environ["OPENAI_API_KEY"] = "SUA_CHAVE_AQUI"

# 2. Criando o Agente Especialista
assistente = Agent(
    role="Assistente Inteligente",
    goal="Responder de forma clara e precisa às dúvidas do usuário.",
    backstory="Você é um assistente virtual prestativo e muito inteligente.",
    verbose=False    # Desativado para o terminal ficar limpo como um chat
)


print(" Chat iniciado! Digite sua pergunta (ou 'Sair' para encerrar):")

while True:
    pergunta_usuario = input("\nVocê: ")

    if pergunta_usuario.lower() == 'sair':
        print("Assistente: Até logo!")
        break

    # Criando a tarefa dinamicamente com a sua pergunta 
    tarefa = Task(
        description=pergunta_usuario,
        expected_output="Uma resposta direta e naturral para o usuário.",
        agent=assistente
    )

    # Executando a resposta do agente
    crew = Crew(
        agents=[assistente],
        tasks=[tarefa]
    )
    resultado = crew.kickoff()

    print(f"\n Assistente: {resultado}")
```
