## 📖 Assignemnt 1: AWS IAM: User, Group, and Policy Assignment — Step by Step

---

### 📌 Prerequisites:

* An AWS account
* AWS Management Console access with permissions to manage IAM

---

## 👥 Step 1️⃣: Create an IAM User

1. Go to **AWS Management Console** → **IAM** → **Users**.
2. Click **Add users**.
3. Enter a **username** (e.g. `atul.user1`).
4. Select **Access type**:

   * ✅ Programmatic access (if using CLI/API)
   * ✅ AWS Management Console access (if using web console)
5. Set a password (optionally enforce a password reset at next sign-in).
6. Click **Next: Permissions**.

---

## 👥 Step 2️⃣: Create an IAM Group (Optional but Recommended)

1. In the **Permissions** step of user creation OR from **IAM → User groups** → **Create group**
2. Provide a **Group name** (e.g. `CloudAdmins`).
3. Attach existing policies (e.g. `AdministratorAccess`, `AmazonS3FullAccess`, or custom policies).
4. Click **Create group**.
5. Assign this group to your user by selecting it.

---

## 📃 Step 3️⃣: Create an IAM Policy (Optional for Custom Permissions)

If no existing AWS managed policy suits your need:

1. Go to **IAM → Policies** → **Create policy**
2. Choose **Visual editor** or **JSON** tab
3. Example JSON for S3 full access:

   ```json
   {
     "Version": "2012-10-17",
     "Statement": [
       {
         "Effect": "Allow",
         "Action": "s3:*",
         "Resource": "*"
       }
     ]
   }
   ```
4. Click **Next: Tags** (optional).
5. Click **Next: Review**, give a **Name** (e.g. `S3FullAccessPolicy`).
6. Click **Create policy**.

---

## 🔒 Step 4️⃣: Attach Policy to a User or Group

**To a Group**:

* Go to **IAM → User groups**
* Select your group (e.g. `CloudAdmins`)
* Go to **Permissions** tab → **Add permissions**
* Choose **Attach policies**
* Select policy (e.g. `S3FullAccessPolicy`) → **Attach policy**

**To a User (if not using a group)**:

* Go to **IAM → Users**
* Select your user
* Go to **Permissions** → **Add permissions**
* Choose **Attach policies**
* Select policy → **Attach policy**

---

## 🔍 Step 5️⃣: Test User Access

1. If you granted **console access**, log in via AWS console with the user credentials.
2. Verify if the user can access services as per attached policy.

---

## 📌 Summary Table

| Task          | AWS Console Path                   |
| :------------ | :--------------------------------- |
| Create User   | IAM → Users → Add users            |
| Create Group  | IAM → User groups → Create group   |
| Create Policy | IAM → Policies → Create policy     |
| Attach Policy | IAM → Users / Groups → Permissions |

---

## ✅ Example Scenario:

**User `atul.user1`** is created and added to **CloudAdmins group**.
**CloudAdmins group** has `AdministratorAccess` and `S3FullAccessPolicy` attached.

---
Sure — let’s clearly lay out an **AWS EC2 SSH, RDP, and IIS Setup Assignment** with well-structured steps. You can use this as a hands-on lab or assignment for training and practice.

---

## 📄 **Assignment 2: EC2 SSH, RDP, and IIS Configuration**

---

## 🎯 Objective:

* Launch Linux and Windows EC2 instances.
* Connect to Linux via SSH.
* Connect to Windows via RDP.
* Install and configure IIS on Windows Server EC2.

---

## 📦 **Pre-requisites**

* AWS Account with EC2 and security group creation permissions.
* AWS key pair for SSH connection.
* Remote Desktop client (for RDP connection).

---

## 📌 **Part A: Launch and Connect to Linux EC2 via SSH**

### ✅ Steps:

1. **Login to AWS Console.**

2. Go to **EC2 Dashboard → Instances → Launch Instance**.

3. Choose **Amazon Linux 2023 AMI**.

4. Choose an instance type: **t2.micro (Free Tier eligible)**.

5. Configure instance details (default is fine for testing).

6. **Add Storage** (keep default 8 GiB).

7. **Add Tags** (optional, e.g. `Name=Linux-SSH-Server`).

8. Configure **Security Group**:

   * Inbound Rule:

     | Type | Protocol | Port | Source                                |
     | :--- | :------- | :--- | :------------------------------------ |
     | SSH  | TCP      | 22   | 0.0.0.0/0 *(or your IP for security)* |

9. Review and **Launch**.

10. Select or create a **Key Pair (.pem)** file and download it.

### ✅ Connect via SSH:

```bash
chmod 400 your-key.pem
ssh -i your-key.pem ec2-user@<Public-IP>
```

---

## 📌 **Part B: Launch and Connect to Windows EC2 via RDP**

### ✅ Steps:

1. **EC2 Dashboard → Launch Instance**

2. Choose **Microsoft Windows Server 2022 Base AMI**.

3. Choose **t2.micro**

4. Configure details, storage, and optional tags.

5. **Security Group Settings**:

   * Inbound Rule:

     | Type | Protocol | Port | Source                                |
     | :--- | :------- | :--- | :------------------------------------ |
     | RDP  | TCP      | 3389 | 0.0.0.0/0 *(or your IP for security)* |

6. Review and Launch.

7. Use existing **Key Pair (.pem)**.

### ✅ Connect via RDP:

1. Select instance → Actions → Connect → RDP Client.
2. Download Remote Desktop file.
3. Get Windows password:

   * Actions → Get Windows Password.
   * Upload your `.pem` key.
   * Decrypt password.
4. Use **Public IP** and decrypted password in RDP client.

---

## 📌 **Part C: Install and Configure IIS on Windows EC2**

### ✅ Steps:

1. RDP into the Windows EC2 instance.
2. Open **Server Manager**.
3. Click **Manage** → **Add Roles and Features**.
4. Select **Role-based or feature-based installation**.
5. Choose the local server.
6. In **Server Roles**, check **Web Server (IIS)**.
7. Add features if prompted, then click **Next** until install.
8. Click **Install** and wait for completion.

### ✅ Verify IIS:

* Open **Internet Explorer / Edge**.
* Enter `http://localhost`
* You should see the **IIS welcome page**.

---

## 📌 **Deliverables**

* Public IP of Linux EC2 and successful SSH command screenshot.
* Public IP of Windows EC2 and RDP session screenshot.
* IIS welcome page screenshot.

---

## 📖 **Bonus** (Optional):

* Create a simple `index.html` on Linux EC2’s `/var/www/html` and test via browser.
* Host a custom web page on Windows IIS.

---

## ✅ Summary:

| Task                 | Linux EC2   | Windows EC2   |
| :------------------- | :---------- | :------------ |
| EC2 Launch           | ✅           | ✅             |
| Security Group Setup | ✅ (Port 22) | ✅ (Port 3389) |
| Connect (SSH / RDP)  | ✅           | ✅             |
| Install IIS          | ❌           | ✅             |

---



