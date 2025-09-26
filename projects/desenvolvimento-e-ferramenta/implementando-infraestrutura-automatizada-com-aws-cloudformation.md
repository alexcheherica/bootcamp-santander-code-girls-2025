# IV Desafio de Projeto - Implementando Infraestrutura Automatizada com AWS CloudFormation  


##  Descrição do Projeto  
Este repositório reúne anotações, práticas e aprendizados adquiridos durante o desafio **Implementando Infraestrutura Automatizada com AWS CloudFormation**.  
O objetivo é aplicar os conceitos de **Infraestrutura como Código (IaC)** utilizando o serviço **AWS CloudFormation**, que permite criar, configurar e gerenciar recursos na nuvem de forma automatizada e segura.

---

##  O que é o AWS CloudFormation?  
O **AWS CloudFormation** é um serviço que permite definir e provisionar infraestrutura na AWS por meio de arquivos de template escritos em **JSON** ou **YAML**.  
Esses templates descrevem os recursos desejados (como instâncias EC2, buckets S3, roles IAM, etc.), permitindo que sejam criados de forma **repetível, versionável e auditável**.

---

##  Benefícios principais  
- **Automação**: elimina a necessidade de configurar recursos manualmente  
- **Consistência**: garante que ambientes sejam criados de forma padronizada  
- **Escalabilidade**: facilita a replicação de ambientes em diferentes regiões ou contas  
- **Segurança**: permite aplicar configurações seguras e controladas via código  
- **Auditoria**: possibilita versionar e rastrear alterações na infraestrutura

---

##  Estrutura básica do CloudFormation  

| Componente | Descrição |
|------------|-----------|
| **Template** | Arquivo JSON ou YAML que define os recursos e configurações |
| **Stack** | Conjunto de recursos criados a partir de um template |
| **Resources** | Elementos da AWS que serão provisionados (ex: EC2, S3, RDS) |
| **Parameters** | Valores dinâmicos que podem ser passados ao template |
| **Outputs** | Informações retornadas após a criação da stack (ex: IP da instância) |
| **Mappings** | Tabelas estáticas usadas para configurar valores com base em condições |
| **Conditions** | Permite criar recursos com base em critérios específicos |

---

##  Fluxo prático de uso  

1. Acesse o console da AWS e selecione o serviço **CloudFormation**  
2. Clique em **Create Stack**  
3. Escolha entre subir um template pronto ou usar o **Designer** para criar visualmente  
4. Defina os parâmetros necessários (ex: tipo de instância EC2, nome do bucket)  
5. Revise e confirme a criação da stack  
6. Acompanhe o progresso e o status da criação dos recursos  
7. Utilize o recurso de **Rollback** em caso de falhas

---

##  CloudFormation vs Terraform  

| Ferramenta         | Características                                                                 |
|--------------------|----------------------------------------------------------------------------------|
| **AWS CloudFormation** | Serviço nativo da AWS, altamente integrado, ideal para ambientes exclusivamente AWS |
| **Terraform**          | Ferramenta de IaC multi-cloud, com maior flexibilidade e suporte a diversos provedores |

---

##  Insights adquiridos durante o projeto  

- Templates em **YAML** são mais legíveis, mas o **JSON** também é suportado  
- O uso de **Stacks** facilita a organização e o gerenciamento de recursos relacionados  
- CloudFormation é ideal para ambientes **AWS-only**, com integração nativa e suporte oficial  
- A reutilização de templates reduz erros humanos e acelera o provisionamento  
- É possível versionar templates com Git e aplicar boas práticas de DevOps  
- O Designer é útil para iniciantes, mas templates manuais oferecem mais controle

---

##  Fontes de estudo  

- [Documentação oficial do AWS CloudFormation](https://docs.aws.amazon.com/cloudformation/)  
- Getting Started com CloudFormation  
- Vídeos da AWS Brasil no YouTube  
- Aulas práticas do bootcamp DIO

