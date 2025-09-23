#  Introdução ao Security Group na AWS

##  O que é um Security Group?
Um Security Group é um firewall virtual que controla o tráfego de rede para os recursos da sua VPC, como instâncias EC2.

##  Características principais
- **Stateful**: respostas são automaticamente permitidas
- **Regras de entrada e saída**: definidas separadamente
- **Aplicado por recurso**: cada instância pode ter múltiplos grupos
- **Só permite, não bloqueia**: tudo que não é permitido é bloqueado por padrão

##  Exemplo prático
### Para servidor web:
- Porta: 80
- Protocolo: TCP
- Origem: 0.0.0.0/0

### Para acesso SSH:
- Porta: 22
- Protocolo: TCP
- Origem: IP público do administrador

##  Benefícios
- Segurança reforçada
- Controle granular de acesso
- Flexibilidade para ambientes dinâmicos

##  Conclusão
Security Groups são essenciais para proteger e controlar o acesso aos seus recursos na AWS. Eles te ajudam a manter seu ambiente seguro e sob controle.
