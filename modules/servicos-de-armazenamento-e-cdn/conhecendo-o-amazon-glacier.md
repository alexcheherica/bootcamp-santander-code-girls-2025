#  Conhecendo o Amazon S3 Glacier

O **Amazon S3 Glacier** é um serviço de armazenamento em nuvem da AWS projetado para **arquivamento de dados de longo prazo** com **baixo custo**. É ideal para informações que não precisam ser acessadas com frequência, mas que devem ser mantidas de forma **segura, durável e escalável**.

---

##  O que é o Amazon S3 Glacier?

* Serviço de **armazenamento em objetos**, assim como o S3.
* Voltado para **arquivos de backup e arquivamento** que exigem **acesso raro**.
* Oferece **custos extremamente reduzidos**, em troca de tempos de recuperação mais longos.
* Integrado ao **Amazon S3**, podendo ser utilizado como uma das classes de armazenamento (Glacier e Glacier Deep Archive).

---

##  Principais Características

* **Durabilidade:** projetado para 99,999999999% (11 noves).
* **Segurança:** criptografia em repouso e em trânsito.
* **Baixo custo:** até 80% mais barato do que o S3 Standard.
* **Controle de acesso:** via IAM, Policies e chaves de criptografia (KMS).
* **Escalabilidade:** suporta desde GB até petabytes de dados.
* **Regiões globais:** disponível em diversas regiões AWS.

---

##  Classes de Armazenamento Glacier

O S3 Glacier possui **duas classes principais**, além de opções de recuperação:

1. **S3 Glacier Instant Retrieval**

   * Para dados raramente acessados, mas que precisam de **acesso imediato**.
   * Baixo custo de armazenamento com recuperação rápida.

2. **S3 Glacier Flexible Retrieval** (antigo S3 Glacier)

   * Para dados acessados ocasionalmente, com diferentes tempos de recuperação:

     * **Expedited:** 1 a 5 minutos.
     * **Standard:** 3 a 5 horas.
     * **Bulk:** 5 a 12 horas (mais barato).

3. **S3 Glacier Deep Archive**

   * A classe **mais barata**, ideal para arquivamento de **anos ou décadas**.
   * Recuperação mais lenta (12 a 48 horas).

---

##  Casos de Uso

* Arquivamento de documentos históricos e jurídicos.
* Armazenamento de dados médicos, científicos ou de pesquisa.
* Backups corporativos de longo prazo.
* Logs de auditoria e compliance.
* Arquivos que precisam ser preservados mas raramente consultados.

---

##  Exemplos Práticos

### Enviando arquivo diretamente para Glacier via AWS CLI

```bash
aws s3 cp arquivo.zip s3://meu-bucket-exemplo/ --storage-class GLACIER
```

### Movendo arquivos de um bucket S3 para Glacier (via Lifecycle)

Crie uma **política de ciclo de vida** para migrar objetos antigos:

```json
{
  "Rules": [
    {
      "ID": "MoveToGlacierAfter30Days",
      "Status": "Enabled",
      "Filter": {
        "Prefix": ""
      },
      "Transitions": [
        {
          "Days": 30,
          "StorageClass": "GLACIER"
        }
      ]
    }
  ]
}
```

### Recuperando arquivos do Glacier

1. Solicite a restauração:

```bash
aws s3api restore-object \
  --bucket meu-bucket-exemplo \
  --key arquivo.zip \
  --restore-request '{"Days":7,"GlacierJobParameters":{"Tier":"Standard"}}'
```

2. Após concluído, o arquivo ficará disponível para download por 7 dias.

---

##  Segurança e Boas Práticas

* Configure **IAM Policies** para restringir acessos.
* Utilize **criptografia com SSE-KMS** para maior controle.
* Crie **políticas de ciclo de vida** automáticas para movimentar dados.
* Planeje o tempo de recuperação de acordo com a **classe escolhida**.
* Evite usar Glacier para dados que precisam de acesso frequente.

---

##  Preços

O custo do Amazon S3 Glacier é composto por:

* Armazenamento mensal (GB).
* Solicitações de upload, recuperação e exclusão.
* Transferência de dados (para fora da AWS).
* Recuperação (varia de acordo com o tempo escolhido: Expedited, Standard ou Bulk).

 [Tabela oficial de preços do S3 Glacier](https://aws.amazon.com/pt/s3/pricing/)

---

##  Recursos Úteis

* [Documentação Oficial Amazon S3 Glacier](https://docs.aws.amazon.com/amazonglacier/latest/dev/introduction.html)
* [Classes de Armazenamento S3](https://aws.amazon.com/pt/s3/storage-classes/)
* [AWS CLI Glacier](https://docs.aws.amazon.com/cli/latest/reference/glacier/)

---

##  Conclusão

O **Amazon S3 Glacier** é uma solução poderosa para **armazenamento de baixo custo e longo prazo**, ideal para organizações que precisam preservar grandes volumes de dados com segurança e durabilidade.
Com políticas de ciclo de vida e integração ao Amazon S3, é possível otimizar custos e manter a conformidade de dados sem abrir mão da confiabilidade da AWS.

