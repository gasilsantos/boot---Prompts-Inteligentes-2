# boot---Prompts-Inteligentes-2
boot - dio - apenai - services
# Aplicações Práticas com Azure OpenAI e Semantic Kernel

Este repositório contém um resumo das aplicações práticas utilizando o Azure OpenAI, com exemplos de chamadas de API e integração com o Semantic Kernel para criar soluções inteligentes e escaláveis.

## Índice

- [Introdução](#introdução)
- [Pré-requisitos](#pré-requisitos)
- [Configuração do Azure OpenAI](#configuração-do-azure-openai)
- [Chamadas de API com Azure OpenAI](#chamadas-de-api-com-azure-openai)
- [Integração com o Semantic Kernel](#integração-com-o-semantic-kernel)
- [Exemplos Práticos](#exemplos-práticos)
- [Considerações Finais](#considerações-finais)
- [Recursos Adicionais](#recursos-adicionais)

## Introdução

O **Azure OpenAI** integra modelos avançados de linguagem natural em aplicativos, possibilitando funcionalidades como:
- Geração de texto
- Resumo automático
- Tradução
- Análise de sentimentos

Combinando o Azure OpenAI com o **Semantic Kernel**, é possível orquestrar funções semânticas, permitindo a criação de fluxos de trabalho que integram múltiplos serviços e aprimoram a inteligência dos sistemas.

## Pré-requisitos

- Conta ativa no [Azure](https://portal.azure.com)
- Chave de API e endpoint do Azure OpenAI
- Ambiente de desenvolvimento configurado para realizar chamadas HTTP/REST (ex.: Postman, cURL ou bibliotecas como `requests` para Python)
- Instalação do Semantic Kernel (conforme a linguagem de desenvolvimento, ex.: .NET via NuGet ou pacotes Python)

## Configuração do Azure OpenAI

1. **Criação do recurso**: No portal do Azure, crie um recurso do Azure OpenAI.
2. **Obtenção da chave de API**: Após a criação, copie a chave de API e o endpoint fornecido.
3. **Segurança**: Configure as políticas de acesso para que somente aplicações autorizadas possam utilizar o serviço.

## Chamadas de API com Azure OpenAI

Utilize as APIs REST do Azure OpenAI para interagir com os modelos. Veja um exemplo em Python:

```python
import requests
import json

# Substitua <seu-endpoint> e <nome-da-deployment> pelos valores correspondentes
endpoint = "https://<seu-endpoint>.openai.azure.com/openai/deployments/<nome-da-deployment>/completions?api-version=2022-12-01"
api_key = "SUA_CHAVE_API_AQUI"
headers = {
    "Content-Type": "application/json",
    "api-key": api_key
}

data = {
    "prompt": "Explique os benefícios da integração do Azure OpenAI com o Semantic Kernel.",
    "max_tokens": 100
}

response = requests.post(endpoint, headers=headers, json=data)
result = response.json()
print(json.dumps(result, indent=2))
