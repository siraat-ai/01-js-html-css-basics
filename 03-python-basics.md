# 🐍 Python Mini-Course Cheat Sheet  
### Targeted for Cloud + AI Automation & OpenAI API Integration  

---

## ⚙️ 1. Setup & Environment  

**Install Python & Libraries**
```bash
# Check version
python --version

# Install pip (if missing)
python -m ensurepip --upgrade

# Install essential libraries
pip install openai requests google-cloud-storage
````

**Create and run a Python file**

```bash
# Create
nano app.py

# Run
python app.py
```

---

## 💡 2. Core Syntax Essentials

**Variables**

```python
name = "Naveed"
age = 28
is_active = True
```

**Data Types**

```python
text = "AI Cloud"
number = 42
items = ["AI", "Cloud", "Security"]
info = {"project": "OpenAI Integration", "status": "Active"}
```

**Printing**

```python
print("Mission:", info["project"])
```

---

## 🔁 3. Control Flow

**If-Else**

```python
if age > 18:
    print("Access granted.")
else:
    print("Access denied.")
```

**Loops**

```python
for item in items:
    print("Learning:", item)

count = 0
while count < 3:
    print("Iteration:", count)
    count += 1
```

---

## 🧩 4. Functions

**Define & Use**

```python
def greet_user(name):
    return f"Hello, {name}! Welcome to Cloud + AI."

print(greet_user("Naveed"))
```

**With Parameters**

```python
def add(a, b):
    return a + b
result = add(10, 5)
print(result)
```

---

## 📦 5. Working with Libraries

**Importing Modules**

```python
import math
import requests
```

**Example: Simple API Call**

```python
response = requests.get("https://api.github.com")
print(response.status_code)
```

---

## 🧠 6. File Operations

```python
# Write to file
with open("notes.txt", "w") as file:
    file.write("Cloud + AI Mission Log")

# Read file
with open("notes.txt", "r") as file:
    content = file.read()
    print(content)
```

---

## 🤖 7. Using OpenAI API (Core Task)

```python
import openai

openai.api_key = "YOUR_API_KEY"

response = openai.Completion.create(
    model="gpt-3.5-turbo-instruct",
    prompt="Write a cloud security checklist",
    max_tokens=100
)

print(response["choices"][0]["text"])
```

**Modern Chat API Example**

```python
from openai import OpenAI
client = OpenAI(api_key="YOUR_API_KEY")

chat = client.chat.completions.create(
    model="gpt-4o-mini",
    messages=[{"role": "user", "content": "Explain IAM in Google Cloud"}]
)

print(chat.choices[0].message.content)
```

---

## ☁️ 8. Interacting with Google Cloud (Example)

**Upload File to Cloud Storage**

```python
from google.cloud import storage

client = storage.Client()
bucket = client.bucket("my-cloud-ai-bucket")
blob = bucket.blob("mission.txt")
blob.upload_from_filename("notes.txt")

print("File uploaded successfully.")
```

> 🔐 *Note:* Authentication handled via `gcloud auth application-default login`

---

## ⚡ 9. Error Handling

```python
try:
    result = 10 / 0
except Exception as e:
    print("Error:", e)
finally:
    print("Process complete.")
```

---

## 🧮 10. Quick Reference Summary

| Concept    | Example              | Use Case               |
| ---------- | -------------------- | ---------------------- |
| Variable   | `x = 10`             | Store values           |
| List       | `[1,2,3]`            | Multiple items         |
| Dict       | `{"key": "value"}`   | Key-value storage      |
| If/Else    | `if x>0:`            | Conditional logic      |
| Loop       | `for i in range(3):` | Repeat actions         |
| Function   | `def run():`         | Reusable block         |
| Import     | `import openai`      | Use libraries          |
| API Call   | `requests.get()`     | Cloud/A.I. integration |
| Try/Except | Error handling       | Stability              |
| File I/O   | `open("file.txt")`   | Logs / configs         |

---

## 🧭 Practical Workflow for Projects

1. **Prototype AI Logic** → Build in Python using OpenAI API.
2. **Host & Automate** → Use Cloud Functions or Cloud Run.
3. **Secure & Scale** → Apply IAM and Cloud Security principles.
4. **Document Results** → Save logs, outputs, and insights.

---

✍️ **Created & Curated by**
**Muhammad Naveed Ishaque**
*Learning to engineer intelligence in systems and discipline in self — through AI, Cloud, and Fitness Science.*

> “Where technology builds the world — and discipline builds the self.”

```

---

Would you like me to add a **“Mini Practice Lab Section”** at the end (5 short Python tasks) to help you apply these commands practically before starting your courses?

