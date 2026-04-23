# Quiz Gamification App

> Flask-based web quiz platform with gamification mechanics, Azure Cosmos DB backend, Azure Functions integration, and CI/CD pipeline via GitHub Actions.

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![Flask](https://img.shields.io/badge/Flask-000000?style=flat&logo=flask&logoColor=white)
![Azure](https://img.shields.io/badge/Azure-0078D4?style=flat&logo=microsoftazure&logoColor=white)
![CosmosDB](https://img.shields.io/badge/Cosmos_DB-0078D4?style=flat&logo=microsoftazure&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat&logo=githubactions&logoColor=white)

---

## Overview

Web application for interactive quiz delivery with gamification mechanics.
Built with Flask, backed by Azure Cosmos DB, and extended with an Azure Functions serverless layer for quiz finalization logic.

**84 commits · 120 production deployments · CI/CD automated via GitHub Actions**

---

## Architecture

```
FlaskMiniProjeto/          ← Web app (this repo)
│   app.py                     Flask application entry point
│   quiz.py                    Quiz logic and Cosmos DB integration
│   requirements.txt           Python dependencies
│   static/css/                Styles
│   templates/                 HTML templates (Jinja2)
│   .github/workflows/         CI/CD pipeline (GitHub Actions)
│
FinalizeQuizFunction/      ← Azure Function (companion repo)
    function_app.py            Serverless quiz finalization handler
    function.json              Function bindings config
```

---

## Tech Stack

| Layer | Technology |
|---|---|
| Web Framework | Flask (Python) |
| Database | Azure Cosmos DB |
| Serverless | Azure Functions (Python) |
| CI/CD | GitHub Actions |
| Infrastructure | Microsoft Azure |
| Automation | PowerShell (setup script) |

---

## Prerequisites

- Python 3.x
- Azure account with Cosmos DB instance
- Azure Functions Core Tools + VS Code Azure Tools extension
- PowerShell (for setup script)

---

## Setup

### 1. Clone and configure environment

```bash
git clone https://github.com/GuilhermePires21890/FlaskMiniProjeto.git
cd FlaskMiniProjeto
pip install -r requirements.txt
```

### 2. Configure image path (PowerShell script)

Edit `Script.ps1` and update the images path variable:

```powershell
$caminhoImagens="C:/your/path/to/images"
```

Run the script:
```powershell
.\Script.ps1
```

### 3. Configure Azure Cosmos DB credentials

In `app.py` and `quiz.py`, replace the placeholder with your Cosmos DB Primary Key:

```python
COSMOS_KEY = "YOUR_PRIMARY_KEY_HERE"
```

Get your key from: **Azure Portal → Cosmos DB → Keys → PRIMARY KEY**

### 4. Deploy Azure Function

1. Open `FinalizeQuizFunction/` folder in VS Code
2. Install the **Azure Tools** extension pack
3. Sign in to Azure via the sidebar
4. Under Workspace → Local Project → Deploy to Function App

### 5. Configure GitHub Actions (for CI/CD)

Update the workflow file `.github/workflows/` with your Azure credentials and repository name before enabling automated deployments.

---

## Related Repository

This project uses an Azure Function for quiz finalization logic:

**[FinalizeQuizFunction](https://github.com/GuilhermePires21890/FinalizeQuizFunction)** — Serverless handler that processes quiz completion events via Azure Functions (Python).

---

## Contributors

- [@GuilhermePires21890](https://github.com/GuilhermePires21890)
- [@eduardospaulo2](https://github.com/eduardospaulo2)
