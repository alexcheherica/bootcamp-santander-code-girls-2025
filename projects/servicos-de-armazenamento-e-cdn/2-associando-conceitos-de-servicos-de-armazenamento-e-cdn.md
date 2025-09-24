# II Desafio de Código  – Associando Conceitos de Serviços de Armazenamento e CDN -  Serviços de Armazenamento e CDN – Ciclo de Vida, Replicação, Cache - parte 2

##  Descrição  
Este desafio tem como objetivo relacionar corretamente termos técnicos da AWS com suas respectivas definições.  
A proposta é simples: dado o nome de um recurso ou configuração, o programa deve retornar sua descrição principal de forma direta e precisa.  

É uma excelente forma de praticar:  
- Estruturas condicionais (`if`, `elif`)  
- Manipulação de entrada e saída  
- Conhecimento básico sobre recursos de armazenamento e distribuição de conteúdo na AWS  

---

##  Entrada  
O programa recebe como entrada uma string com um dos seguintes termos:  

- **Lifecycle Policy**  
- **Cross-Region Replication**  
- **Cache Behavior**  
- **Storage Class**  

---

##  Saída  
O programa deve imprimir a descrição correspondente ao termo informado.  
As descrições devem ser exatamente como listadas abaixo:  

| Termo                  | Descrição                                   |  
|-------------------------|---------------------------------------------|  
| Lifecycle Policy        | Regras para mover ou excluir arquivos       |  
| Cross-Region Replication| Replica objetos S3 em outra região          |  
| Cache Behavior          | Define como o CloudFront armazena conteúdo  |  
| Storage Class           | Define o tipo de armazenamento no S3        |  

---

##  Código Base  

```python
entrada = input()

def descrever_politica(servico):
  if servico == "Lifecycle Policy":
    return "Regras para mover ou excluir arquivos"
  elif servico == "Cross-Region Replication":
    return "Replica objetos S3 em outra região"
  elif servico == "Cache Behavior":
    return "Define como o CloudFront armazena conteúdo"
  elif servico == "Storage Class":
    return "Define o tipo de armazenamento no S3"

print(descrever_politica(entrada))
