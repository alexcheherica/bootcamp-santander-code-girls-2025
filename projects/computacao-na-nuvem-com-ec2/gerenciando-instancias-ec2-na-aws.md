# ☁️Primeiro Desafio de Projeto - Gerenciamento de Instâncias EC2 na AWS

## Objetivo
Documentar a prática de criação, configuração e gerenciamento de instâncias EC2 na AWS, consolidando os conhecimentos adquiridos nas aulas da DIO.

## Diagrama da Arquitetura

O diagrama abaixo ilustra visualmente os componentes e o fluxo de comunicação:

📁 Localizado na pasta `/images/diagrama-ec2.png`

---

## Aprendizados

- Entendimento prático da estrutura de redes na AWS  
- Criação e configuração de instâncias EC2  
- Aplicação de boas práticas de segurança com Security Groups  

---

##  Recursos Adicionais

- [Documentação EC2 AWS](https://docs.aws.amazon.com/pt_br/AWSEC2/latest/UserGuide/concepts.html)  
- [Guia Markdown GitHub](https://guides.github.com/features/mastering-markdown/)  
- [Draw.io para diagramas](https://draw.io)  


## Visão Geral da Arquitetura

A arquitetura representa o fluxo de comunicação entre um usuário externo e uma aplicação hospedada em uma instância EC2 dentro de uma Subnet Pública em uma VPC. A comunicação é protegida por regras de segurança definidas em um Security Group.

## Fluxo de Comunicação:

Usuário → Internet → Internet Gateway → VPC → Subnet Pública → Instância EC2 → Security Group


---

## Componentes da Arquitetura

| Componente         | Função                                                                 |
|--------------------|------------------------------------------------------------------------|
|  Usuário         | Origem das requisições, acessa a aplicação via navegador ou terminal. |
|  Internet        | Rede pública que conecta o usuário à AWS.                             |
|  Internet Gateway | Permite que recursos dentro da VPC se comuniquem com a internet.     |
|  VPC             | Rede virtual isolada onde os recursos da aplicação são hospedados.    |
|  Subnet Pública  | Sub-rede com acesso à internet, onde está a instância EC2.            |
|  Instância EC2   | Máquina virtual que executa a aplicação ou serviço.                   |
|  Security Group  | Conjunto de regras que controlam o tráfego de entrada e saída.        |



