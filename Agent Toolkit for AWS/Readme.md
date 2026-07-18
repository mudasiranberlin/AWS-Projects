# Agent Toolkit for AWS

## Overview

The **Agent Toolkit for AWS** helps AI coding assistants (such as Claude Code, Codex, Cursor, and Kiro) build, deploy, and manage AWS resources securely and efficiently.

It provides AI agents with:
- Access to AWS services
- Latest AWS documentation
- Step-by-step guidance (Skills)
- Secure authentication using AWS IAM
- Project guardrails through Rules Files

---

## Why Use It?

Without the Agent Toolkit, AI agents may:
- Choose the wrong AWS service
- Misconfigure AWS resources
- Struggle with complex AWS workflows
- Use outdated AWS knowledge

With the Agent Toolkit:
- Uses the latest AWS documentation
- Follows AWS best practices
- Executes AWS API calls securely
- Supports complex AWS workflows

---

# Components

## 1. AWS MCP Server

Acts as a bridge between AI coding agents and AWS.

### Features
- Connects AI agents to AWS
- Searches AWS documentation
- Executes AWS API calls
- Runs Python scripts
- Uses IAM authentication
- Provides CloudWatch monitoring

**Easy Remember:**  
> MCP = Bridge between AI and AWS

---

## 2. Agent Skills

Pre-built instructions and workflows that help AI complete AWS tasks.

### Includes
- Service selection
- Step-by-step procedures
- Troubleshooting
- AWS SDK best practices

**Easy Remember:**  
> Skills = Step-by-step Guide

---

## 3. Plugins

Plugins quickly configure supported AI coding assistants.

Supported agents include:
- Claude Code
- Codex

*Kiro connects directly and does not require a plugin.*

**Easy Remember:**  
> Plugin = Quick Setup

---

## 4. Rules Files

Rules Files define how AI agents should work within a project.

Examples:
- Use AWS MCP Server
- Search documentation first
- Restrict dangerous actions
- Apply project standards

**Easy Remember:**  
> Rules = Guardrails

---

# What Can It Do?

The Agent Toolkit can:

- Build AWS applications
- Deploy applications
- Create AWS infrastructure
- Search AWS documentation
- Troubleshoot AWS issues
- Monitor AWS resources
- Execute AWS API calls securely

---

# Security

The toolkit uses AWS security services:

- IAM Authentication
- Least Privilege Access
- CloudTrail Logging
- CloudWatch Monitoring

---

# Authentication

Supports:

- AWS IAM Credentials
- SigV4 Authentication
- OAuth 2.1

---

# Pricing

The Agent Toolkit is **free**.

You only pay for the AWS resources your agent creates or uses.

---

# Interview Notes

### What is Agent Toolkit for AWS?

The Agent Toolkit for AWS helps AI coding assistants securely build, deploy, and manage AWS resources using AWS best practices.

---

## Main Components

| Component | Purpose |
|-----------|---------|
| AWS MCP Server | Connects AI to AWS |
| Agent Skills | Step-by-step guidance |
| Plugins | Easy installation |
| Rules Files | Guardrails and project rules |

---

## Memory Trick

**MCP → Skills → Plugin → Rules**

- **MCP** → Connect AI to AWS
- **Skills** → Teach AI
- **Plugin** → Install AI support
- **Rules** → Protect AI actions

---

# One-Line Interview Answer

> **The Agent Toolkit for AWS enables AI coding assistants to securely build, deploy, troubleshoot, and manage AWS resources using the AWS MCP Server, Agent Skills, Plugins, and Rules Files while following AWS best practices.**
