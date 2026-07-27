# 🚀 GitHub Actions - Level 1 (Beginner Guide)

> Learn GitHub Actions from scratch with simple explanations and real-world examples.

---

# 📖 What is GitHub Actions?

GitHub Actions is an **automation service** provided by GitHub.

It automatically performs tasks whenever something happens in your repository (such as pushing code, creating a pull request, or releasing a new version).

Instead of doing repetitive work manually, GitHub does it for you.

---

# 🏢 Real-Life Example

Imagine you own a restaurant.

Every morning your staff performs the same tasks:

```
Open Restaurant
        ↓
Clean Tables
        ↓
Cook Food
        ↓
Serve Customers
        ↓
Close Restaurant
```

Those tasks happen automatically every day.

GitHub Actions works the same way.

Whenever something happens in your repository, GitHub automatically performs the tasks you define.

---

# 🤖 What Can GitHub Actions Do?

GitHub Actions can automatically:

- ✅ Build your project
- ✅ Test your code
- ✅ Check code quality
- ✅ Deploy your website
- ✅ Create releases
- ✅ Run scripts
- ✅ Send notifications
- ✅ Publish packages
- ✅ Run AI or Python scripts
- ✅ Automate almost anything

---

# 🌍 Where is GitHub Actions Used?

GitHub Actions is commonly used in:

- HTML Projects
- CSS Projects
- JavaScript Projects
- React Projects
- Next.js Projects
- Node.js Projects
- Express.js APIs
- MERN Stack Applications
- Python Projects
- AI Applications
- Mobile Apps
- Open Source Projects

---

# 💡 Why Learn GitHub Actions?

Without GitHub Actions:

```
Write Code
      ↓
Build Project Manually
      ↓
Run Tests Manually
      ↓
Deploy Manually
```

With GitHub Actions:

```
Write Code
      ↓
git push
      ↓
GitHub Builds
      ↓
Runs Tests
      ↓
Deploys Automatically
```

This saves time and reduces human mistakes.

---

# 📂 Folder Structure

GitHub always looks inside:

```
.github/
└── workflows/
```

Example:

```
MyProject/

├── .github/
│   └── workflows/
│       ├── first.yml
│       ├── build.yml
│       └── deploy.yml
│
├── src/
├── package.json
└── README.md
```

> Every workflow file must be inside `.github/workflows/`.

---

# 📄 Workflow File

A workflow is written in YAML.

Example:

```yaml
name: My First GitHub Action

on:
  push:

jobs:
  hello:
    runs-on: ubuntu-latest

    steps:
      - name: Say Hello
        run: echo "Hello World!"
```

---

# 🧱 Basic Workflow Structure

```
Workflow
     │
     ▼
name
     │
     ▼
on
     │
     ▼
jobs
     │
     ▼
job
     │
     ▼
runs-on
     │
     ▼
steps
     │
     ▼
run
```

---

# 🔑 Common Keywords

These keywords appear in almost every GitHub Actions workflow.

| Keyword | Purpose | Changes? |
|----------|----------|----------|
| name | Workflow name | ✅ Yes |
| on | Event trigger | ✅ Yes |
| jobs | Group of work | ❌ No |
| job-name | Job identifier | ✅ Yes |
| runs-on | Operating system | ✅ Sometimes |
| steps | Individual tasks | ❌ No |
| - name | Step title | ✅ Yes |
| run | Execute terminal command | ❌ Keyword stays, command changes |

---

# 📘 Explanation of Every Keyword

## 1️⃣ name

```yaml
name: My First GitHub Action
```

The workflow title shown in the **Actions** tab.

Examples:

```yaml
name: Build Project
```

```yaml
name: Deploy Website
```

```yaml
name: Test Backend
```

---

## 2️⃣ on

```yaml
on:
  push:
```

This tells GitHub **when to run the workflow**.

Think of it as a trigger.

Without `on`, GitHub doesn't know when to start.

---

## 3️⃣ jobs

```yaml
jobs:
```

A workflow contains one or more jobs.

Example:

```
Workflow

├── Job 1
└── Job 2
```

---

## 4️⃣ Job Name

```yaml
build:
```

or

```yaml
hello:
```

or

```yaml
deploy:
```

This is simply the job's identifier.

---

## 5️⃣ runs-on

```yaml
runs-on: ubuntu-latest
```

This tells GitHub which operating system to use.

Common options:

```yaml
ubuntu-latest
```

```yaml
windows-latest
```

```yaml
macos-latest
```

Most projects use **ubuntu-latest**.

---

## 6️⃣ steps

```yaml
steps:
```

A job is divided into small tasks called steps.

Example:

```
Cook Food

↓

Boil Water

↓

Add Tea

↓

Serve
```

Each task is one step.

---

## 7️⃣ Step Name

```yaml
- name: Install Packages
```

This is only a label shown inside GitHub Actions.

---

## 8️⃣ run

```yaml
run:
```

Runs a terminal command.

Example:

```yaml
run: echo "Hello"
```

Later you'll use commands like:

```yaml
run: npm install
```

```yaml
run: npm test
```

```yaml
run: npm run build
```

---

# ⚡ Common Triggers

## Push

```yaml
on:
  push:
```

Runs whenever you push code.

---

## Pull Request

```yaml
on:
  pull_request:
```

Runs whenever someone creates a Pull Request.

---

## Manual

```yaml
on:
  workflow_dispatch:
```

Adds a **Run Workflow** button.

---

# 💻 Common Operating Systems

Ubuntu

```yaml
runs-on: ubuntu-latest
```

Windows

```yaml
runs-on: windows-latest
```

macOS

```yaml
runs-on: macos-latest
```

---

# 📂 Multiple Workflow Files

One project can contain many workflow files.

Example:

```
.github/

└── workflows/

    ├── build.yml
    ├── deploy.yml
    ├── test.yml
    ├── lint.yml
    └── release.yml
```

Each file is a separate workflow.

---

# 🚀 What Happens When You Push?

Suppose:

```
build.yml

on:
  push:
```

```
test.yml

on:
  push:
```

```
deploy.yml

on:
  push:
```

When you execute:

```bash
git push
```

GitHub does this:

```
Push Event
      │
      ▼
Checks All Workflow Files
      │
      ├── build.yml
      ├── test.yml
      └── deploy.yml
```

Since all three listen for **push**, all three run.

---

# 📊 Beginner Workflow

```yaml
name: My First GitHub Action

on:
  push:

jobs:
  hello:
    runs-on: ubuntu-latest

    steps:
      - name: Introduction
        run: echo "Hello! My name is Waqar."

      - name: Goal
        run: echo "I want to become an AI Engineer."

      - name: Learning
        run: echo "Today I learned GitHub Actions!"
```

---

# 🧠 Important Rules

✅ Workflow files must be inside:

```
.github/workflows/
```

✅ GitHub reads every `.yml` or `.yaml` file inside that folder.

✅ Every workflow is independent.

✅ One `git push` can trigger multiple workflows if they all use:

```yaml
on:
  push:
```

✅ Every workflow runs on its own temporary virtual machine.

---

# 📚 Level 1 Summary

After completing Level 1, you should know:

- What GitHub Actions is
- Why companies use it
- What a workflow is
- Folder structure
- YAML basics
- Common keywords
- Triggers
- Jobs
- Steps
- Runs-on
- Multiple workflow files
- Push event
- How GitHub automatically executes workflows

---

# 🎯 Next Level

In Level 2, you'll learn:

- workflow_dispatch
- pull_request
- Multiple Jobs
- Job Dependencies
- Branch Filters
- Conditions
- GitHub Marketplace Actions

---