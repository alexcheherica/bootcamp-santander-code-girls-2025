# I Desafio de Código  – Associando Conceitos de Recursos da AWS - Criando Recursos na AWS – Lambda, Funções, Triggers - parte 2

##  Descrição
Este projeto tem como objetivo reforçar os conceitos fundamentais do serviço **AWS Lambda**,  
uma solução *serverless* da Amazon Web Services que permite executar funções sob demanda,  
sem necessidade de gerenciar servidores.

O desafio consiste em associar corretamente termos técnicos usados no contexto do Lambda  
às suas definições exatas.

---

##  Objetivo
Receber como entrada o nome de um termo relacionado ao **AWS Lambda** e retornar sua definição correspondente, conforme especificado no enunciado.

---

##  Exemplos de entrada e saída

| Entrada          | Saída                                      |
|------------------|--------------------------------------------|
| Lambda Function  | Função executada automaticamente na AWS    |
| Trigger          | Evento que dispara uma execução Lambda      |
| Runtime          | Ambiente de execução da função              |
| Execution Role   | Permissões para a função acessar serviços   |

---

##  Lógica de Resolução
A solução foi implementada em **Python**, utilizando uma função chamada `descrever_lambda_termo`  
que compara a entrada com os termos esperados e retorna a descrição correspondente.  

O código utiliza estrutura condicional `if/elif/else` e garante que a saída seja exatamente igual à exigida pelo sistema de testes.


##  Código Final

```python
entrada = input()

def descrever_lambda_termo(termo):
    if termo == "Lambda Function":
        return "Função executada automaticamente na AWS"

    elif termo == "Trigger":
        return "Evento que dispara uma execução Lambda"

    elif termo == "Runtime":
        return "Ambiente de execução da função"

    elif termo == "Execution Role":
        return "Permissões para a função acessar serviços"

    else:
        return "Entrada inválida"

print(descrever_lambda_termo(entrada))

