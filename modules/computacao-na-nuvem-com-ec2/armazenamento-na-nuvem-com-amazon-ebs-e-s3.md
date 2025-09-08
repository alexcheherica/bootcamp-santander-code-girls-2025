# ☁️ Amazon EBS (Elastic Block Store)

O **EBS** é um serviço de **armazenamento em blocos** que pode ser anexado a qualquer instância **EC2**.  
Pense nele como um **HD externo** que você conecta na sua máquina virtual (VM).  

## ☁️ Principais pontos:
- Cada instância EC2 já vem com um volume de armazenamento, mas com o EBS conseguimos expandir facilmente com alguns cliques.  
- Podemos escolher o **tamanho e o modelo** de volume conforme a necessidade da aplicação.  

### ☁️ Exemplos de uso:
- Armazenamento de bancos de dados (**MySQL, PostgreSQL, Oracle**).  
- Armazenamento de dados para **aplicações web**.  
- Registro de **logs de sistema**.  

☁️ O **EBS** é indicado quando precisamos de **armazenamento persistente e de alta confiabilidade** diretamente vinculado a uma instância.  

---

# ☁️ Amazon S3 (Simple Storage Service)

Já o **S3** é um serviço de **armazenamento de objetos**.  
Diferente do EBS, ele não fica preso a uma única instância, sendo perfeito para guardar **grandes volumes de dados** de forma segura e escalável.  

## ☁️ Principais pontos:
- Ideal para **organizar, armazenar e recuperar dados** na nuvem.  
- Possui diferentes **classes de armazenamento**, que ajudam a reduzir custos dependendo da frequência de acesso.  
- **Exemplo prático**: hospitais armazenam exames em classes diferentes do S3.  
  - Exames recentes → precisam ser acessados rapidamente.  
  - Exames antigos → podem ser migrados para uma classe mais barata.  
- Podemos configurar **regras de ciclo de vida (Lifecycle)** para que os objetos sejam migrados automaticamente, por exemplo, para a classe **Glacier** (arquivamento de longo prazo e baixo custo).  

---

# ☁️ Conclusão

- **EBS**: armazenamento em blocos, funciona como um HD ligado a uma instância EC2. Ótimo para **bancos de dados** e sistemas que precisam de acesso constante e persistente.  
- **S3**: armazenamento de objetos, super escalável, ideal para **grandes volumes de dados**, com diferentes classes para economizar custos e opções de ciclo de vida para automação.  

☁️ Esses dois serviços juntos mostram como a **AWS** nos dá flexibilidade para armazenar dados de forma **eficiente, escalável e econômica**. 
