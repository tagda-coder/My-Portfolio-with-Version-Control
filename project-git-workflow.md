Here's the all required Steps to maintain the workflow of portfolio project with git Versions Control

1. Build different versions (`v1`, `v2`, `v3`…)
2. Update any version anytime
3. Switch easily between them

---

# 🔥 Portfolio Workflow (Best Mix of Branches + Folders)

### 📌 Step 1: Setup Project Structure

```bash
portfolio-hub/
  ├── index.html          # hub page with buttons to v1, v2, v3
  ├── portfolio-v1/       # first version
  ├── portfolio-v2/       # second version
  ├── portfolio-v3/       # third version
```

👉 Each `portfolio-vX` is a full project (HTML/React/Tailwind etc.).

---

### 📌 Step 2: Initialize Git

```bash
git init
git add .
git commit -m "Initial commit: hub + v1, v2, v3"
git branch -M main
git remote add origin <your-repo-url>
git push -u origin main
```

---

### 📌 Step 3: Create Branches per Version

(So you can isolate updates to one version without breaking others)

```bash
git checkout -b v1
# work only in portfolio-v1 folder
git add .
git commit -m "Updated portfolio v1"
git push origin v1
```

```bash
git checkout -b v2
# work only in portfolio-v2 folder
git add .
git commit -m "Improved portfolio v2 navbar"
git push origin v2
```

👉 Now each version has its **own branch**.

---

### 📌 Step 4: Hub Page Linking

Your `index.html` in the root (main branch) will link to deployed versions:

```html
<h1>Choose a Portfolio Version 🚀</h1>
<ul>
  <li><a href="/portfolio-v1/">View Version 1</a></li>
  <li><a href="/portfolio-v2/">View Version 2</a></li>
  <li><a href="/portfolio-v3/">View Version 3</a></li>
</ul>
```

---

### 📌 Step 5: Updating a Version

Example: Update **v2**

```bash
git checkout v2
cd portfolio-v2
# make changes
git add .
git commit -m "Added animations to v2"
git push origin v2
```

👉 Only `portfolio-v2` is updated.

👉 `v1` and `v3` remain safe.

---

### 📌 Step 6: Deployment

* If you use **Vercel / Netlify** → set separate deploys for each branch (`v1`, `v2`, `v3`).
* Or deploy one repo where `/portfolio-vX` folders are hosted, and your hub (`index.html`) links to them.

---

✅ **Result:**

* Easy to **test multiple versions**
* Easy to **switch**
* Easy to **update any version** without breaking others

---

Made with ❤️
