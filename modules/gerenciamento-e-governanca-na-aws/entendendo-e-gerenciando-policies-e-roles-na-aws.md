#  Entendendo e Gerenciando Policies e Roles na AWS

Este documento explica em detalhes o que são **Policies (Políticas)** e **Roles (Funções)** no **AWS IAM (Identity and Access Management)**, mostrando como funcionam, como são aplicadas e quais boas práticas seguir para garantir **segurança e governança** na nuvem AWS.

---

##  O que são Policies (Políticas)?

As **Policies** são documentos em **JSON** que definem **permissões** para identidades ou recursos na AWS.
Elas descrevem **quem pode fazer o quê** em quais **recursos**.

Cada política contém:

* **Effect**: se a ação é permitida (`Allow`) ou negada (`Deny`).
* **Action**: as operações que podem ser realizadas (ex.: `s3:PutObject`, `ec2:StartInstances`).
* **Resource**: os recursos aos quais a permissão se aplica (ex.: `arn:aws:s3:::meu-bucket/*`).

###  Exemplo de Policy

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": "s3:ListBucket",
      "Resource": "arn:aws:s3:::meu-bucket"
    }
  ]
}
```

Essa política permite **listar objetos** dentro de um bucket específico no S3.

###  Tipos de Policies

1. **AWS Managed Policies**: criadas e mantidas pela AWS, prontas para uso.
2. **Customer Managed Policies**: criadas pelo próprio usuário/administrador.
3. **Inline Policies**: anexadas diretamente a um usuário, grupo ou role (mais específicas).

---

##  O que são Roles (Funções)?

As **Roles** são **identidades IAM** que não estão ligadas a uma pessoa, mas podem ser **assumidas por usuários, aplicações ou serviços** para obter permissões temporárias.

Elas funcionam como um **“papel”** que alguém ou algo assume para executar ações específicas.

###  Exemplo prático de Role

* Uma instância **EC2** precisa acessar objetos em um bucket S3.
* Em vez de armazenar credenciais dentro da instância, é criada uma **Role com permissões de leitura no S3**.
* A instância **assume a Role** e executa as operações com segurança.

###  Tipos de Roles

1. **Service Roles**: usadas por serviços AWS (ex.: Lambda acessar DynamoDB).
2. **Cross-Account Roles**: permitem acesso entre diferentes contas AWS.
3. **IAM Roles for Federated Users**: usadas em autenticação federada (SSO, Active Directory).

---

##  Relação entre Policies e Roles

* **Policies** definem as permissões.
* **Roles** são identidades que assumem essas permissões.
* **Usuários/Serviços** assumem uma Role para ganhar acesso temporário conforme as regras da Policy.

**Exemplo:**

* Criar uma **Policy** que permite `PutObject` no S3.
* Anexar essa Policy a uma **Role** chamada `S3Uploader`.
* Uma **função Lambda** assume a Role `S3Uploader` e envia arquivos ao bucket.

---

##  Boas práticas de uso

* Sempre aplicar o **princípio do menor privilégio**: conceder apenas o necessário.
* **Preferir Roles a credenciais fixas** (chaves de acesso expostas são um risco).
* Usar **políticas gerenciadas pela AWS** para casos comuns e **customizadas** para necessidades específicas.
* Monitorar o uso de Policies e Roles via **AWS CloudTrail** e **IAM Access Analyzer**.
* Rotacionar permissões temporárias regularmente.

---

##  Benefícios

* **Segurança**: acesso temporário reduz riscos.
* **Escalabilidade**: fácil delegar permissões para múltiplos serviços/usuários.
* **Flexibilidade**: pode ser usado em **multi-conta** e **federation**.
* **Auditoria**: integra-se ao **CloudTrail** para rastrear quem usou determinada Role.

---

##  Referências

* [AWS IAM Policies – Documentação oficial](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html)
* [AWS IAM Roles – Documentação oficial](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles.html)
* [IAM Best Practices](https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html)

---
