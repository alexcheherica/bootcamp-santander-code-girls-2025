#  Gerenciando usuários e permissões na AWS com IAM (Identity and Access Management)

Este documento apresenta os **fundamentos do IAM (Identity and Access Management)**, o serviço da AWS responsável por **gerenciar usuários, grupos, funções e permissões**, garantindo **segurança e controle de acesso** aos recursos da nuvem.

---

##  O que é o IAM?

O **IAM (Identity and Access Management)** é o serviço central da AWS para **controle de identidade e permissões**.
Ele permite definir **quem pode acessar o quê** dentro da sua conta AWS, de forma **granular e segura**.

Com o IAM, é possível:

* Criar e gerenciar **usuários e grupos**.
* Definir **políticas de permissões** baseadas em regras JSON.
* Atribuir **funções (roles)** com permissões temporárias.
* Ativar **autenticação multifator (MFA)** para maior segurança.
* Integrar com **federation (SSO, Active Directory, etc.)**.

---

##  Componentes principais do IAM

1. **Usuários (Users)**

   * Representam **identidades individuais** (ex.: funcionários, desenvolvedores).
   * Podem ter credenciais de acesso à AWS (console, CLI, SDKs).

2. **Grupos (Groups)**

   * Conjunto de usuários que compartilham **permissões comuns**.
   * Exemplo: grupo `Developers` com acesso somente a instâncias EC2 de teste.

3. **Funções (Roles)**

   * Identidades com **permissões temporárias** que podem ser assumidas por **usuários, aplicações ou serviços AWS**.
   * Muito usado para **EC2 acessar S3** ou **Lambda acessar DynamoDB** sem expor credenciais.

4. **Políticas (Policies)**

   * Conjunto de regras em **JSON** que definem as permissões (permitir ou negar ações).
   * Exemplo de política permitindo listar buckets no S3:

     ```json
     {
       "Version": "2012-10-17",
       "Statement": [
         {
           "Effect": "Allow",
           "Action": "s3:ListAllMyBuckets",
           "Resource": "*"
         }
       ]
     }
     ```

---

##  Boas práticas de segurança com IAM

* **Princípio do menor privilégio**: conceda apenas as permissões estritamente necessárias.
* **Use funções (roles) em vez de chaves fixas**: especialmente para aplicações e serviços AWS.
* **Ative MFA (Multi-Factor Authentication)**: para proteger contas críticas (principalmente a conta root).
* **Nunca use a conta root para tarefas do dia a dia**: crie usuários administradores separados.
* **Rotacione credenciais regularmente**: evite uso prolongado de chaves de acesso.
* **Monitore com CloudTrail**: registre quem fez alterações no IAM.

---

##  Exemplo prático

Imagine uma equipe de desenvolvimento que precisa acessar apenas ambientes de **teste** no EC2:

1. Crie um **grupo IAM** chamado `Developers`.
2. Anexe uma **política personalizada** que permite apenas:

   * Iniciar/parar instâncias EC2 em uma VPC de teste.
   * Sem acesso a produção.
3. Adicione os desenvolvedores como **usuários do grupo**.
4. Habilite **MFA** para cada usuário.

Assim, todos têm **acesso controlado**, sem risco de comprometer o ambiente de produção.

---

##  Benefícios do IAM

* Controle **centralizado e seguro** de identidades.
* Permissões **granulares e flexíveis**.
* Suporte a **auditoria e conformidade**.
* Integração com **outros serviços AWS** e diretórios corporativos.
* **Escalabilidade**: do uso individual até grandes organizações.

---

##  Referências

* [AWS IAM – Documentação oficial](https://docs.aws.amazon.com/iam/)
* [Best Practices for IAM Security](https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html)
* [IAM Policy Reference](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies.html)

---
