# 🚀 CI/CD Workflow Summary for Role-Based Career Path Platform

This document summarizes the setup and execution of **Continuous Integration (CI)** and **Continuous Deployment (CD)** using **GitHub Actions** for a project hosted on GitHub and deployed via **GitHub Pages**.

---

## 📁 Project Info

- **Repository:** `my-first-repo`
- **Live Site:** [https://srisha516.github.io/my-first-repo/](https://srisha516.github.io/my-first-repo/)
- **Branch:** `main`
- **Author:** Srisha S

---

## ✅ Continuous Integration (CI)

### 🔹 Purpose:
To validate every code push by:
- Installing dependencies
- Building the project
- Running optional tests

### 📄 Workflow File: `.github/workflows/ci.yml`

```yaml
name: CI - Build Check

on:
  push:
    branches: [main]

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
    - uses: actions/checkout@v3

    - name: Setup Node.js
      uses: actions/setup-node@v3
      with:
        node-version: 18

    - name: Install Dependencies
      run: npm install

    - name: Build
      run: npm run build
