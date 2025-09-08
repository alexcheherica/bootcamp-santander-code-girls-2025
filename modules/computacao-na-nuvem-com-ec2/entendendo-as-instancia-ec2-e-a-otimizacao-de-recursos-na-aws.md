# ☁️ O que é o Amazon EC2?

O **Amazon Elastic Compute Cloud (EC2)** é basicamente o serviço de máquinas virtuais da AWS.  
Ele permite que a gente rode sistemas operacionais como **Linux ou Windows** na nuvem.  

Cada instância EC2 é composta por:  
- **CPU**  
- **Memória**  
- **Disco (armazenamento)**  
- **Rede**  
- **Sistema Operacional**  

No modelo de nuvem, o EC2 se enquadra no **IaaS (Infraestrutura como Serviço)**.  
Isso significa que a AWS cuida da infraestrutura física e nós ficamos responsáveis pelos **aplicativos, dados e conexões**.  

---

# ☁️ Segurança nas instâncias  

Na criação de uma instância EC2, podemos configurar **grupos de segurança**, que funcionam como um *firewall virtual*.  
Neles definimos:  
- **Protocolos** (TCP, UDP, etc.)  
- **Portas** (ex: 22 para SSH, 80 para HTTP)  
- **Faixas de IPs** que podem acessar a instância  

Isso é essencial para proteger nosso ambiente na nuvem.  

---

# ☁️ Como escolher a instância certa?  

Não é só selecionar qualquer instância, e sim **entender as necessidades da aplicação**.  
A escolha correta ajuda a:  
- Melhorar a **eficiência**  
- **Escalar recursos** quando necessário  
- **Reduzir custos**  

---

# ☁️ Otimização de recursos na AWS  

**Otimizar = economizar custos.** Algumas práticas que aprendi foram:  

1. **Desligar instâncias não utilizadas** – especialmente em ambientes de teste, desenvolvimento e treinamento, onde não é preciso manter ligado à noite ou nos fins de semana.  
2. **Remover recursos ociosos** – muitas vezes criamos e esquecemos, mas cada recurso parado continua gerando cobrança.  
3. **Escalonamento (Scale)** – podemos aumentar ou diminuir a capacidade de forma manual ou automática:  
   - **Vertical**: aumentar CPU, memória ou disco da mesma instância.  
   - **Horizontal**: adicionar novas instâncias ou recursos (ex: outro servidor rodando junto).  

---

# ☁️ Tipos de instâncias EC2  

- **On-Demand**: pagas por hora, ótimas para cargas imprevisíveis e testes.  
- **Reservadas**: mais baratas que as On-Demand, mas exigem contrato de uso (ex: 1 ano).  
- **Spot**: podem ter até **90% de desconto**, mas a AWS pode interromper a qualquer momento (com aviso prévio de 2 minutos).  
