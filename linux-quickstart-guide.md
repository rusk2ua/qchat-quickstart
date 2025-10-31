# Amazon Q Chat Quick Start Guide for Linux

## Prerequisites

- Linux distribution (Ubuntu, CentOS, Amazon Linux, etc.)
- Terminal access with sudo privileges
- AWS Builder ID (free) OR AWS account
- Internet connection

## Installation

### Step 1: Install AWS CLI v2

```bash
# Download AWS CLI v2 for Linux
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"

# Install unzip if not available
sudo apt update && sudo apt install unzip -y  # Ubuntu/Debian
# OR
sudo yum install unzip -y  # CentOS/RHEL/Amazon Linux

# Extract and install
unzip awscliv2.zip
sudo ./aws/install

# Verify installation
aws --version
```

### Step 2: Install Amazon Q CLI

```bash
# Download and install Amazon Q CLI
curl -Lo q-cli.zip "https://d2bqwlg1xwxe0g.cloudfront.net/releases/1.0.0/q-cli-linux-x64.zip"
unzip q-cli.zip
sudo mv q /usr/local/bin/
chmod +x /usr/local/bin/q

# Verify installation
q --version
```

## Configuration

### Step 3: Choose Authentication Method

**Option A: AWS Builder ID (Recommended - Free)**

1. Create a free AWS Builder ID at: https://profile.aws.amazon.com/
2. Verify your email address
3. Start Amazon Q Chat - it will prompt you to authenticate:

```bash
q chat
# Follow the browser authentication flow when prompted
```

**Option B: AWS Account Credentials**

If you have an existing AWS account, configure your credentials:

```bash
aws configure
```
Enter your:
- AWS Access Key ID
- AWS Secret Access Key  
- Default region (e.g., us-east-1)
- Default output format (json)

**Option C: Environment Variables (AWS Account)**
```bash
export AWS_ACCESS_KEY_ID=your-access-key
export AWS_SECRET_ACCESS_KEY=your-secret-key
export AWS_DEFAULT_REGION=us-east-1
```

**Option D: IAM Roles (for EC2 instances)**
Attach an IAM role with appropriate permissions to your EC2 instance.

### Step 4: Verify Access

## Getting Started

### Step 5: Start Amazon Q Chat

```bash
# Start interactive chat session
q chat

# Start with a specific question
q chat "How do I create an S3 bucket?"

# Get help
q --help
q chat --help
```

### Step 6: Basic Commands

Once in the chat session:

```
# Ask questions about AWS
How do I deploy a Lambda function?

# Get code examples
Show me Python code to list S3 buckets

# File operations
/save conversation.txt    # Save conversation
/load conversation.txt    # Load previous conversation
/context add file.py     # Add file context
/quit                    # Exit chat
```

## Common Use Cases

### Infrastructure Questions
```
How do I set up a VPC with public and private subnets?
What's the best practice for RDS security groups?
```

### Code Assistance
```
Write a CloudFormation template for an EC2 instance
Show me Terraform code for an S3 bucket with versioning
```

### Troubleshooting
```
My Lambda function is timing out, how can I debug this?
Why is my EC2 instance not accessible via SSH?
```

## Troubleshooting

### Common Issues

**Permission Denied**
```bash
# Ensure Q CLI has execute permissions
chmod +x /usr/local/bin/q
```

**Authentication Issues**
```bash
# For Builder ID: Re-authenticate
q chat
# Follow browser authentication flow

# For AWS credentials: Check configuration
aws configure list
aws sts get-caller-identity
```

**Network Issues**
```bash
# Test connectivity
curl -I https://profile.aws.amazon.com  # For Builder ID
aws sts get-caller-identity             # For AWS credentials
```

### Getting Help

- Use `q --help` for CLI options
- Use `/help` within chat for session commands
- Check AWS documentation for credential setup issues

## Documentation References

- [Amazon Q Developer Documentation](https://docs.aws.amazon.com/amazonq/)
- [AWS Builder ID Signup](https://profile.aws.amazon.com/)
- [AWS CLI Installation Guide](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html)
- [AWS Credentials Configuration](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-files.html)
- [IAM Permissions for Amazon Q](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/security-iam.html)
- [Amazon Q Chat CLI Reference](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/cli-commands.html)

## Next Steps

1. Explore Amazon Q's code generation capabilities
2. Integrate with your IDE using Amazon Q extensions
3. Set up team collaboration features
4. Configure custom knowledge bases for your organization

---

**Need Help?** Use `q chat "help me get started"` for interactive assistance.
