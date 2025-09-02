# ☁️ Resumo -  Primeiros Passos com Acesso Seguro e Controle de Custos na AWS

## 🛠️ Hands-On (Prática) — Explicando os Conceitos

### 💰 Controle de gastos e alertas
Isso significa acompanhar quanto está sendo consumido na sua conta AWS.  
A plataforma oferece ferramentas para definir limites de gastos e receber notificações quando os custos começam a subir.  
É como colocar um alarme no seu cartão de crédito para não gastar além do planejado.

---

### 🔐 IAM (Identity and Access Management)
É o sistema da AWS que permite controlar **quem pode acessar o quê**.  
Com ele, você cria usuários (como se fossem perfis) e define exatamente o que cada um pode fazer.  
Por exemplo, um usuário pode ter permissão só para visualizar dados, enquanto outro pode criar ou apagar recursos.  
É como dar chaves diferentes para cada pessoa numa empresa.

---

### 🧭 Formas de acesso à AWS

- **AWS CLI:**  
  Ferramenta de linha de comando, usada por quem prefere digitar comandos em vez de usar interface gráfica.  
  Ideal para automações e tarefas rápidas.

- **Cloud Shell:**  
  Terminal que roda direto no navegador, sem precisar instalar nada.  
  Já vem com várias ferramentas prontas para usar.

- **Console AWS:**  
  Interface visual da AWS, acessada pelo navegador.  
  É onde você clica em botões e navega por menus para gerenciar seus serviços.

---

### 🤖 Automação com script `bash scriptIAM.sh usuarios.csv`
Esse é um exemplo de automação.  
Um **script** é um conjunto de instruções que o computador executa automaticamente.  
Neste caso, o script lê um arquivo CSV (tipo uma planilha com nomes e dados) e cria usuários e grupos no IAM de forma rápida.  
Em vez de fazer isso manualmente, o script faz tudo de uma vez só.


