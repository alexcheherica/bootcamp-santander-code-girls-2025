# II Desafio de Projeto - Explorando Workflowas Automatizados com AWS Step Functions

## O que é?  
O **AWS Step Functions** é um serviço da Amazon que permite coordenar vários serviços e atividades em uma sequência organizada de etapas.  
Ele funciona como um **orquestrador de processos**, onde cada parte do fluxo é representada por um **estado**.  

Esse fluxo pode ser escrito em **JSON** ou construído de forma intuitiva pelo **editor visual da AWS**, conectando blocos em um diagrama.  

---

## Como funciona?   
- Os fluxos de trabalho são divididos em **estados (states)**, e cada estado corresponde a uma ação.  
- Você pode criar esse fluxo de maneira **visual** ou descrevê-lo em **JSON**.  
- O Step Functions garante a execução na ordem correta e ainda trata **erros, repetições e caminhos alternativos** de forma automática.  

---

## Principais componentes  
Dentro de um fluxo, cada **estado** possui um papel específico. Os mais usados são:  

- **Task** → Executa uma atividade, como rodar uma função Lambda ou chamar um serviço da AWS.  
- **Choice** → Define decisões condicionais (*se acontecer X → siga por este caminho, caso contrário → siga por outro*).  
- **Wait** → Faz o processo pausar por um período ou até uma data/hora determinada.  
- **Parallel** → Permite rodar várias ramificações ao mesmo tempo e só continua quando todas terminam.  
- **Map** → Repete uma sequência de passos para cada item de uma lista (*semelhante a um loop `for`*).  
- **Pass** → Encaminha dados sem realizar ação, útil para testes ou ajustes.  
- **Fail** → Finaliza o fluxo com status de falha.  
- **Succeed** → Encerra o fluxo com status de sucesso.  

Esses elementos permitem construir desde automações simples até fluxos corporativos altamente complexos.  

---

## Vantagens  
- **Organização**: ajuda a estruturar processos complicados de maneira clara.  
- **Resiliência**: lida automaticamente com erros e repetições.  
- **Integração**: conecta facilmente com outros serviços AWS.  
- **Clareza**: fluxos são fáceis de entender e acompanhar visualmente.  

---

## Exemplos de aplicação 
- Gerenciar pedidos em **lojas online** (pagamento → estoque → envio).  
- Criar pipelines de **machine learning** (coleta de dados → treino → validação).  
- Automatizar processos de **ETL** (extrair → transformar → salvar dados).  

---

## Lições aprendidas  
- O Step Functions elimina a necessidade de códigos extensos para orquestração.  
- A divisão em estados facilita a **manutenção e o entendimento** do processo.  
- Com a integração nativa com serviços como **Lambda, DynamoDB e S3**, as possibilidades de automação aumentam muito.  

---

## Fontes   
- [AWS Step Functions – Documentação Oficial](https://docs.aws.amazon.com/step-functions/)  
- [Guia de Início Rápido AWS Step Functions](https://aws.amazon.com/pt/step-functions/getting-started/)  
