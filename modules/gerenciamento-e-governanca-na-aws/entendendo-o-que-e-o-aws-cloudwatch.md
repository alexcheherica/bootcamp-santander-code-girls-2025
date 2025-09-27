#  Entendendo o que é o AWS CloudWatch

Este documento tem como objetivo explicar de forma clara e detalhada o que é o **Amazon CloudWatch**, como funciona e quais são suas principais aplicações dentro da **observabilidade** em ambientes AWS.

---

##  O que é o AWS CloudWatch?

O **Amazon CloudWatch** é um serviço totalmente gerenciado da AWS que fornece **monitoramento e observabilidade** para recursos da nuvem e aplicações.
Ele coleta, analisa e exibe métricas, logs e eventos, permitindo que desenvolvedores, administradores e equipes de operações tenham **visibilidade em tempo real** da infraestrutura e do desempenho de suas aplicações.

---

##  Como o CloudWatch funciona?

O CloudWatch é baseado em três pilares principais:

1. **Métricas (Metrics)**

   * Dados numéricos coletados automaticamente dos serviços AWS (como CPU, memória, latência, uso de disco, etc.).
   * Também é possível criar **métricas personalizadas** enviadas pela própria aplicação.

2. **Logs (Logs)**

   * Armazena, pesquisa e analisa logs de aplicações e serviços.
   * Pode ser integrado ao **CloudWatch Logs Insights**, que permite executar consultas em grandes volumes de logs.

3. **Eventos (Events / EventBridge)**

   * Reage a mudanças no ambiente em tempo real.
   * Exemplo: quando uma instância EC2 é parada, um evento pode disparar uma **função Lambda** para notificar a equipe.

4. **Alarmes (Alarms)**

   * Permitem definir **limiares de alerta** sobre métricas.
   * Exemplo: se a CPU de uma instância EC2 ultrapassar 80%, um alarme pode enviar uma notificação via **SNS** ou acionar **Auto Scaling**.

---

##  Principais funcionalidades

* **Monitoramento de recursos AWS**: EC2, RDS, Lambda, DynamoDB, S3 e muito mais.
* **Monitoramento de aplicações**: coleta métricas de aplicações personalizadas.
* **Dashboards customizados**: permite visualizar métricas e gráficos em tempo real.
* **Alarmes automatizados**: dispara ações como notificações, execução de funções Lambda ou ajuste automático de recursos.
* **Análise de logs**: facilita a identificação de erros, gargalos e comportamentos inesperados.
* **Integração com automação**: pode trabalhar junto com **SNS, SQS, Lambda e Auto Scaling**.

---

##  Exemplo prático de uso

Imagine um **site de e-commerce** hospedado na AWS:

* O CloudWatch coleta métricas de **latência** e **uso de CPU** do servidor EC2.
* Se a CPU ultrapassar **70% por mais de 5 minutos**, um **alarme é disparado**.
* Esse alarme pode:

  * Notificar a equipe via **SNS (e-mail ou SMS)**.
  * Acionar o **Auto Scaling**, criando uma nova instância automaticamente.
* Os **logs do servidor** ficam no **CloudWatch Logs**, permitindo analisar possíveis erros em transações.

---

##  Benefícios

* **Visibilidade centralizada**: tudo em um único painel.
* **Proatividade**: identificação e correção de problemas antes que afetem os usuários.
* **Escalabilidade**: funciona em pequenos projetos até arquiteturas complexas.
* **Custo-efetivo**: paga apenas pelo que usar (quantidade de métricas, logs e alarmes).
* **Integração com todo o ecossistema AWS**.

---

##  Fluxo resumido de funcionamento

1. Recursos AWS ou aplicações **enviam métricas e logs** para o CloudWatch.
2. O CloudWatch **armazena e analisa** os dados.
3. **Dashboards e relatórios** exibem a saúde e o desempenho do sistema.
4. **Alarmes e eventos** podem **acionar ações automáticas** para corrigir problemas.

---

##  Referências

* [Amazon CloudWatch – Documentação oficial](https://docs.aws.amazon.com/cloudwatch/)
* [Visão geral do CloudWatch na AWS](https://aws.amazon.com/cloudwatch/)
* [CloudWatch Logs Insights](https://docs.aws.amazon.com/AmazonCloudWatch/latest/logs/AnalyzingLogData.html)

---
