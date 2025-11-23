# Agente Bancário Generativo com LangGraph e Gemini
Este projeto demonstra a criação de um agente bancário utilizando a biblioteca LangGraph para orquestração de lógica complexa, em conjunto com o modelo de linguagem Gemini 2.5 Flash da Google para processamento e interação. O agente é capaz de consultar saldos e realizar transferências em um sistema bancário simulado, seguindo regras de segurança e contexto.

O projeto utiliza as seguintes bibliotecas:

- **langgraph**: Para criar a arquitetura de agente (ReAct).  
- **langchain** e **langchain-community**: Componentes principais do ecossistema LangChain.  
- **langchain-google-genai**: Para integrar o modelo Gemini.

### Instalação

```bash
pip install -q "langgraph>=1.0.0" "langchain>=0.3.0" "langchain-community>=0.3.0" "langchain-google-genai>=2.0.0"
```

🔑 Configuração da API

É necessário configurar a chave da API do Google no ambiente:
```bash
import os
GOOGLE_API_KEY = os.getenv("GOOGLE_API_KEY")
from langchain_google_genai import ChatGoogleGenerativeAI
```

# Instanciando o LLM
```bash
llm = ChatGoogleGenerativeAI(
    model="gemini-2.5-flash"
)
```

💼 Sistema Bancário Simulado

O sistema utiliza uma lista de dicionários para simular contas bancárias:
```bash
contas = [
    {"nome": "Maria Clara", "cpf": "123.456.789-10", "numeroConta": 1234, "saldo": 200},
    {"nome": "Emilly", "cpf": "456.789.123-20", "numeroConta": 4321, "saldo": 200},
]
```
