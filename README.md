# create-k8s-cluster

> 🚀 Instantly bootstrap Kubernetes clusters and deploy your apps — powered by LLMs, guided by simple CLI prompts, and fully configurable.

---

## 🧠 Overview

`create-k8s-cluster` is a developer-first CLI tool that automates the setup of Kubernetes clusters and deployment of apps — without requiring you to write a single line of YAML.

It leverages LLMs (like Google Gemini) to generate production-ready manifests, charts, and configs based on your answers to interactive prompts.

Designed to be simple, extensible, and safe — this tool helps you get from zero to running cluster in minutes.

---

## ✨ Features

- ✅ Interactive CLI — just answer a few questions
- 🚀 Choose your runtime: Minikube, Kind, K3s, or full K8s
- ⚙️ Deploy apps with LLM-generated YAML + Helm configs
- 📁 Generates `.create-k8s-cluster.conf` for future upgrades
- 🔁 Rerun with `--upgrade` to apply changes from config
- 🔐 No API keys stored — ever (session-only)
- 🧠 Supports LLM providers (Google Gemini recommended)
- 💡 No DevOps or K8s experience required

---

## 📦 Installation

You don’t need to clone anything. Just run:

```bash
npx create-k8s-cluster
```

Make sure you have:

* ✅ Docker installed
* ✅ Node.js (for `npx`)
* ✅ Python 3.x (for backend generation logic, if used)
* ✅ Optional: K8s CLI tools (`kubectl`, etc.)

---

## 🚀 Usage

```bash
npx create-k8s-cluster
```

Answer the CLI prompts:

```bash
? Provide your LLM API key:
? Choose K8s type: (minikube/k3s/kind/k8s)
? How many worker nodes?
? App to deploy? (nextjs/fastapi/redis/etc.)
? Enable monitoring? (Y/N)
? Enable ingress? (Y/N)
```

Once done, the tool will:

* Spin up your cluster
* Generate YAML/Helm configs via LLM
* Deploy your app
* Provide cluster access instructions

---

## 🛠️ Configuration File

After first run, a `.create-k8s-cluster.conf` is generated:

```ini
cluster_type=minikube
nodes=2
app_stack=nextjs,fastapi
llm=gemini
llm_api_key=env:GEMINI_API_KEY
enable_monitoring=true
```

You can edit this file and re-run the tool with:

```bash
npx create-k8s-cluster --upgrade
```

The CLI will automatically detect changes and apply them.

---

## 🔐 Security

* API keys are **only kept in-memory**
* Nothing is saved to disk unless explicitly written
* No analytics, no telemetry, no vendor lock-in

---

## 🌍 LLM Provider Support

Currently supports:

* [x] **Google Gemini** (recommended — generous free tier)

You’ll be asked to input your API key during first use.

---

## 📚 Examples

```bash
npx create-k8s-cluster
```

Result:

* `minikube` cluster with 2 nodes
* Next.js app and FastAPI backend deployed
* Ingress + monitoring enabled
* Everything deployed in isolated Docker containers

---

## 🤝 Contributing

Pull requests, issues, and ideas are welcome!

Looking for:

* CLI improvements
* LLM prompt optimizations
* Support for new app templates
* Community config presets

```bash
git clone https://github.com/YOUR-USERNAME/create-k8s-cluster.git
cd create-k8s-cluster
npm install
npm run dev
```

---

## 📜 License

MIT — free to use, modify, and distribute.
