# LocalStack Lab

**Practice AWS services locally without cost**

## Quick Start

```bash
# Navigate to this directory
cd module-01/aws

# Copy environment configuration
cp .env.example .env

# Start LocalStack
docker compose up -d

# View logs
docker compose logs -f localstack

# Check health
curl http://localhost:4566/_localstack/health
```

## Lab Exercises

### Exercise 1: S3 Bucket Operations
```bash
# List buckets
aws --endpoint-url=http://localhost:4566 s3 ls

# Create a bucket
aws --endpoint-url=http://localhost:4566 s3 mb s3://my-test-bucket

# Upload a file
echo "Hello LocalStack" > test.txt
aws --endpoint-url=http://localhost:4566 s3 cp test.txt s3://my-test-bucket/

# List bucket contents
aws --endpoint-url=http://localhost:4566 s3 ls s3://my-test-bucket
```

### Exercise 2: DynamoDB Table Operations
```bash
# Create table
aws --endpoint-url=http://localhost:4566 dynamodb create-table \
    --table-name Users \
    --attribute-definitions AttributeName=UserId,AttributeType=S \
    --key-schema AttributeName=UserId,KeyType=HASH \
    --billing-mode PAY_PER_REQUEST

# Put item
aws --endpoint-url=http://localhost:4566 dynamodb put-item \
    --table-name Users \
    --item '{"UserId": {"S": "user1"}, "Name": {"S": "Alice"}}'

# Get item
aws --endpoint-url=http://localhost:4566 dynamodb get-item \
    --table-name Users \
    --key '{"UserId": {"S": "user1"}}'
```

### Exercise 3: Lambda Function
```bash
# Create handler
mkdir lambda && cd lambda
cat > handler.py << 'EOF'
def lambda_handler(event, context):
    return {'statusCode': 200, 'body': 'Hello from LocalStack!'}
EOF

# Package
zip function.zip handler.py

# Create function
aws --endpoint-url=http://localhost:4566 lambda create-function \
    --function-name my-function \
    --runtime python3.9 \
    --role arn:aws:iam::000000000000:role/test-role \
    --handler handler.lambda_handler \
    --zip-file fileb://function.zip

# Invoke function
aws --endpoint-url=http://localhost:4566 lambda invoke \
    --function-name my-function \
    response.json

cat response.json
```

## Configuration Files

| File | Purpose |
|------|---------|
| `docker-compose.yml` | Container configuration |
| `.env.example` | Environment variables template |

## Cleanup

```bash
# Stop LocalStack and remove volumes
docker compose down -v

# Remove the data volume
docker volume rm localstack-data
```

## Documentation

For detailed guides and theory, see:
- **[LocalStack Quick Start Guide](../../docs/module-01/aws/localstack-quick-start.md)**
- **[AWS CLF-C02 Study Guide](../../docs/module-01/aws/)**

## Troubleshooting

### Port already in use
```bash
# Find process on port 4566 (Windows)
netstat -ano | findstr :4566

# Kill the process
taskkill /PID <PID> /F
```

### Container not starting
```bash
# Check Docker is running
docker ps

# View logs
docker compose logs localstack
```

## Services Available

LocalStack FREE tier supports these CLF-C02 exam services:
- S3, DynamoDB, Lambda, EC2
- API Gateway, IAM, SNS, SQS
- Kinesis, CloudWatch Logs

For full service list, see [LocalStack Guide](../../docs/module-01/aws/localstack-guide.md).

## Study Path

1. Read AWS service guides in [`docs/module-01/aws/`](../../docs/module-01/aws/)
2. Practice with exercises in this directory
3. Combine with Terraform lab in [`module-01/terraform/basics/`](../terraform/)
