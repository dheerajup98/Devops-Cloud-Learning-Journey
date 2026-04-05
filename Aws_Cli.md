# 🚀 Day 9 – AWS CLI, Automation vs Manual, and Remote Access (MobaXterm)

## 📌 Overview
In this learning module, I explored:
- Manual vs Automated (CLI) methods to create AWS resources
- Complete understanding of AWS CLI
- How to connect a Windows machine to a Linux server (EC2/VM)
- What happens behind the scenes (deep understanding)

---

# 🔹 1. Manual vs Automation (AWS)

## 🖱️ Manual Method (AWS Console - GUI)

### Steps:
1. Login to AWS Console
2. Navigate to EC2 Dashboard
3. Click "Launch Instance"
4. Select AMI (Ubuntu / Amazon Linux)
5. Choose instance type (t2.micro)
6. Configure security group (allow SSH - port 22)
7. Create/select key pair
8. Launch instance

### ❌ Problems:
- Time-consuming
- Not scalable
- Not suitable for automation
- Manual errors possible
- Hard to reproduce environments

---

## ⚡ Automation Method (AWS CLI)

### Full EC2 Creation Flow Using CLI

## Step 1: Create Key Pair
```bash
aws ec2 create-key-pair \
--key-name my-key \
--query 'KeyMaterial' \
--output text > my-key.pem
