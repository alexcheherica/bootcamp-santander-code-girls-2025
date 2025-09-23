#  Criando sua Primeira Função com Amazon Lambda

##  O que é o AWS Lambda?
O AWS Lambda é um serviço serverless que executa código sob demanda, sem necessidade de gerenciar servidores. Ideal para automações, APIs e processamento de eventos.

##  Passo a Passo

### 1. Acesse o Console da AWS
- Vá até o serviço “Lambda”

### 2. Clique em “Criar função”
- Escolha “Criar do zero”
- Nomeie sua função
- Selecione o runtime (ex: Python 3.9)

### 3. Defina a Execution Role
- Crie uma role com permissões básicas
- Permite que a função acesse outros serviços

### 4. Escreva o código
```python
def lambda_handler(event, context):
    return {
        'statusCode': 200,
        'body': 'Olá, Lambda!'
    }
