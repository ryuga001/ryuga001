<img width="100%" src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=6,11,20&height=200&section=header&text=Rahul%20Singh&fontSize=58&fontColor=ffffff&fontAlignY=36&desc=Software%20Development%20Engineer%20%E2%80%A2%20Distributed%20Systems%20%E2%80%A2%20Data%20Security&descAlignY=58&descSize=17" alt="header" />

<p align="center">
  I design <b>fault-tolerant, high-throughput backend systems</b> that stay correct under load, failure and multi-tenant pressure,<br/>
  and ship them with real testing and CI/CD.
</p>

<p align="center">
  <a href="https://me.ryuga.space/en"><img src="https://img.shields.io/badge/Portfolio-111827?style=for-the-badge&logo=firefox&logoColor=FF7139" /></a>
  <a href="https://www.linkedin.com/in/rahul-singh-546676240/"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" /></a>
  <a href="mailto:rahul0singh003@gmail.com"><img src="https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white" /></a>
  <a href="https://codeforces.com/profile/ryuga01"><img src="https://img.shields.io/badge/Codeforces-Specialist-1F8ACB?style=for-the-badge&logo=codeforces&logoColor=white" /></a>
  <a href="https://www.codechef.com/users/rahul_singh36"><img src="https://img.shields.io/badge/CodeChef-3★-964B00?style=for-the-badge&logo=codechef&logoColor=white" /></a>
  <a href="https://leetcode.com/u/r_singh"><img src="https://img.shields.io/badge/LeetCode-FFA116?style=for-the-badge&logo=leetcode&logoColor=white" /></a>
</p>

---

## ⚡ Impact at a Glance

<table align="center">
  <tr>
    <td align="center" width="25%"><h2>2,000+</h2><b>events / sec</b><br/><sub>SIEM log forwarding<br/>zero message loss</sub></td>
    <td align="center" width="25%"><h2>10M+</h2><b>events / run</b><br/><sub>distributed bulk export<br/>fair across 100+ tenants</sub></td>
    <td align="center" width="25%"><h2>100+ × 100+</h2><b>tenants × devices</b><br/><sub>content-aware DLP<br/>offline detection</sub></td>
    <td align="center" width="25%"><h2>4</h2><b>cloud sources</b><br/><sub>S3 · Azure Blob<br/>Google Drive · SharePoint</sub></td>
  </tr>
</table>

---

## 🧠 What I Build

### 1. SIEM Log-Forwarding Microservice
> Lock-free pipeline sustaining **2,000+ events/sec with zero message loss**

HTTP/TCP delivery in JSON and Syslog formats, built on the **LMAX Disruptor**, with per-vendor rate limits enforced on the way out.

```mermaid
flowchart LR
    A[Incoming events] --> B[Disruptor<br/>lock-free ring buffer]
    B --> C[Per-vendor<br/>rate limiter]
    C --> D[HTTP / TCP<br/>JSON · Syslog]
```

### 2. Distributed Bulk-Export Pipeline
> Processes **10M+ security events per run** with fair scheduling across **100+ tenants**

Built with **Java, Spring Batch, AWS S3, Redis and RabbitMQ**. Per-tenant Redis token buckets and processing-time quotas, plus RabbitMQ priority queuing, remove noisy-neighbor starvation.

```mermaid
flowchart LR
    A[Export request] --> B{{RabbitMQ<br/>priority queue}}
    B --> C[Spring Batch<br/>workers]
    R[(Redis<br/>token bucket · time quota<br/>per tenant)] -.-> C
    C --> D[(AWS S3)]
```

### 3. Content-Based Data Loss Prevention Engine
> Supports **100+ tenants with 100+ devices each**, with fully **offline** violation detection

**CDC chunking + MinHash/LSH** gives sublinear similarity search. Fingerprint matching runs only when policy criteria are met, which removes redundant computation. Signatures sync from MongoDB to on-device SQLite.

```mermaid
flowchart LR
    A[Content] --> B[CDC<br/>chunking]
    B --> C[MinHash / LSH<br/>candidate search]
    C --> D{Policy criteria<br/>met?}
    D -- yes --> E[Fingerprint<br/>match]
    D -- no --> F[Skip]
    M[(MongoDB)] -- sync --> S[(On-device SQLite)]
    S -.-> C
```

### 4. Cloud Data Discovery
> Connector architecture, ingestion and processing pipelines for **4 cloud sources**

```mermaid
flowchart LR
    A[AWS S3] --> E
    B[Azure Blob] --> E
    C[Google Drive] --> E
    D[SharePoint] --> E[Connectors]
    E --> F[Ingestion] --> G[Processing]
```

---

## 🛠️ Tech Stack

<p align="center">
  <b>Languages</b><br/>
  <img src="https://skillicons.dev/icons?i=java,go,py,ts,js,cpp" /><br/><br/>
  <b>Backend</b><br/>
  <img src="https://skillicons.dev/icons?i=spring,nodejs,express,django,graphql" /><br/><br/>
  <b>Messaging & Data</b><br/>
  <img src="https://skillicons.dev/icons?i=rabbitmq,redis,postgres,mongodb,mysql,sqlite" /><br/><br/>
  <b>Frontend</b><br/>
  <img src="https://skillicons.dev/icons?i=react,nextjs,tailwind,threejs" /><br/><br/>
  <b>Cloud & DevOps</b><br/>
  <img src="https://skillicons.dev/icons?i=aws,azure,docker,githubactions,linux,git" />
</p>

<p align="center">
  <sub><code>Distributed Systems</code> · <code>Concurrency</code> · <code>Rate Limiting</code> · <code>Message Queues & Streams</code> · <code>System Design</code> · <code>Similarity Search</code> · <code>Testing & CI/CD</code></sub>
</p>

---

## 📊 GitHub Activity

<p align="center">
  <img height="165" src="https://github-readme-stats.vercel.app/api?username=ryuga001&theme=tokyonight&hide_border=true&show_icons=true&count_private=true" />
  <img height="165" src="https://streak-stats.demolab.com/?user=ryuga001&theme=tokyonight&hide_border=true" />
</p>

<p align="center">
  <img width="100%" src="https://github-readme-activity-graph.vercel.app/graph?username=ryuga001&theme=tokyo-night&hide_border=true&area=true" />
</p>

---

<img width="100%" src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=6,11,20&height=90&section=footer" alt="footer" />
