# I Desafio de Código  – Associando Conceitos de Recursos da AWS - Criando Recursos na AWS – EC2, S3, Lambda - parte 1

##  Descrição
Este projeto tem como objetivo exercitar a lógica de programação utilizando condicionais simples.  
A proposta é criar um programa que receba o nome de um serviço da AWS e retorne sua descrição correspondente de forma objetiva e exata.

Os serviços abordados são:

- **Amazon EC2** – Serviço de máquinas virtuais sob demanda  
- **Amazon S3** – Armazenamento de objetos na nuvem  
- **AWS Lambda** – Executa código sem gerenciar servidores  
- **Amazon Machine Image** – Modelo de instância EC2 pré-configurado  

---

##  Objetivo
Associar corretamente cada recurso da AWS à sua principal função.  
O programa deve receber uma entrada textual e retornar a descrição exata, conforme especificado no enunciado do desafio.

---

##  Exemplos de entrada e saída

| Entrada               | Saída                                         |
|-----------------------|-----------------------------------------------|
| Amazon EC2            | Serviço de máquinas virtuais sob demanda      |
| Amazon S3             | Armazenamento de objetos na nuvem             |
| AWS Lambda            | Executa código sem gerenciar servidores       |
| Amazon Machine Image  | Modelo de instância EC2 pré-configurado       |

---

##  Lógica de Resolução
A solução foi implementada em **Python**, utilizando uma estrutura condicional `if/elif/else`  
para comparar a entrada com os serviços esperados e retornar a saída correspondente.  

O nome da função foi ajustado para `descrever_servico`, conforme exigido pelo sistema de testes.
##  Código Final

```python
entrada = input()

def descreve_servico(servico): 

    if servico == "Amazon EC2":
        return "Serviço de máquinas virtuais sob demanda"
    elif servico == "Amazon S3":
        return "Armazenamento de objetos na nuvem"
    elif servico == "AWS Lambda":
        return "Executa código sem gerenciar servidores"
    elif servico == "Amazon Machine Image":
        return "Modelo de instância EC2 pré-configurado"
    else:
        return "Entrada inválida"

print(descreve_servico(entrada))