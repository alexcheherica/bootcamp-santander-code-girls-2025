#  Entendendo o que é uma Subnet na Amazon VPC

##  O que é uma Subnet?
Uma subnet é uma divisão lógica dentro da sua VPC que organiza e isola recursos. Ela define como os recursos se comunicam entre si e com a internet.

##  Tipos de Subnet
- **Pública**: acesso direto à internet via Internet Gateway
- **Privada**: sem acesso direto à internet, usa NAT Gateway para saída

##  Componentes de uma Subnet
- Bloco de IP (CIDR)
- Zona de disponibilidade
- Tabela de roteamento
- Gateway associado (Internet ou NAT)

##  Benefícios
- Organização por função
- Isolamento de recursos sensíveis
- Alta disponibilidade em múltiplas zonas
- Controle granular de tráfego

##  Conclusão
Subnets são essenciais para criar arquiteturas seguras, escaláveis e bem organizadas na nuvem. Elas te dão controle total sobre como seus recursos se comunicam dentro da VPC.
