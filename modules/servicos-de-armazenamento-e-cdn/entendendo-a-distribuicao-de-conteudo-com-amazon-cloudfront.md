#  Entendendo a Distribuição de Conteúdo com Amazon CloudFront

O **Amazon CloudFront** é o **serviço de CDN (Content Delivery Network)** da AWS, projetado para entregar conteúdos (sites, vídeos, APIs e arquivos) de forma **rápida, segura e de baixa latência** para usuários em qualquer lugar do mundo.

---

##  O que é o Amazon CloudFront?

* **CDN global** que utiliza uma rede de **Edge Locations** (pontos de presença) espalhados pelo mundo.
* Funciona em conjunto com **origens** como Amazon S3, Amazon EC2, Elastic Load Balancing ou até mesmo servidores on-premises.
* O conteúdo é **cacheado nas Edge Locations**, reduzindo a distância entre usuário e servidor, o que melhora a experiência de acesso.

---

##  Principais Características

* **Baixa latência** → entrega de conteúdo mais rápida.
* **Distribuição global** → mais de 400 pontos de presença em múltiplos países.
* **Integração com AWS** → S3, EC2, ELB, Lambda@Edge.
* **Segurança** → integração com AWS Shield (DDoS Protection) e AWS WAF (Web Application Firewall).
* **Cache dinâmico** → controle avançado de cache com políticas de TTL e invalidação.
* **Suporte a HTTPS** → criptografia com certificados gerenciados pelo ACM.
* **Streaming de vídeo** → otimizado para entregar conteúdo de mídia sob demanda ou ao vivo.

---

##  Conceitos Fundamentais

1. **Distribuição (Distribution)**

   * Configuração principal do CloudFront.
   * Define de onde vem o conteúdo (origem) e como será entregue.

2. **Origem (Origin)**

   * Local onde os dados estão armazenados.
   * Exemplos: bucket S3, instância EC2, servidor HTTP.

3. **Edge Location**

   * Ponto de presença que **cacheia** e entrega conteúdo para usuários próximos.

4. **Objeto (Object)**

   * Arquivo individual distribuído pelo CloudFront (HTML, CSS, JS, imagens, vídeos, etc.).

5. **TTL (Time to Live)**

   * Tempo que um objeto fica armazenado no cache da Edge Location antes de ser atualizado.

---

##  Casos de Uso

* Hospedagem e aceleração de **sites estáticos**.
* Entrega de **vídeos sob demanda** ou **streaming ao vivo**.
* Distribuição de **APIs** de forma global e de baixa latência.
* Proteção de aplicações contra ataques DDoS.
* **E-commerce** → carregamento rápido de páginas e segurança de transações.

---

##  Exemplos Práticos

### Criando uma distribuição no CloudFront (via AWS CLI)

```bash
aws cloudfront create-distribution \
    --origin-domain-name meu-bucket-s3.s3.amazonaws.com
```

### Invalidando o cache (quando um objeto foi atualizado)

```bash
aws cloudfront create-invalidation \
    --distribution-id ABCD1234EFGH56 \
    --paths "/index.html"
```

### Configurando tempo de cache (TTL) em segundos

```json
{
  "DefaultCacheBehavior": {
    "TargetOriginId": "MinhaOrigemS3",
    "ViewerProtocolPolicy": "redirect-to-https",
    "DefaultTTL": 86400,
    "MaxTTL": 31536000,
    "MinTTL": 0
  }
}
```

---

##  Segurança e Boas Práticas

* Use **HTTPS** para todas as distribuições.
* Integre com **AWS WAF** para proteger contra ataques na camada de aplicação.
* Utilize **CloudFront Signed URLs** e **Signed Cookies** para restringir acesso a conteúdos pagos ou privados.
* Combine com **Shield Advanced** para proteção contra DDoS.
* Monitore com **CloudWatch Metrics** e habilite **Access Logs** para auditoria.

---

##  Preços

O custo do CloudFront é baseado em:

* **Transferência de dados** para fora da AWS (por região).
* **Número de requisições** (HTTP/HTTPS).
* **Invalidations** (primeiros 1.000 por mês são gratuitos).
* Recursos adicionais como Lambda@Edge e Field-Level Encryption.

 [Tabela oficial de preços do Amazon CloudFront](https://aws.amazon.com/pt/cloudfront/pricing/)

---

##  Recursos Úteis

* [Documentação Oficial Amazon CloudFront](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/Introduction.html)
* [Guia de Introdução](https://aws.amazon.com/pt/cloudfront/getting-started/)
* [AWS WAF & Shield](https://aws.amazon.com/pt/waf/)

---

##  Conclusão

O **Amazon CloudFront** é essencial para aplicações que exigem **rapidez, disponibilidade e segurança** na entrega de conteúdo.
Com sua rede global de **Edge Locations**, integração com outros serviços AWS e recursos de segurança avançados, o CloudFront é uma solução completa para empresas que desejam otimizar a experiência dos usuários e proteger suas aplicações na nuvem.
