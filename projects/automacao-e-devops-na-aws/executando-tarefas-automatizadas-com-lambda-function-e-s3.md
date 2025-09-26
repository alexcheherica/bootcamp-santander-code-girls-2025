# V Desafio de Projeto - Executando Tarefas Automatizadas com Lambda Function e S3


##  Descrição do Projeto  
Este repositório contém anotações, exemplos e aprendizados adquiridos durante o projeto **Executando Tarefas Automatizadas com AWS Lambda e S3**.  
O objetivo é explorar a integração entre **funções Lambda** e o serviço de armazenamento **Amazon S3**, automatizando tarefas como processamento de arquivos, geração de logs, notificações e muito mais, tudo sem precisar gerenciar servidores.

---

##  O que é o AWS Lambda?  
O **AWS Lambda** é um serviço de computação sem servidor (serverless) que permite executar código em resposta a eventos, como uploads em buckets S3, alterações em bancos de dados, chamadas HTTP via API Gateway, entre outros.  
Você escreve a função, define o gatilho e o Lambda cuida da execução, escalabilidade e gerenciamento.

---

##  O que é o Amazon S3?  
O **Amazon Simple Storage Service (S3)** é um serviço de armazenamento de objetos altamente escalável e seguro.  
É ideal para armazenar arquivos, imagens, logs, backups, dados estáticos e muito mais.  
O S3 pode ser integrado com Lambda para executar ações automáticas quando arquivos são enviados, modificados ou excluídos.

---

##  Integração Lambda + S3  
A integração entre Lambda e S3 permite que funções sejam disparadas automaticamente quando eventos ocorrem em um bucket.  
Exemplos de uso:

- Processar imagens após upload (redimensionar, converter, etc.)  
- Validar ou transformar arquivos CSV antes de armazenar em banco  
- Gerar notificações ou logs quando arquivos são adicionados  
- Criar thumbnails de vídeos ou imagens  
- Indexar documentos para busca

---

##  Estrutura do Projeto  

| Componente | Descrição |
|------------|-----------|
| **Bucket S3** | Armazena os arquivos que disparam eventos |
| **Função Lambda** | Código que será executado automaticamente |
| **Trigger/Event** | Configuração que conecta o evento do S3 à função Lambda |
| **IAM Role** | Permissões que permitem à função Lambda acessar o S3 |

---

##  Fluxo de Implementação  

1. Criar um bucket no Amazon S3  
2. Criar uma função Lambda com a linguagem desejada (ex: Python, Node.js)  
3. Definir a trigger: evento de `PUT` (upload) no bucket  
4. Criar uma role IAM com permissões de leitura/escrita no S3  
5. Testar o fluxo: enviar um arquivo e verificar a execução da função  
6. Monitorar logs no Amazon CloudWatch

---

##  Exemplo de Código (Python)

```python
import json
import boto3

def lambda_handler(event, context):
    s3 = boto3.client('s3')
    
    bucket = event['Records'][0]['s3']['bucket']['name']
    key = event['Records'][0]['s3']['object']['key']
    
    print(f"Arquivo recebido: {key} no bucket {bucket}")
    
    destino = 'bucket-destino'
    s3.copy_object(Bucket=destino, CopySource={'Bucket': bucket, 'Key': key}, Key=key)
    
    return {
        'statusCode': 200,
        'body': json.dumps('Processamento concluído!')
    }
