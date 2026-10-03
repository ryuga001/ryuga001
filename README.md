# Rahul Singh

**Software Development Engineer · Backend · Distributed Systems · Data Security**

I build backend systems that deal with **concurrency, high-throughput workloads, multi-tenancy, asynchronous processing, and data security**.

Currently working mostly with **Java, Go, Redis, RabbitMQ, MongoDB, PostgreSQL, AWS, and Next.js**.

<p align="left">
  <a href="https://me.ryuga.space/en">
    <img alt="Portfolio" src="https://img.shields.io/badge/Portfolio-111827?style=for-the-badge&logo=firefox&logoColor=FF7139" />
  </a>
  <a href="https://www.linkedin.com/in/rahul-singh-546676240/">
    <img alt="LinkedIn" src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" />
  </a>
  <a href="mailto:rahul0singh003@gmail.com">
    <img alt="Email" src="https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white" />
  </a>
  <a href="https://codeforces.com/profile/ryuga01">
    <img alt="Codeforces" src="https://img.shields.io/badge/Codeforces-Specialist-1F8ACB?style=for-the-badge&logo=codeforces&logoColor=white" />
  </a>
  <a href="https://www.codechef.com/users/rahul_singh36">
    <img alt="CodeChef" src="https://img.shields.io/badge/CodeChef-3★-964B00?style=for-the-badge&logo=codechef&logoColor=white" />
  </a>
  <a href="https://leetcode.com/u/r_singh">
    <img alt="LeetCode" src="https://img.shields.io/badge/LeetCode-FFA116?style=for-the-badge&logo=leetcode&logoColor=white" />
  </a>
</p>

---

## What I Like Building

I enjoy working on problems where the interesting part isn't just making the API work, but making the system behave correctly when things get difficult.

- ⚙️ **Distributed & concurrent systems**
- 🚦 **Rate limiting, backpressure & fair scheduling**
- 📬 **Message queues, streams & asynchronous processing**
- 🏢 **Multi-tenant backend architectures**
- 🔐 **Data security & content inspection**
- 🔎 **Large-scale file discovery & processing**
- ☁️ **Cloud integrations & storage systems**
- 🧪 **Testing, observability & failure handling**

Some engineering problems I've worked on include:

> How do you prevent one tenant from consuming all available workers?

> How do you handle millions of events without allowing memory usage to grow without bounds?

> How do you process large files without loading them entirely into memory?

> How do you keep asynchronous delivery reliable when external systems are slow or unavailable?

These are the kinds of problems I like exploring.

---

## 🚀 Featured Project

### 🔐 [SecurePlus](https://github.com/ryuga001/SecurePlus)

**Multi-tenant outbound email security platform**

SecurePlus is a backend-heavy security system I built end to end to explore **email security, asynchronous delivery, multi-tenancy, policy enforcement, and distributed system design**.

```text
SMTP
 │
 ▼
┌─────────────────────┐
│   Policy Engine     │
│                     │
│  Rules + Inspection │
└──────────┬──────────┘
           │
           ▼
     DKIM Signing
           │
           ▼
   Async Delivery
           │
           ▼
      Recipient MX
```

### What it handles

- Multi-tenant email policies
- Content and rule inspection
- DKIM signing
- Asynchronous delivery
- Recipient MX retry/backoff
- Delivery auditing
- Security incidents
- Role-based administration
- Tenant configuration caching
- Object storage for tenant assets

### Architecture

```text
                    ┌───────────────┐
                    │   Next.js     │
                    │ Admin Console │
                    └───────┬───────┘
                            │
                            ▼
                    ┌───────────────┐
                    │      Go       │
                    │   API / Auth  │
                    └───────┬───────┘
                            │
              ┌─────────────┼─────────────┐
              ▼             ▼             ▼
           MongoDB        Redis        Object Store
              │             │          S3 / MinIO
              │             │
              └──────┬──────┘
                     ▼
              Policy / Delivery
                     │
                     ▼
                Async Queue
                     │
                     ▼
                Recipient MX
```

**Stack:** `Go` `Redis` `MongoDB` `Next.js` `TypeScript` `S3 / MinIO`

**→ [View the repository](https://github.com/ryuga001/SecurePlus)**  
**→ [Open the live console](https://secureplus.onrender.com)**

---

## 🧠 Engineering Work

A few areas I've worked on professionally and use to guide the systems I build here.

### High-throughput event processing

Worked on a SIEM log-forwarding system handling **2,000+ events/sec in load testing**, using bounded processing and per-destination rate limiting.

```text
Incoming Events
      │
      ▼
Lock-free Buffer
      │
      ▼
Per-vendor Rate Limit
      │
      ▼
JSON / Syslog
      │
      ▼
HTTP / TCP
```

The interesting part wasn't just throughput — it was making overload **bounded and predictable** instead of allowing queues and memory to grow indefinitely.

---

### Distributed bulk processing

Worked on export workloads reaching **10M+ events per run across 100+ tenants**.

The system used:

- RabbitMQ for work distribution
- Redis token buckets for admission control
- Tenant-level processing quotas
- Priority scheduling
- Multipart S3 uploads

The primary design concern was **fairness under shared infrastructure**.

---

### Content similarity & DLP

Worked on content-aware detection designed around **100+ tenants and 100+ endpoint devices**.

The pipeline uses concepts including:

```text
File
 │
 ▼
CDC Chunking
 │
 ▼
MinHash
 │
 ▼
LSH Candidate Search
 │
 ▼
Policy Evaluation
 │
 ▼
Fingerprint Matching
```

The goal is to avoid expensive fingerprinting when cheaper similarity checks can eliminate a candidate first.

---

### Cloud Data Discovery

Built cloud-source integrations around a shared discovery pipeline for:

- AWS S3
- Azure Blob Storage
- Google Drive
- SharePoint

The scanner is designed around **streaming file processing**, so large files don't need to be loaded completely into memory.

```text
Cloud Provider
      │
      ▼
   Connector
      │
      ▼
   Metadata
      │
      ▼
   Streaming
      │
      ▼
 Processing Pipeline
```

---

## 🛠️ Tech Stack

### Languages

<p>
  <img src="https://skillicons.dev/icons?i=java,go,py,ts,js,cpp" />
</p>

### Backend

<p>
  <img src="https://skillicons.dev/icons?i=spring,nodejs,express,django,graphql" />
</p>

### Data & Messaging

<p>
  <img src="https://skillicons.dev/icons?i=rabbitmq,redis,postgres,mongodb,mysql,sqlite" />
</p>

### Frontend

<p>
  <img src="https://skillicons.dev/icons?i=react,nextjs,tailwind,threejs" />
</p>

### Cloud & Infrastructure

<p>
  <img src="https://skillicons.dev/icons?i=aws,azure,docker,githubactions,linux,git" />
</p>

---

## 🔬 Currently Exploring

- Distributed job processing
- Streaming architectures
- Backpressure and load shedding
- Multi-tenant resource isolation
- Reliable asynchronous workflows
- Large-scale file processing
- Cloud storage architectures
- Security-focused backend systems
- Go backend development
- System design

---

## 📈 Competitive Programming

I also enjoy algorithmic problem solving.

| Platform | Rating |
| --- | --- |
| Codeforces | **Specialist · 1422 max** |
| CodeChef | **3★ · 1667 max** |

<a href="https://codeforces.com/profile/ryuga01">Codeforces</a> ·
<a href="https://www.codechef.com/users/rahul_singh36">CodeChef</a> ·
<a href="https://leetcode.com/u/r_singh">LeetCode</a>

---

## 📊 GitHub

<p align="center">
  <img
    height="165"
    src="https://github-readme-stats.vercel.app/api?username=ryuga001&theme=tokyonight&hide_border=true&show_icons=true&count_private=true"
  />
  <img
    height="165"
    src="https://streak-stats.demolab.com/?user=ryuga001&theme=tokyonight&hide_border=true"
  />
</p>

<p align="center">
  <img
    width="100%"
    src="https://github-readme-activity-graph.vercel.app/graph?username=ryuga001&theme=tokyo-night&hide_border=true&area=true"
  />
</p>

---

<p align="center">
  <sub>Build systems. Understand failure. Keep learning.</sub>
</p>
