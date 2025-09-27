#  Fundamentos do AWS CloudTrail para Auditoria e Segurança na AWS

Este documento tem como objetivo explicar os **fundamentos do AWS CloudTrail**, mostrando sua importância para **auditoria, governança e segurança** em ambientes AWS.

---

##  O que é o AWS CloudTrail?

O **AWS CloudTrail** é um serviço que **registra e armazena todas as atividades realizadas em sua conta AWS**.
Cada chamada feita para a API da AWS (seja por usuários, funções, serviços ou até automações) é registrada como um **evento**, garantindo **rastreabilidade e auditoria completa**.

Em resumo, o CloudTrail permite responder às perguntas:

* Quem fez a requisição?
* O que foi feito?
* Quando foi feito?
* De onde veio a requisição?

---

##  Como funciona o CloudTrail?

1. **Registro de eventos**

   * O CloudTrail registra ações feitas via **Console AWS, CLI, SDKs e serviços internos**.
   * Exemplo: criação de uma instância EC2, exclusão de um bucket S3, alteração em políticas de IAM.

2. **Entrega de logs**

   * Os eventos podem ser armazenados em **arquivos JSON** dentro de um **bucket S3**.
   * Também podem ser enviados para o **CloudWatch Logs** para análise em tempo real.

3. **Eventos de gerenciamento vs. eventos de dados**

   * **Eventos de gerenciamento**: operações administrativas (ex.: criar/deletar instância EC2, alterar permissões IAM).
   * **Eventos de dados**: operações nos recursos (ex.: leitura de objetos em S3, invocação de função Lambda).

4. **Integração com segurança**

   * Pode ser integrado ao **Amazon Athena** para consultas avançadas em logs.
   * Pode disparar **CloudWatch Events/EventBridge** para automatizar respostas de segurança.

---

##  Casos de uso do CloudTrail

* **Auditoria de conformidade**
  Atender requisitos de **LGPD, GDPR, HIPAA, PCI-DSS**, entre outros, fornecendo trilhas de auditoria completas.

* **Segurança e investigação forense**
  Detectar atividades suspeitas, como logins fora do horário padrão ou tentativas de exclusão de recursos críticos.

* **Governança e monitoramento**
  Garantir que políticas e melhores práticas estão sendo seguidas em toda a organização.

* **Automação de resposta a incidentes**
  Exemplo: se uma chave IAM for criada sem autorização, o CloudTrail registra o evento e o **EventBridge** pode disparar uma ação para desativar a chave imediatamente.

---

##  Exemplo prático

Imagine que um **usuário mal-intencionado** tente excluir um bucket S3 que contém dados sensíveis:

1. O CloudTrail registra a ação:

   * Usuário que executou.
   * Endereço IP de origem.
   * Horário exato.
   * Recurso afetado.

2. O evento é enviado para o **CloudWatch Logs**.

3. Um alarme dispara via **SNS** para notificar a equipe de segurança.

4. Um **Lambda** é acionado automaticamente para recriar a política do bucket e bloquear novos acessos suspeitos.

---

##  Benefícios do CloudTrail

* **Transparência total**: todas as ações são rastreadas.
* **Segurança aprimorada**: permite identificar e reagir a atividades suspeitas.
* **Conformidade**: ajuda a cumprir regulações de segurança e auditoria.
* **Integração com serviços AWS**: funciona junto com **S3, CloudWatch, Athena, EventBridge e GuardDuty**.
* **Histórico completo**: armazena eventos por até **90 dias por padrão**, podendo ser exportados para longo prazo no S3.

---

##  Fluxo resumido

1. Usuário/serviço executa uma ação na AWS.
2. O **CloudTrail** registra o evento.
3. O evento é enviado para **S3** (armazenamento), **CloudWatch Logs** (monitoramento) ou ambos.
4. Alarmes e automações podem ser disparados a partir desses registros.

---

##  Referências

* [AWS CloudTrail – Documentação oficial](https://docs.aws.amazon.com/cloudtrail/)
* [AWS CloudTrail – Página do serviço](https://aws.amazon.com/cloudtrail/)
* [Best Practices for Security Logging in AWS](https://docs.aws.amazon.com/whitepapers/latest/security-logging-best-practices/)

---
