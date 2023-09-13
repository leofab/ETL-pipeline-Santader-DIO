# ETL Pipeline Santander DIO

## Descrição
Este código implementa um pipeline ETL (Extração, Transformação e Carga) para a Santander Dev Week. Ele realiza as seguintes operações:

1. **Importação de IDs de Clientes**:
   - Lê um arquivo CSV contendo IDs de clientes.
   - Converte os IDs em uma lista.

2. **Obtenção de Clientes da API Santander Dev Week**:
   - Utiliza os IDs dos clientes para fazer requisições à API da Santander Dev Week e obter informações sobre os clientes.
   - Filtra e armazena os clientes que foram obtidos com sucesso.

3. **Geração de Conteúdo Personalizado**:
   - Utiliza a API do HuggingFace e o LangChain para gerar conteúdo personalizado para cada cliente com base em sua profissão.

4. **Tradução para Português**:
   - Utiliza modelos de tradução da biblioteca HuggingFace para traduzir o conteúdo gerado para o Português.

5. **Adição de Mensagem Personalizada**:
   - Gera uma mensagem personalizada para cada cliente e a adiciona às informações do cliente.

6. **Atualização de Usuários**:
   - Faz uma requisição PUT para atualizar as informações dos clientes na API da Santander Dev Week.

## Requisitos

- `pandas` para manipulação de dados em formato tabular.
- `requests` para fazer requisições HTTP.
- `json` para manipulação de dados JSON.
- `langchain` para criação de templates de texto.
- `transformers` para trabalhar com modelos de linguagem.
- `sentence_transformers`, `accelerate` e `bitsandbytes` para acelerar o processo de geração de texto.
- `huggingface_hub` para integração com o HuggingFace Model Hub.

## Configuração

- Deve ser fornecida uma chave de API do HuggingFace Hub (`hug_api_key`) para acesso aos modelos de linguagem.

## Execução

- O código é executado sequencialmente, realizando cada etapa do pipeline.

## Notas

- O código assume que o arquivo CSV com os IDs dos clientes está no mesmo diretório do script.
- Certifique-se de que os pacotes Python mencionados estejam instalados para execução bem-sucedida.

---

## Fontes

- [Vídeo - LangChain + HuggingFace's Inference API - no OpenAI credits required!](https://www.youtube.com/watch?v=dD_xNmePdd0)
- [Código no Colab de como fazer a configuração da API geradora de texto](https://colab.research.google.com/drive/18XH8DTbgI4Zrsg-Xat-El3FvL8ZIDXMD?usp=sharing#scrollTo=2PpqSc3cG7jJ)
- [Gpt2 huggingface repo](https://huggingface.co/gpt2)
- [Tradutor ingles-portugues feito na Unicamp](https://huggingface.co/unicamp-dl/translation-en-pt-t5)

Lembre-se de substituir `hug_api_key` com sua própria chave de API do HuggingFace Hub antes de executar o código.
