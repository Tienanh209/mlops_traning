# MLOps Training

**Hands-on training for MLOps infrastructure, deployment, and CI/CD**

## Quick Start

1. **Start Learning** - Browse the [Study Guide](./docs/) in the `docs/` folder
2. **Practice Labs** - Run exercises in the `module-X/` folders

```
Start here:  docs/README.md  →  Complete study guide
Then:        module-01/      →  Hands-on labs
```

## Course Overview

| Module | Topic | Description | Technologies |
|--------|-------|-------------|--------------|
| 1 | Infrastructure & Prerequisites | Docker, AWS, Terraform fundamentals | Docker, AWS, Terraform, LocalStack |
| 2 | Model Deployment | Batch, API, streaming deployments | FastAPI, Docker, AWS Lambda |
| 3 | Testing & CI/CD | Testing strategies and CI/CD pipelines | GitHub Actions, pytest |

## Repository Structure

```
mlops_training/
├── docs/                          # 📖 CONCEPTUAL LEARNING
│   ├── README.md                  #   Study guide and navigation
│   ├── module-01/                 #   Module 1 theory and guides
│   │   ├── docker/                #   - Docker concepts
│   │   ├── terraform/             #   - Terraform IaC guide
│   │   └── aws/                   #   - AWS CLF-C02 exam prep
│   ├── module-02/                 #   Module 2 theory
│   └── module-03/                 #   Module 3 theory
│
├── module-01/                     # 🛠️ LAB & PRACTICE CODE
│   ├── docker/basics/             #   Docker containers and compose
│   ├── terraform/basics/          #   Terraform configurations
│   └── aws/localstack/            #   LocalStack for AWS practice
│
├── module-02/                     #   Model deployment labs
│   └── batch-api/fastapi/         #   FastAPI deployment
│
├── module-03/                     #   Testing and CI/CD labs
│   └── testing/                   #   Testing frameworks
│
└── assets/                        # Images and diagrams
```

## How to Use This Training

### For Each Topic

1. **Read the theory** in `docs/module-X/`
2. **Practice with labs** in `module-X/`
3. **Experiment** with configurations
4. **Build your own** variations

### Example: Learning Docker

```bash
# 1. Read the conceptual guide
cat docs/module-01/docker/basics.md

# 2. Navigate to the lab
cd module-01/docker/basics

# 3. Run the exercises
docker compose up -d

# 4. Experiment and learn
docker compose logs -f
```

### Example: Learning AWS with LocalStack

```bash
# 1. Read AWS service guide
cat docs/module-01/aws/storage-services.md

# 2. Start LocalStack
cd module-01/aws/localstack
cp .env.example .env
docker compose up -d

# 3. Practice S3 operations
aws --endpoint-url=http://localhost:4566 s3 mb s3://my-bucket
```

## Module Guides

| Module | Study Guide | Lab Location |
|--------|-------------|--------------|
| **Module 1** | [Infrastructure Guide](./docs/module-01/) | [`module-01/`](./module-01/) |
| **Module 2** | Coming soon | [`module-02/`](./module-02/) |
| **Module 3** | Coming soon | [`module-03/`](./module-03/) |

## Prerequisites

- Basic Python knowledge
- Machine learning concepts
- Command-line interface familiarity
- Docker Desktop installed

## Study Path

1. **[Start with the Study Guide](./docs/)** - Complete overview
2. **Module 1: Infrastructure** - Docker, Terraform, AWS
3. **Module 2: Model Deployment** - Batch and API patterns
4. **Module 3: Testing & CI/CD** - Automation pipelines

## Contributing

This is a training repository. See [CONTRIBUTING.md](./CONTRIBUTING.md)

---

**Start Learning:** [docs/README.md](./docs/) ← Complete study guide
