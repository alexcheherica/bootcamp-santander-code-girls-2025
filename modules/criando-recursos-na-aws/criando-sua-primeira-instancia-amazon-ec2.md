# 🖥️ Criando o nosso Amazon EC2 – Guia Completo

O Amazon EC2 (Elastic Compute Cloud) é o serviço da AWS que permite criar servidores virtuais na nuvem. Com ele, você pode hospedar aplicações, sites, bancos de dados e muito mais, com escalabilidade e controle total.

---

## 🔧 Passo a Passo para Criar sua Instância EC2

### 1. Acessar o Console AWS
- Entre no [AWS Management Console](https://aws.amazon.com/console/)
- Navegue até o serviço **EC2**

### 2. Iniciar a Criação da Instância
- Clique em **“Launch Instance”**
- Dê um nome à instância (ex: `MeuServidorWeb`)

### 3. Escolher a Amazon Machine Image (AMI)
- Selecione o sistema operacional desejado:
  - Amazon Linux
  - Ubuntu
  - Windows Server

### 4. Selecionar o Tipo de Instância
- Escolha o tipo de máquina:
  - `t2.micro` (gratuito no Free Tier)
  - Tipos maiores para aplicações mais exigentes

### 5. Criar ou Selecionar um Par de Chaves (Key Pair)
- Crie um novo par de chaves ou selecione um existente
- Baixe o arquivo `.pem` e guarde com segurança

### 6. Configurar o Grupo de Segurança
- Defina regras de acesso (firewall):
  - Porta 22 (SSH) para Linux
  - Porta 3389 (RDP) para Windows
  - Porta 80/443 para servidores web

### 7. Revisar e Lançar
- Revise as configurações
- Clique em **“Launch Instance”**

---

##  Acessando sua Instância

### Linux (via SSH)
>bash
ssh -i "minhachave.pem" ec2-user@ip-da-instancia

## 🪟 Windows (via RDP)

Use o Remote Desktop com IP público, usuário e senha para acessar sua instância EC2 com sistema operacional Windows.

---

##  Monitoramento e Gerenciamento

Acompanhe o status da instância no **EC2 Dashboard**.

**Ações disponíveis:**
- Iniciar, parar ou terminar instância
- Monitorar CPU, rede e disco com **CloudWatch**

---

##  Boas Práticas

- Use **tags** para organizar seus recursos
- Configure **alertas com CloudWatch**
- Utilize **Elastic IP** para IP fixo
- Implemente **Auto Scaling** e **Load Balancer** para alta disponibilidade

---

##  Aplicações Comuns

- Hospedagem de sites e APIs
- Ambientes de desenvolvimento/testes
- Servidores de banco de dados
- Processamento de dados

---

> Com esse passo a passo, você já pode criar e gerenciar sua própria instância EC2 na AWS. Compartilhe com quem está começando na nuvem!


