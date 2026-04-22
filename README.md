# GitHub Actions Starter 🚀

A minimal full-stack project to learn **CI/CD with GitHub Actions**.  
The backend is already built and tested. **Your job: write the workflow.**

---

## Project Structure

```
github-actions-starter/
├── backend/                   ← Express API (Node.js)
│   ├── index.js               ← API routes + helper functions
│   ├── index.test.js          ← Jest unit + integration tests
│   ├── .eslintrc.json         ← ESLint config
│   └── package.json
├── frontend/                  ← Plain HTML/CSS/JS UI
│   ├── index.html
│   ├── style.css
│   └── app.js
```

---

## Getting Started

### 1. Fork & Clone

```bash
# Fork this repo on GitHub, then:
git clone https://github.com/<your-username>/github-actions-starter.git
cd github-actions-starter
```

### 2. Run the backend locally

```bash
cd backend
npm install  
npm test          
npm run lint       
npm start          # start server on http://localhost:3000
```

### 3. Open the frontend
Open `frontend/index.html` in your browser.  
The status badge should turn green once the backend is running.

---

## Your Task 🎯

**Create the CI workflow file.**

1. Copy the starter template:
   ```bash
   cp .github/workflows/ci.starter.yml .github/workflows/ci.yml
   ```
2. Open `.github/workflows/ci.yml` and fill in every `TODO`.
3. Commit and push — watch the **Actions** tab in GitHub.

### What the pipeline should do

| Step | Command | Why |
|------|---------|-----|
| Checkout code | `actions/checkout@v4` | Runner needs your files |
| Setup Node | `actions/setup-node@v4` | Install correct Node version |
| Install deps | `npm ci` | Deterministic, faster than `npm install` |
| Lint | `npm run lint` | Catch style/syntax issues early |
| Test | `npm test` | Run all unit + integration tests |

Run the **same job for Node 18.x and 20.x** using a matrix strategy.

---

## Activities

### Activity 1 — Break it intentionally
- Push a bad indentation (use a tab instead of spaces in the YAML)  
- Watch it fail in the Actions tab, then fix it

### Activity 2 — Fail a test
In `backend/index.test.js`, change one expected value so a test fails:
```js
// change this:
expect(add(2, 3)).toBe(5);
// to this:
expect(add(2, 3)).toBe(99);
```
Push → see the red ✗ → revert → see the green ✓

### Closing Challenge
Add a **branch protection rule**:  
`Settings → Branches → Add rule → Require status checks before merging`  
Select your `build-and-test` check. Now open a PR with a failing test — GitHub should block the merge.

---

## API Reference

| Method | Route | Body | Response |
|--------|-------|------|----------|
| GET | `/` | — | `{ "status": "ok" }` |
| GET | `/greet/:name` | — | `{ "message": "Hello, Alice!" }` |
| POST | `/add` | `{ "a": 4, "b": 6 }` | `{ "result": 10 }` |

---

## Useful Links

- [GitHub Actions Docs](https://docs.github.com/en/actions)
- [actions/checkout](https://github.com/actions/checkout)
- [actions/setup-node](https://github.com/actions/setup-node)
- [actions/upload-artifact](https://github.com/actions/upload-artifact)
- [GitHub Marketplace](https://github.com/marketplace?type=actions)
