# ☁️ Google Cloud Console & CLI — Quick Master Guide  
### Focused for Cloud + AI Engineering & Automation Workflows  

---

## 🎯 Objective  
To gain practical command-line and console fluency for deploying, managing, and securing cloud resources used in **AI-integrated systems** — without unnecessary complexity.

---

## ⚙️ 1. Setup & Authentication  

**Install Google Cloud CLI (gcloud)**
```bash
# macOS / Linux
curl https://sdk.cloud.google.com | bash

# Windows (PowerShell)
Invoke-WebRequest "https://dl.google.com/dl/cloudsdk/channels/rapid/GoogleCloudSDKInstaller.exe" -OutFile "installer.exe"
Start-Process .\installer.exe
````

**Initialize CLI**

```bash
gcloud init
```

> Connects CLI with your Google account and sets your default project.

**Authenticate for APIs and Python SDKs**

```bash
gcloud auth application-default login
```

> Enables your local Python/OpenAI scripts to access GCP services securely.

---

## 🏗️ 2. Project & Configuration Basics

**List Existing Projects**

```bash
gcloud projects list
```

**Create New Project**

```bash
gcloud projects create my-cloud-ai-project
```

**Set Active Project**

```bash
gcloud config set project my-cloud-ai-project
```

**View Current Config**

```bash
gcloud config list
```

---

## 💻 3. Compute Engine — VM Deployment

**Enable Compute Engine API**

```bash
gcloud services enable compute.googleapis.com
```

**Create VM Instance**

```bash
gcloud compute instances create ai-lab-vm \
    --zone=us-central1-a \
    --machine-type=e2-medium \
    --image-family=debian-12 \
    --image-project=debian-cloud
```

**List VM Instances**

```bash
gcloud compute instances list
```

**Connect via SSH**

```bash
gcloud compute ssh ai-lab-vm --zone=us-central1-a
```

**Delete Instance**

```bash
gcloud compute instances delete ai-lab-vm --zone=us-central1-a
```

---

## 📦 4. Cloud Storage — Data & File Management

**Create Bucket**

```bash
gcloud storage buckets create gs://my-cloud-ai-bucket --location=US
```

**Upload File**

```bash
gcloud storage cp mission.txt gs://my-cloud-ai-bucket
```

**Download File**

```bash
gcloud storage cp gs://my-cloud-ai-bucket/mission.txt .
```

**List Buckets**

```bash
gcloud storage buckets list
```

---

## 🔐 5. IAM & Security Essentials

**List All Users and Roles**

```bash
gcloud projects get-iam-policy my-cloud-ai-project
```

**Add IAM Member**

```bash
gcloud projects add-iam-policy-binding my-cloud-ai-project \
    --member="user:username@gmail.com" \
    --role="roles/viewer"
```

**Remove IAM Member**

```bash
gcloud projects remove-iam-policy-binding my-cloud-ai-project \
    --member="user:username@gmail.com" \
    --role="roles/viewer"
```

**List Available Roles**

```bash
gcloud iam roles list
```

---

## 🧩 6. Cloud Run / Cloud Functions — AI Integration Hosting

**Enable Required APIs**

```bash
gcloud services enable run.googleapis.com cloudfunctions.googleapis.com
```

**Deploy Cloud Function (Python example)**

```bash
gcloud functions deploy ai-endpoint \
    --runtime python311 \
    --trigger-http \
    --allow-unauthenticated \
    --entry-point main
```

**Deploy Container to Cloud Run**

```bash
gcloud run deploy ai-service \
    --image gcr.io/my-cloud-ai-project/ai-app:latest \
    --region us-central1 \
    --allow-unauthenticated
```

> These services host your OpenAI-powered automation or chat applications on GCP.

---

## 📊 7. Monitoring & Logging

**View Logs (Cloud Logging)**

```bash
gcloud logging read "resource.type=gce_instance" --limit=10
```

**List Monitoring Metrics**

```bash
gcloud monitoring metrics list
```

**Check Service Health**

```bash
gcloud compute instances describe ai-lab-vm --zone=us-central1-a
```

---

## 🧠 8. Cleanup & Maintenance

**List All Resources**

```bash
gcloud assets list --project=my-cloud-ai-project
```

**Disable APIs**

```bash
gcloud services disable compute.googleapis.com
```

**Delete Project (Final Cleanup)**

```bash
gcloud projects delete my-cloud-ai-project
```

---

## 🧭 9. Practice Flow Summary

1. **Create Project** → `gcloud projects create`
2. **Enable APIs** → `gcloud services enable`
3. **Deploy Resource** → `gcloud compute / run / functions`
4. **Secure Access** → `gcloud projects add-iam-policy-binding`
5. **Monitor Logs** → `gcloud logging read`
6. **Automate / Integrate with Python** → via `gcloud auth application-default login`

---

## 🧮 10. Quick Reference Table

| Command                           | Purpose                | Example                     |
| --------------------------------- | ---------------------- | --------------------------- |
| `gcloud init`                     | Initialize environment | Configure account & project |
| `gcloud config set project`       | Set default project    | `my-cloud-ai-project`       |
| `gcloud compute instances create` | Launch VM              | `ai-lab-vm`                 |
| `gcloud storage buckets create`   | Create storage         | `my-bucket`                 |
| `gcloud functions deploy`         | Deploy AI API endpoint | `ai-endpoint`               |
| `gcloud run deploy`               | Deploy container app   | `ai-service`                |
| `gcloud iam roles list`           | List IAM roles         | View permissions            |
| `gcloud logging read`             | View logs              | Resource health             |
| `gcloud projects delete`          | Cleanup                | Remove old project          |

---

## 💬 Professional Insight

> ⚡ **Master the commands — but think like an architect.**
> You’re not just running instances; you’re *designing intelligent systems* that integrate AI, automation, and security across cloud environments.

---

✍️ **Created & Curated by**
**Muhammad Naveed Ishaque**
*Learning to engineer intelligence in systems and discipline in self — through AI, Cloud, and Fitness Science.*

> “Where technology builds the world — and discipline builds the self.”

```

---

Would you like me to add a **“5-Day GCloud CLI Practice Lab Plan”** (daily tasks for skill consolidation — create, secure, deploy, monitor, clean-up) right after this section to help you implement it systematically?
```
