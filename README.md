Aí vai **os 2 README completos em Markdown**, prontos pra **copy/paste**, com um “seletor” no topo pra alternar entre **PT-BR** e **EN**.

---

## ✅ `README.md` (PT-BR)


<div align="center">

# 🏋️ GymHabbit — WhatsApp Fitness Challenge Bot

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](./LICENSE)

**🌎 Idioma:** **PT-BR** | [EN](./README.en.md)

</div>

> Bot de WhatsApp para administrar e organizar uma competição de treinos (academia, corrida e esportes em geral), com **metas personalizáveis por participante** e **ranking por desempenho percentual**.

---

## 📸 Preview

<!-- Placeholder para imagem(s) do projeto -->
![GymHabbit Preview](./docs/images/preview.png)

<!-- Outras opções -->
<!-- ![Preview 2](./docs/images/preview-2.png) -->

---

## 🎥 Demo (link/vídeo)

<!-- Placeholder para link demonstrativo -->
- Demo: [coloque-aqui-o-link-da-demo](https://example.com)

<!-- Placeholder para vídeo -->
- Vídeo: [coloque-aqui-o-link-do-video](https://youtube.com/...)

---

## 🚀 Por que esse projeto existe?

Já existe um serviço conhecido chamado **Gym Rats**, mas ele tinha uma limitação importante pra nossa realidade:

- Queríamos uma competição para manter a consistência
- **Nem todo mundo tem a mesma meta** (ex.: 3 dias/semana vs 5 dias/semana)

O **GymHabbit** resolve isso permitindo que cada participante defina sua própria meta semanal.  
A pontuação/ranking é calculada de forma **percentual**, proporcional ao objetivo individual de cada pessoa.

---

## ✨ Como funciona (visão geral)

- O bot roda em um grupo específico do WhatsApp
- Participantes fazem **check-ins** enviando foto com comando na legenda
- O sistema registra e pontua os check-ins no banco
- O ranking pode ser consultado no grupo
- **Todo domingo** o ranking é atualizado automaticamente

---

## 🧩 Features / Comandos

### ✅ `!checkin`
**Como usar:** envie uma **foto** no grupo com a legenda:

```text
!checkin
````

> Importante: sem foto + legenda `!checkin`, o check-in não será contabilizado.

### 🏆 `!rank`

Retorna o **ranking global atual** do desafio no grupo.

---

## 🛠️ Tech Stack

* **n8n** — orquestração de agentes e lógica do fluxo
* **JavaScript** — nodes de código no n8n
* **EvolutionAPI** — API de WhatsApp (entrada via webhook)
* **OpenAI LLMs** — interpretação / automação via IA
* **Supabase (PostgreSQL)** — armazenamento de dados (check-ins, participantes, rankings)
* **Infra** — VPS Hostinger (n8n + EvolutionAPI)

---

## 🏗️ Arquitetura (alto nível)

```text
WhatsApp Group
   │
   ▼
EvolutionAPI (Webhook)
   │
   ▼
n8n (Workflows + JS Code Nodes + LLM)
   │
   ├── Supabase (DB)
   └── Ranking (global + atualização automática semanal)
```

---

## 📦 Setup (instalação rápida)

> A instalação é simples: basta importar **2 arquivos** na sua instância do n8n.

### 1) Pré-requisitos

* Uma instância do **n8n** rodando (local/VPS)
* Uma instância da **EvolutionAPI**
* Um banco de dados (**Supabase** recomendado)
* Uma chave da API da **OpenAI**
* Um grupo do WhatsApp (onde o bot vai operar)

---

## ⚙️ Configuração

### 2) Importar os workflows no n8n

1. Abra sua instância do n8n
2. Vá em **Workflows → Import**
3. Importe os dois arquivos abaixo:

* `./workflows/workflow-1.json` <!-- placeholder -->
* `./workflows/workflow-2.json` <!-- placeholder -->

> Ajuste os nomes/caminhos acima para os arquivos reais do repositório.

---

### 3) Ajustar variáveis / credenciais

Depois de importar, você precisará configurar:

#### ✅ Banco de dados

* Criar e configurar o banco (ou usar Supabase)
* Garantir que as tabelas necessárias existam *(placeholder abaixo)*

📌 **Schema (placeholder):**

* [ ] `participants`
* [ ] `checkins`
* [ ] `weekly_rankings` / `global_rankings` *(ajuste conforme seu modelo)*

> Dica: coloque aqui um link para o arquivo SQL do schema quando você adicionar no repo:
> `./database/schema.sql`

#### ✅ Credenciais do Supabase

* URL do projeto
* Service role key / anon key (conforme seu uso)
* Configuração do node de conexão no n8n

#### ✅ Filtro do grupo (remoteJid)

No node de **Filter**, configure o `remoteJid` do grupo que chega via webhook:

* `remoteJid`: `coloque-aqui-o-remoteJid-do-seu-grupo`

#### ✅ OpenAI API Key

* Configure a credencial no n8n (OpenAI)
* Informe a API KEY no node correspondente

#### ✅ n8n + EvolutionAPI

* Ajustar URLs (base URL) e tokens/credenciais
* Ajustar endpoint do webhook conforme sua instalação

---

## ✅ Como usar

Depois de configurado:

1. Adicione o bot ao grupo do WhatsApp
2. Envie no grupo:

* `!checkin` (com foto + legenda)
* `!rank` (para consultar ranking)

📅 **Obs:** todo domingo o ranking é atualizado automaticamente.

---

## 🧪 Exemplos

### Exemplo de check-in válido

* **Foto** + legenda:

```text
!checkin
```

### Exemplo de consulta de ranking

```text
!rank
```

---

## 🗺️ Roadmap (opcional)

* [ ] Comando `!goal` para definir meta via chat
* [ ] Histórico semanal por participante
* [ ] Mensagens automáticas de incentivo
* [ ] Dashboard web com estatísticas

---

## 🤝 Contribuições

Sugestões e PRs são bem-vindos!
Se tiver alguma ideia de melhoria, abra uma **Issue** ou mande um **Pull Request**.

📌 *Opcional:* adicione um `CONTRIBUTING.md` com padrões de contribuição.

---

## 📝 Licença

Distribuído sob a licença **MIT**.
Veja o arquivo [LICENSE](./LICENSE) para mais detalhes.

---

## 👤 Autor

**Seu Nome Aqui**

* GitHub: [@seuuser](https://github.com/seuuser)
* LinkedIn: [seu-link](https://linkedin.com/in/...)

📫 Contato: [seuemail@exemplo.com](mailto:seuemail@exemplo.com)


## ✅ `README.en.md` (English)

<div align="center">

# 🏋️ GymHabbit — WhatsApp Fitness Challenge Bot

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](./LICENSE)

**🌎 Language:** [PT-BR](./README.md) | **EN**

</div>

> A WhatsApp bot to manage and run fitness challenges (gym, running, sports in general) with **personalized weekly goals per participant** and a **percentage-based ranking**.

---

## 📸 Preview

<!-- Project image placeholder -->
![GymHabbit Preview](./docs/images/preview.png)

<!-- Alternative -->
<!-- ![Preview 2](./docs/images/preview-2.png) -->

---

## 🎥 Demo (link/video)

<!-- Demo link placeholder -->
- Demo: [put-your-demo-link-here](https://example.com)

<!-- Video placeholder -->
- Video: [put-your-video-link-here](https://youtube.com/...)

---

## 🚀 Why this project?

There’s a well-known service called **Gym Rats**, but it had one key limitation for our use case:

- We wanted a challenge to keep ourselves consistent
- **Not everyone has the same weekly goal** (e.g., 3 days/week vs 5 days/week)

**GymHabbit** solves this by allowing each participant to set their own weekly goal.  
The score/ranking is calculated as a **percentage**, proportional to each person’s individual goal.

---

## ✨ How it works (overview)

- The bot runs inside a specific WhatsApp group
- Participants do **check-ins** by sending a photo with a command in the caption
- The system stores and scores check-ins in the database
- The ranking can be requested in the group
- The ranking is **automatically updated every Sunday**

---

## 🧩 Features / Commands

### ✅ `!checkin`
**How to use:** send a **photo** in the group with this caption:

```text
!checkin
````

> Important: without a photo + `!checkin` caption, the check-in won’t be counted.

### 🏆 `!rank`

Returns the **current global ranking** of the challenge in the group.

---

## 🛠️ Tech Stack

* **n8n** — workflow orchestration and core logic
* **JavaScript** — code nodes inside n8n
* **EvolutionAPI** — WhatsApp API (webhook intake)
* **OpenAI LLMs** — AI interpretation / automation
* **Supabase (PostgreSQL)** — data storage (check-ins, participants, rankings)
* **Infra** — Hostinger VPS (n8n + EvolutionAPI)

---

## 🏗️ Architecture (high level)

```text
WhatsApp Group
   │
   ▼
EvolutionAPI (Webhook)
   │
   ▼
n8n (Workflows + JS Code Nodes + LLM)
   │
   ├── Supabase (DB)
   └── Ranking (global + weekly auto update)
```

---

## 📦 Setup (quick install)

> Setup is simple: import **2 files** into your n8n instance.

### 1) Requirements

* A running **n8n** instance (local/VPS)
* A running **EvolutionAPI** instance
* A database (**Supabase** recommended)
* An **OpenAI API key**
* A WhatsApp group (where the bot will run)

---

## ⚙️ Configuration

### 2) Import the workflows into n8n

1. Open your n8n instance
2. Go to **Workflows → Import**
3. Import the following two files:

* `./workflows/workflow-1.json` <!-- placeholder -->
* `./workflows/workflow-2.json` <!-- placeholder -->

> Update the names/paths above to match your actual repository files.

---

### 3) Update variables / credentials

After importing, configure:

#### ✅ Database

* Create/configure your DB (or use Supabase)
* Make sure required tables exist *(placeholder below)*

📌 **Schema (placeholder):**

* [ ] `participants`
* [ ] `checkins`
* [ ] `weekly_rankings` / `global_rankings` *(adjust to your model)*

> Tip: add a link to your schema SQL when you include it in the repo:
> `./database/schema.sql`

#### ✅ Supabase credentials

* Project URL
* Service role key / anon key (depending on usage)
* Configure the DB nodes in n8n

#### ✅ Group filter (remoteJid)

In your **Filter** node, set the WhatsApp `remoteJid` you receive from the webhook:

* `remoteJid`: `put-your-group-remoteJid-here`

#### ✅ OpenAI API Key

* Create/configure the OpenAI credentials in n8n
* Add your API key to the node(s)

#### ✅ n8n + EvolutionAPI

* Set base URLs and tokens/credentials
* Adjust the webhook endpoint for your deployment

---

## ✅ Usage

Once configured:

1. Add the bot to your WhatsApp group
2. Use commands:

* `!checkin` (photo + caption)
* `!rank` (get current ranking)

📅 **Note:** the ranking is automatically updated every Sunday.

---

## 🧪 Examples

### Valid check-in

* **Photo** + caption:

```text
!checkin
```

### Ranking request

```text
!rank
```

---

## 🗺️ Roadmap (optional)

* [ ] `!goal` command to set weekly goal via chat
* [ ] Weekly history per participant
* [ ] Automated motivation messages
* [ ] Web dashboard with stats

---

## 🤝 Contributing

Suggestions and PRs are welcome!
If you have ideas, open an **Issue** or submit a **Pull Request**.

📌 *Optional:* add a `CONTRIBUTING.md` with contribution guidelines.

---

## 📝 License

Released under the **MIT** License.
See [LICENSE](./LICENSE) for details.

---

## 👤 Author

**Your Name Here**

* GitHub: [@FabriciosViana](https://github.com/FabriciosViana)
* LinkedIn: [@FabriciosViana](https://linkedin.com/in/FabriciosViana)

📫 Contact: [Email](mailto:fabricioviana.dev@gmail.com)
