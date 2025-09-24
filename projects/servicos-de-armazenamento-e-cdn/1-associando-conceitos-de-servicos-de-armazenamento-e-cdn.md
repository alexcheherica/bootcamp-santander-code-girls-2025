# II Desafio de Código  – Associando Conceitos de Serviços de Armazenamento e CDN - Serviços de Armazenamento e CDN – S3, Glacier, CloudFront - parte 1


##  Descrição  
Este desafio tem como objetivo relacionar corretamente serviços da AWS com suas respectivas funções.  
A proposta é simples: dado o nome de um serviço, o programa deve retornar sua descrição principal de forma direta e precisa.  

É uma excelente forma de praticar:  
- Lógica condicional (`if`, `elif`)  
- Manipulação de entrada e saída  
- Conhecimento básico sobre serviços da AWS  

---

##  Entrada  
O programa recebe como entrada uma string com o nome de um dos seguintes serviços:  

- **Amazon S3 Versioning**  
- **Amazon CloudFront**  
- **Amazon Glacier**  
- **Amazon S3**  

---

##  Saída  
O programa deve imprimir a descrição correspondente ao serviço informado.  
As descrições devem ser exatamente como listadas abaixo:  

| Serviço              | Descrição                                      |  
|----------------------|-----------------------------------------------|  
| Amazon S3 Versioning | Controle de versões de objetos no S3          |  
| Amazon CloudFront    | CDN para entrega rápida de conteúdo           |  
| Amazon Glacier       | Arquivamento de longo prazo com baixo custo   |  
| Amazon S3            | Armazenamento de objetos na nuvem             |  

---

##  Código Base  

```python
entrada = input()

def descrever_armazenamento(servico):
  if servico == "Amazon S3 Versioning":
    return "Controle de versões de objetos no S3"
  elif servico == "Amazon CloudFront":
    return "CDN para entrega rápida de conteúdo"
  elif servico == "Amazon Glacier":
    return "Arquivamento de longo prazo com baixo custo"
  elif servico == "Amazon S3":
    return "Armazenamento de objetos na nuvem"

print(descrever_armazenamento(entrada))

