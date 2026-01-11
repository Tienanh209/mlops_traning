# MLOps Training Documentation

**Complete study guide for MLOps infrastructure and deployment**

## Study Path Overview

This documentation follows a **hybrid structure**:
- **`docs/`** (you are here) - Conceptual learning and theory
- **`module-X/`** - Hands-on labs and practice code

## Quick Start

1. **Choose your module** below
2. **Read the conceptual documentation** in `docs/module-X/`
3. **Practice with labs** in `module-X/` folder

---

## Module 1: Infrastructure Prerequisites

**Goal**: Master Docker, AWS, and Terraform fundamentals for MLOps

### Study Path

| Order | Topic | Description | Lab Location |
|-------|-------|-------------|--------------|
| 1 | Docker Basics | Container fundamentals and Docker concepts | N/A (theory only for now) |
| 2 | AWS | Cloud services, security, networking, and AI/ML | [`module-01/aws/`](../module-01/aws/) |
| 3 | Terraform Basics | Infrastructure as Code fundamentals | [`module-01/terraform/basics/`](../module-01/terraform/basics/) |

### Module 1 Documentation

**Docker:**
- [Docker Basics Guide](module-01/docker/basics.md)

**AWS:**
- [AWS Overview Guide](module-01/aws/README.md) - Complete AWS reference
  - Cloud Concepts & Security
  - Core Services (Compute, Storage, Database, Networking, Analytics)
  - AI/ML Services
  - Deployment Methods
  - Billing & Pricing
  - LocalStack Practice Guides

**Terraform:**
- [Terraform Basics Guide](module-01/terraform/basics.md)
- [Terraform Examples](module-01/terraform/examples.md)
- [Terraform Exercises](module-01/terraform/exercises.md)

### Lab Locations

| Lab | Description | Location |
|-----|-------------|----------|
| **LocalStack** | AWS services practice locally | [`module-01/aws/`](../module-01/aws/) |
| **Terraform Basics** | Infrastructure as Code fundamentals | [`module-01/terraform/basics/`](../module-01/terraform/basics/) |
| **Terraform Examples** | Example configurations | [`module-01/terraform/examples/`](../module-01/terraform/examples/) |
| **Terraform Exercises** | Practice exercises | [`module-01/terraform/exercises/`](../module-01/terraform/exercises/) |

---

## Module 2: Model Deployment

**Goal**: Deploy machine learning models as APIs

**Coming soon** - Batch API deployment with FastAPI

**Lab Location:** [`module-02/batch-api/`](../module-02/batch-api/)

---

## Module 3: Testing & CI/CD

**Goal**: Implement automated testing and deployment pipelines

**Coming soon** - Testing frameworks and CI/CD setup

**Lab Location:** [`module-03/testing/`](../module-03/testing/)

---

## Study Tips

### For Each Module

1. **Read first** - Start with the conceptual guide in `docs/`
2. **Practice second** - Run the lab exercises in `module-X/`
3. **Experiment** - Modify configurations and observe changes
4. **Review** - Re-read documentation with practical context

### For Hands-on Skills

1. **Complete all lab exercises** - Don't skip!
2. **Break things intentionally** - Learn to troubleshoot
3. **Build variations** - Modify exercises to solve new problems
4. **Document your learnings** - Keep notes

### Example Study Workflow

```bash
# 1. Read the conceptual guide
cat docs/module-01/aws/README.md

# 2. Navigate to the lab
cd module-01/aws

# 3. Start the lab environment
docker compose up -d

# 4. Practice the exercises
aws --endpoint-url=http://localhost:4566 s3 mb s3://my-bucket

# 5. Clean up
docker compose down -v
```

---

## Additional Resources

### External References

**General:**
- [Docker Documentation](https://docs.docker.com/)
- [Terraform Documentation](https://developer.hashicorp.com/terraform)
- [LocalStack Documentation](https://docs.localstack.cloud/)

**AWS (Reference for CLF-C02 Exam):**
- [AWS Certified Cloud Practitioner CLF-C02 Exam Guide](https://aws.amazon.com/certification/certified-cloud-practitioner/)
- [DigitalCloud.training Cheat Sheets](https://digitalcloud.training/)

### Internal Tools

- [`module-01/aws/`](../module-01/aws/) - LocalStack lab environment
- [`module-01/terraform/basics/`](../module-01/terraform/basics/) - Terraform practice
- [`module-01/terraform/examples/`](../module-01/terraform/examples/) - Terraform examples
- [`module-01/terraform/exercises/`](../module-01/terraform/exercises/) - Terraform exercises

---

## Progress Tracking

Track your progress by checking off completed modules:

### Module 1: Infrastructure Prerequisites
- [ ] Docker Basics
- [ ] AWS (Cloud, Services, Security, AI/ML)
- [ ] Terraform Basics
- [ ] LocalStack Practice Labs

### Module 2: Model Deployment
- [ ] Batch API with FastAPI
- [ ] Model Deployment Patterns

### Module 3: Testing & CI/CD
- [ ] Testing Frameworks
- [ ] CI/CD Pipelines

---

**Last Updated**: January 2026
