#  Entendendo como funciona o Amazon SNS e SQS na comunicação assíncrona

Este documento explica de forma detalhada o funcionamento do **Amazon SNS (Simple Notification Service)** e do **Amazon SQS (Simple Queue Service)**, dois serviços essenciais da AWS para implementar **comunicação assíncrona** em aplicações distribuídas.

---

##  O que é comunicação assíncrona?

Na comunicação assíncrona, os componentes de um sistema **não precisam interagir ao mesmo tempo**. Ou seja, quem envia a mensagem não precisa esperar que o receptor esteja disponível para processá-la.

Isso garante:

* **Baixo acoplamento** entre os serviços.
* **Escalabilidade**: vários receptores podem processar mensagens em paralelo.
* **Resiliência**: mensagens não se perdem caso o consumidor esteja temporariamente indisponível.

---

##  Amazon SNS (Simple Notification Service)

O **Amazon SNS** é um serviço de **publicação/assinatura (pub/sub)** usado para **enviar mensagens em tempo real** para múltiplos destinatários.

###  Como funciona?

1. Um **publisher** (publicador) envia uma mensagem para um **tópico** do SNS.
2. O **tópico** distribui essa mensagem para todos os **subscribers** (assinantes) configurados.
3. Os assinantes podem ser:

   * Filas do SQS
   * Funções AWS Lambda
   * E-mails, SMS, ou push notifications
   * Endpoints HTTP/HTTPS

###  Exemplo prático:

* Um e-commerce publica em um **tópico SNS** sempre que um pedido é confirmado.
* Os assinantes podem ser:

  * Uma fila SQS para o sistema de faturamento.
  * Uma função Lambda para enviar o e-mail de confirmação.
  * Um endpoint para notificar o aplicativo do cliente.

---

##  Amazon SQS (Simple Queue Service)

O **Amazon SQS** é um serviço de **fila de mensagens** totalmente gerenciado, que garante a **entrega confiável** das mensagens entre sistemas distribuídos.

###  Como funciona?

1. Um **produtor** envia mensagens para uma **fila SQS**.
2. As mensagens ficam armazenadas na fila até que um **consumidor** as leia.
3. Após o processamento, a mensagem pode ser removida da fila.

###  Tipos de fila no SQS:

* **Standard Queue**:

  * Alta taxa de throughput.
  * Pode entregar mensagens mais de uma vez.
  * Ordem **não garantida**.
* **FIFO Queue (First-In-First-Out)**:

  * Mantém a ordem exata de envio.
  * Garante que a mensagem seja entregue **uma única vez**.

###  Exemplo prático:

* No mesmo e-commerce, o sistema de pagamentos envia mensagens para uma fila SQS.
* O sistema de logística consome essas mensagens para iniciar a preparação do envio.

---

##  SNS + SQS: Trabalhando juntos

O SNS e o SQS podem ser usados em conjunto para criar sistemas ainda mais robustos:

* O **SNS** publica a mensagem em um **tópico**.
* Esse tópico está configurado para enviar as mensagens a uma **fila SQS**.
* Um ou mais consumidores processam as mensagens da fila de forma assíncrona.

###  Benefícios dessa combinação:

* Escalabilidade: vários consumidores podem ler da mesma fila.
* Garantia de entrega: mensagens ficam na fila até serem processadas.
* Flexibilidade: múltiplos assinantes (e.g., uma Lambda e uma fila SQS ao mesmo tempo).

---

##  Casos de uso

* **E-commerce**: pedidos confirmados → SNS → notifica SQS (faturamento), Lambda (envio de e-mail), app (notificação push).
* **Processamento em lote**: sistema envia dados para SQS → consumidores processam em segundo plano.
* **Monitoramento**: eventos de erro em aplicações enviam notificações via SNS.

---

##  Conclusão

* O **SNS** é ideal para **notificações em tempo real e fan-out** (vários assinantes ao mesmo tempo).
* O **SQS** é ideal para **processamento confiável e desacoplado** de mensagens.
* Usados em conjunto, permitem construir sistemas **escaláveis, resilientes e distribuídos**.

---

##  Referências

* [Amazon SNS – Documentação oficial](https://docs.aws.amazon.com/sns/)
* [Amazon SQS – Documentação oficial](https://docs.aws.amazon.com/sqs/)
* [Arquitetura orientada a eventos na AWS](https://aws.amazon.com/event-driven-architecture/)
