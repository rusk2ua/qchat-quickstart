# Amazon Q Chat Quick Start

Quick start guides and resources for getting started with Amazon Q Chat across different platforms.

## 📚 Guides

- [Linux Quick Start Guide](linux-quickstart-guide.md) - Complete setup guide for Linux users
- [Offical Q Developer CLI repo and guide](https://github.com/aws/amazon-q-developer-cli) - Guide for all users

## 🚀 What is Amazon Q Chat?

Amazon Q Chat is an AI-powered assistant that helps with AWS-related questions, code generation, and infrastructure guidance directly from your command line.

## 🛠️ Quick Install

```bash
# Install AWS CLI v2
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
unzip awscliv2.zip && sudo ./aws/install

# Install Amazon Q CLI
curl -Lo q-cli.zip "https://d2bqwlg1xwxe0g.cloudfront.net/releases/1.0.0/q-cli-linux-x64.zip"
unzip q-cli.zip && sudo mv q /usr/local/bin/

# Get free Builder ID at: https://profile.aws.amazon.com/
# Start chatting
q chat
```

## 📖 Documentation

- [Amazon Q Developer Documentation](https://docs.aws.amazon.com/amazonq/)
- [AWS CLI Documentation](https://docs.aws.amazon.com/cli/)

## 🤝 Contributing

Feel free to submit issues and enhancement requests!

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
