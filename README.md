# cdk-toolkit-python

A toolkit for managing AWS CDK projects and bootstrapping AWS environments using Python and Bash scripts. This project ensures that `cdk init` and `cdk bootstrap` are performed only once per project or environment and includes utilities for cleanup and status checking.

---

## **Getting Started**

### **1. Set Environment Variables**

Before running the script, configure the following environment variables for your AWS account and region:

```bash
export AWS_DEFAULT_REGION=ap-southeast-2
export AWS_ACCESS_KEY_ID=your-access-key-id
export AWS_SECRET_ACCESS_KEY=your-secret-access-key
export AWS_SESSION_TOKEN=your-session-token
```

Alternatively, configure the AWS CLI:

```bash
aws configure
```

---

### **2. Ensure Python Environment Setup**

Before running the script or your CDK application, ensure your Python environment is properly set up:

For Linux/macOS

1. **Create Virtual Environment**:

   ```bash
   python3 -m venv .venv
   ```

2. **Activate Virtual Environment**:

   ```bash
   source .venv/bin/activate
   ```

3. **Install Required Packages**:

   ```bash
   python -m pip install -r requirements.txt
   ```

For Windows

1. **Create Virtual Environment**:

   ```bash
   python -m venv .venv
   ```

2. **Activate Virtual Environment**:

   ```bash
   .venv\Scripts\activate
   ```

3. **Install Required Packages**:

   ```bash
   python -m pip install -r requirements.txt
   ```

---

### **3. Script Usage**

Run the Bash script with one of the following commands:

#### **Create Bootstrap Stack**

Initialize the CDK project and bootstrap the AWS environment:

```bash
./aws-cdk-bootstrap.sh create
```

#### **Delete Bootstrap Stack**

Clean up the CDK bootstrap stack and associated resources:

```bash
./aws-cdk-bootstrap.sh delete
```

#### **Check Bootstrap Stack**

Check the status of the CDK bootstrap stack:

```bash
./aws-cdk-bootstrap.sh check
```

---

## **Requirements**

- **AWS CLI**: Ensure the AWS CLI is installed and configured. Verify with:

  ```bash
  aws --version
  ```

- **Bash**: A Bash environment to run the scripts.
- **Python**: Python 3.7 or higher is required.

---

## **Troubleshooting**

- **Error: Unable to determine account or region**:
  Ensure the AWS CLI is configured correctly, or set the `AWS_DEFAULT_REGION` environment variable.

- **Bootstrap stack deletion fails due to non-empty S3 bucket**:
  Manually clean up the bucket:

  ```bash
  aws s3 rm s3://<bucket-name> --recursive
  ```

- **Virtual environment is not activated or dependencies are missing**:

For Linux/macOS

  1. Activate your virtual environment:

     ```bash
     source .venv/bin/activate
     ```

  2. Install dependencies:

     ```bash
     python -m pip install -r requirements.txt
     ```

For Windows

  1. Activate your virtual environment:

     ```bash
     .venv\Scripts\activate
     ```

  2. Install dependencies:

     ```bash
     python -m pip install -r requirements.txt
     ```

---

## **License**

This project is licensed under the MIT License. See the [LICENSE](./LICENSE) file for details.
