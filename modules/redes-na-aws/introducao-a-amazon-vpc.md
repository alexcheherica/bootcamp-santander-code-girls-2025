#  Introdução à Amazon VPC

##  O que é a Amazon VPC?
A Amazon VPC (Virtual Private Cloud) é um serviço da AWS que permite criar uma rede virtual privada na nuvem. Você controla totalmente como seus recursos se comunicam entre si e com a internet.

##  Por que usar uma VPC?
- Segurança reforçada
- Isolamento de recursos
- Flexibilidade de configuração

##  Componentes principais

### 1. Sub-redes (Subnets)
- Públicas: acessíveis pela internet
- Privadas: acesso interno apenas

### 2. Tabela de Roteamento
- Define o caminho do tráfego entre sub-redes e para fora da VPC

### 3. Internet Gateway
- Permite acesso à internet para sub-redes públicas

### 4. NAT Gateway
- Permite acesso à internet para sub-redes privadas sem exposição externa

### 5. Security Groups e NACLs
- Firewalls que controlam tráfego de entrada e saída

### 6. Endereçamento IP
- Definido por você usando blocos CIDR

##  O que você pode fazer com uma VPC?
- Hospedar servidores web
- Proteger bancos de dados
- Criar ambientes isolados
- Conectar sua rede local à AWS

##  Conclusão
A VPC é essencial para arquitetar soluções seguras e escaláveis na nuvem. Ela te dá controle total sobre sua infraestrutura virtual!
