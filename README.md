# n8n

---

## 🔰 Beginner Level

### ✅ 1. What is n8n?

* Open-source alternative to Zapier, Make
* Enables automation workflows with 300+ integrations
* Visual low-code editor + custom JS nodes

### ✅ 2. Getting Started

* **Installation**

  * Local: `npx n8n`
  * Docker: `docker run -it --rm -p 5678:5678 n8nio/n8n`
  * Cloud: [n8n.cloud](https://n8n.io)

* **Basic UI Concepts**

  * Nodes
  * Triggers (Webhooks, Schedulers, Events)
  * Execution flow
  * Manual vs. production mode

### ✅ 3. First Workflows

* Use examples like:

  * RSS → Telegram
  * Google Sheets → Email
  * Twitter → Notion

---

## 🧠 Intermediate Level

### ✅ 4. Core Features

* **Data Handling**

  * Expressions and dynamic values
  * JSON structure understanding
  * Item looping

* **Built-in Nodes**

  * Webhook
  * HTTP Request
  * Set / IF / Switch / Merge
  * Function (JavaScript logic)

### ✅ 5. Authentication & API

* OAuth2 setup
* API token headers in HTTP Request
* Pagination handling

### ✅ 6. Trigger Workflows

* Webhook Trigger
* Schedule Trigger (cron jobs)
* Polling vs Push-based

---

## 🔧 Advanced Level

### ✅ 7. Custom JavaScript

* Use **Function** and **FunctionItem** nodes
* Transform, filter, and manipulate data

```js
return items.map(item => {
  item.json.fullName = `${item.json.firstName} ${item.json.lastName}`;
  return item;
});
```

### ✅ 8. Building Complex Workflows

* Nested workflows
* Error handling (Try/Catch equivalent)
* Conditional branching (IF, Switch, Merge)

### ✅ 9. Self-hosting & DevOps

* Docker + Postgres + Redis
* Running on DigitalOcean, AWS, or VPS
* Setting up environment variables

### ✅ 10. Production Best Practices

* Git versioning with workflows as code
* Encryption & security (API keys, secrets)
* Audit logs, access control (with n8n Enterprise)

---

## 💼 Use Cases (Projects to Try)

* ✅ Email parser + database entry
* ✅ CRM to Slack notifications
* ✅ Stripe → Notion for sales tracking
* ✅ Auto-post to Twitter, LinkedIn from RSS feed
* ✅ AI integration using OpenAI API (prompt → reply → email)

---

## 📚 Resources

* [Official Docs](https://docs.n8n.io)
* [n8n YouTube](https://www.youtube.com/c/n8n-io)
* [Awesome-n8n repo](https://github.com/teambit/awesome-n8n)
* [n8n Templates](https://n8n.io/workflows/)



Here’s a refined version for your content:

---

### ✅ 1. What is **n8n**?

* 🧩 **Open-source workflow automation tool** – a powerful alternative to Zapier and Make.com
* 🔗 **Connects 300+ apps** (APIs, services, databases) to automate repetitive tasks
* 🧠 **Visual low-code editor** – drag & drop nodes to create custom workflows
* ✍️ Supports **JavaScript logic** via Function nodes for advanced data manipulation
* 🛠️ Can be **self-hosted or used in the cloud** (n8n.cloud)


Here's a clean and clear explanation for ✅ **2. Getting Started** with **n8n**:

---

### ✅ 2. Getting Started

#### 🔧 **Installation Options**

Choose one of the following methods to run n8n:

* **Local (via NPX)**:

  ```bash
  npx n8n
  ```

  Runs n8n in your terminal locally.

* **Docker**:

  ```bash
  docker run -it --rm -p 5678:5678 n8nio/n8n
  ```

  Spins up n8n in an isolated container at `http://localhost:5678`.

* **Cloud (hosted)**:
  Use the managed version at [n8n.cloud](https://n8n.io) — no setup required.

---

#### 🧭 **Basic UI Concepts**

* **Nodes**:
  Building blocks that represent actions (e.g., HTTP request, Google Sheets, Send Email).

* **Triggers**:
  Special nodes that start workflows. Common types:

  * **Webhooks**: Listen to HTTP requests
  * **Schedules**: Run workflows at specific times
  * **Events**: React to external system changes

* **Execution Flow**:
  The path data takes through connected nodes from start to finish.

* **Manual vs Production Mode**:

  * **Manual**: For testing workflows step-by-step.
  * **Production**: Automatically runs workflows on trigger in background.

<img width="1024" height="1024" alt="ChatGPT Image Jul 14, 2025, 08_29_17 AM" src="https://github.com/user-attachments/assets/8921005e-ed11-4553-9a25-4e87f87bc9ab" />

Here’s a clean explanation for ✅ **4. Core Features** of n8n:

---

### ✅ 4. Core Features

#### 📦 **Data Handling**

Master how data flows between nodes:

* **Expressions & Dynamic Values**
  Use `{{ $json["key"] }}` to inject data from previous steps dynamically.

* **JSON Structure Understanding**
  All node data is passed in JSON format — understanding this helps with mapping, filtering, and transformations.

* **Item Looping**
  Each node processes items in an array — loops automatically unless you use `SplitInBatches`, `Merge`, etc.

---

#### 🧰 **Built-in Nodes (Power Tools)**

* **Webhook**
  Receive data from external apps or form submissions.

* **HTTP Request**
  Make GET/POST/PUT/etc. API calls to any external service.

* **Set**
  Define or modify fields.

* **IF / Switch / Merge**
  Add conditional logic, route flows, and combine multiple branches.

* **Function**
  Add custom JavaScript logic to manipulate data directly.

Here’s a clear and concise explanation for ✅ **5. Authentication & API** in n8n:

---

### ✅ 5. Authentication & API

#### 🔐 **OAuth2 Setup**

* Use **Credential Types** in n8n to configure OAuth2.
* Supports services like Google, Notion, GitHub, etc.
* Automatically handles token refresh and scopes.

#### 🔑 **API Token in HTTP Request**

* In **HTTP Request Node**, go to **Authentication** tab.
* Choose **Header Auth**, and set:

  * Key: `Authorization`
  * Value: `Bearer YOUR_API_TOKEN`

#### 🔄 **Pagination Handling**

* Use **"Pagination" options** in built-in nodes (e.g., Notion, Airtable).
* For custom APIs:

  * Loop using `While`, `IF`, or `Function` nodes.
  * Use query params like `?page=2` or `?offset=XYZ`.

Here’s a crisp explanation for ✅ **7. Custom JavaScript** in n8n’s advanced section:

---

## 🔧 Advanced Level

### ✅ 7. Custom JavaScript

#### 🧠 Power-Up with Code

* **Function Node**
  Processes the **entire input array** at once.
  Example:

  ```js
  return items.map(item => {
    item.json.total = item.json.price * item.json.qty;
    return item;
  });
  ```

* **FunctionItem Node**
  Runs **per item** — useful for transforming single entries.
  Example:

  ```js
  item.json.fullName = item.json.first + " " + item.json.last;
  return item;
  ```

#### 🔄 Use Cases

* Data cleaning (e.g. remove nulls)
* Calculations (e.g. totals, tax)
* API response reshaping
* Custom filtering/logic

Here’s a concise explanation for ✅ **8. Building Complex Workflows** in **n8n**:

---

### ✅ 8. Building Complex Workflows

#### 🔁 **Nested Workflows**

* Use the **Execute Workflow** node to call reusable sub-workflows.
* Helps modularize and reuse logic across projects.

#### 🛠️ **Error Handling (Try/Catch)**

* Enable **"Continue on Fail"** in nodes.
* Use **Error Trigger** node or **IF node** to route based on error.
* Combine with **Merge** to unify main + error paths.

#### 🔀 **Conditional Branching**

* **IF Node**: Basic true/false split based on data (e.g., `status === "active"`).
* **Switch Node**: Route data to multiple paths (e.g., by type or source).
* **Merge Node**: Rejoin multiple branches after conditional logic.


Here’s a clean and clear explanation for ✅ **9. Self-hosting & DevOps** in **n8n**:

---

### ✅ 9. Self-hosting & DevOps

#### 🐳 **Docker + Postgres + Redis**

* Use `docker-compose` to run n8n with dependencies:

  ```yaml
  services:
    postgres:
      image: postgres
    redis:
      image: redis
    n8n:
      image: n8nio/n8n
      ports:
        - 5678:5678
      environment:
        - DB_TYPE=postgresdb
        - DB_POSTGRESDB_HOST=postgres
        - QUEUE_MODE=redis
        - REDIS_HOST=redis
  ```

#### ☁️ **Cloud Deployment**

* Works great on:

  * **DigitalOcean** (1-Click App or Droplet)
  * **AWS EC2** (via Docker or AMI)
  * **Any VPS** with Docker installed

#### 🔐 **Environment Variables**

* Use `.env` or set in `docker-compose.yml`
* Common vars:

  * `N8N_BASIC_AUTH_USER` / `PASSWORD`
  * `WEBHOOK_TUNNEL_URL`
  * `EXECUTIONS_MODE=queue`
  * `N8N_HOST`, `N8N_PORT`


Here’s a professional and structured explanation for ✅ **10. Production Best Practices** in **n8n**:

---

### ✅ 10. Production Best Practices

#### 🧬 **Workflows as Code (Git Versioning)**

* Use **n8n CLI** or API to export/import workflows (`.json` format)
* Store in Git for version control, code reviews, and CI/CD

#### 🔐 **Encryption & Security**

* Store secrets securely using:

  * **Environment variables**
  * **n8n credentials system** (built-in encryption)
* Use **API keys**, **OAuth tokens**, and **HTTP headers** securely via credential nodes

#### 🕵️‍♂️ **Audit Logs & Access Control** (n8n Enterprise)

* Track:

  * Workflow changes
  * User actions
  * Execution logs
* Use **Role-Based Access Control (RBAC)** to manage team permissions



