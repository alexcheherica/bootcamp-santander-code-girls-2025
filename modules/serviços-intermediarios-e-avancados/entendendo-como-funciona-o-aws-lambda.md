#  Entendendo como funciona o AWS Lambda

O **AWS Lambda** é um serviço de **computação serverless** da Amazon Web Services que permite executar código sem a necessidade de provisionar ou gerenciar servidores. Com ele, você paga apenas pelo tempo de execução do código e pela quantidade de requisições processadas.

---

##  O que é o AWS Lambda?

* Serviço **serverless** (sem servidor visível para o usuário).
* Executa código em resposta a **eventos** (gatilhos).
* Suporta diversas linguagens como **Node.js, Python, Java, Go, C#, Ruby** e **custom runtimes**.
* Escala automaticamente conforme a demanda.

---

##  Principais Características

* **Escalabilidade automática:** dimensiona de acordo com a carga de trabalho.
* **Custo sob demanda:** você paga apenas pelos milissegundos em que o código é executado.
* **Integração nativa:** funciona em conjunto com serviços como S3, DynamoDB, Kinesis, API Gateway, SNS, CloudWatch, entre outros.
* **Gerenciamento simplificado:** sem necessidade de configurar servidores, patches ou balanceamento de carga.
* **Ambiente isolado:** cada função roda em um ambiente seguro e independente.

---

##  Conceitos Fundamentais

1. **Função Lambda (Lambda Function)**

   * O código que será executado.
   * Inclui código + configurações (runtime, memória, permissões).

2. **Evento (Trigger)**

   * A ação que dispara a execução da função.
   * Exemplos: upload em S3, mensagem em fila SQS, chamada de API Gateway.

3. **Handler**

   * Ponto de entrada da função (método executado quando a função é chamada).

4. **Runtime**

   * Ambiente de execução da função (Python, Node.js, Java, etc.).

5. **Execution Role (IAM Role)**

   * Permissões que definem quais recursos AWS a função pode acessar.

6. **Concurrency**

   * Número de execuções simultâneas que a função pode ter.

---

##  Casos de Uso

* Processamento de arquivos enviados ao **S3**.
* Automação de tarefas (ex.: redimensionar imagens, gerar relatórios).
* Backend de aplicações via **API Gateway**.
* Processamento em tempo real de streams (ex.: Kinesis, DynamoDB Streams).
* Integração com **chatbots, IoT** e aplicações event-driven.
* Monitoramento e notificações automáticas.

---

##  Exemplos Práticos

### Exemplo em Python (Hello World)

```python
def lambda_handler(event, context):
    return {
        'statusCode': 200,
        'body': 'Olá, AWS Lambda!'
    }
```

### Criando uma função Lambda via AWS CLI

```bash
aws lambda create-function \
  --function-name hello-lambda \
  --runtime python3.9 \
  --role arn:aws:iam::123456789012:role/lambda-execution-role \
  --handler lambda_function.lambda_handler \
  --zip-file fileb://codigo.zip
```

### Invocando a função Lambda via CLI

```bash
aws lambda invoke \
  --function-name hello-lambda \
  saida.json
```

---

##  Segurança e Boas Práticas

* Conceda permissões mínimas via **IAM Role** (princípio do menor privilégio).
* Monitore logs com **CloudWatch Logs**.
* Utilize **Variáveis de Ambiente** para credenciais e configs sensíveis.
* Evite funções monolíticas → prefira **funções pequenas e específicas**.
* Configure **Dead Letter Queues (DLQ)** para capturar falhas.
* Use **Layers** para compartilhar bibliotecas entre funções.

---

##  Preços

O custo do AWS Lambda é baseado em:

* **Número de requisições** → primeiros 1 milhão por mês são gratuitos.
* **Duração da execução** → medida em milissegundos e quantidade de memória alocada.
* **Serviços integrados** → custo adicional de triggers (ex.: chamadas no API Gateway).

 [Tabela oficial de preços do AWS Lambda](https://aws.amazon.com/pt/lambda/pricing/)

---

##  Recursos Úteis

* [Documentação Oficial AWS Lambda](https://docs.aws.amazon.com/lambda/latest/dg/welcome.html)
* [Exemplos de Código](https://github.com/awsdocs/aws-lambda-developer-guide)
* [AWS Lambda Limits](https://docs.aws.amazon.com/lambda/latest/dg/gettingstarted-limits.html)

---

##  Conclusão

O **AWS Lambda** revoluciona a forma de construir aplicações ao eliminar a necessidade de gerenciar infraestrutura.
Ele é **eficiente, econômico e altamente escalável**, tornando-se uma escolha ideal para arquiteturas **serverless** modernas e aplicações baseadas em eventos.
Com sua ampla integração com serviços da AWS, o Lambda se adapta a diferentes cenários, desde pequenas automações até sistemas corporativos complexos.
