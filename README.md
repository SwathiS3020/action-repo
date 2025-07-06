# 🔄 action-repo – GitHub Webhook Trigger (Developer Assessment Task – Apr 2021)

This repository is part of a full-stack solution for the Developer Assessment Task. It is designed to simulate typical GitHub activity — such as pushing code, opening pull requests, and merging branches — in order to trigger webhook events. These events are received and processed by a companion Flask backend (`webhook-repo`) that stores and displays them.

---

## 📌 Objective

This repository exists to generate real GitHub webhook activity. Each action (push, PR, merge) sends a payload to the webhook endpoint hosted by [`webhook-repo`](https://github.com/your-username/webhook-repo). This setup mimics real-world development workflows and is used to test full webhook integration.

---

## 🚀 Webhook Configuration Steps

To connect this repo to your webhook-repo backend:

1. Go to **Settings → Webhooks → Add Webhook**
2. In **Payload URL**, paste your ngrok forwarding URL:
https://your-ngrok-url/webhook
3. Set **Content type** to: `application/json`
4. Choose the following events:
- ✅ Push events
- ✅ Pull request events
5. Click **Add webhook**

---

## 🔁 Actions That Trigger Webhooks

### 🔁 Webhook-Triggering GitHub Actions

| Action Type     | How to Trigger                                                                 |
|------------------|--------------------------------------------------------------------------------|
| **Push**         | Commit and push code to any branch (e.g., `main`, `dev`, `feature/*`)          |
| **Pull Request** | Open a pull request from one branch to another (e.g., `feature/login → main`)  |
| **Merge**        | Merge a pull request or push a commit with `"merge"` in the message            |

Each of these actions will automatically trigger a webhook event to the Flask server running in the `webhook-repo`.


---

## 🧪 Example Workflow

```bash
# 1. Create a new feature branch
git checkout -b feature/homepage

# 2. Make changes and commit
git add .
git commit -m "Add homepage layout"

# 3. Push to GitHub
git push origin feature/homepage

# 4. Open a PR from 'feature/homepage' → 'main'

# 5. Merge the PR
