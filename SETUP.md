# Course Repository Setup

Complete this setup during Week 1. The goal is to confirm that you can access the course repository, edit files, work on isolated project branches, and submit work by pull request.

## 1. Create a GitHub account

Create a free GitHub account if you do not already have one: <https://github.com/signup>

Do not place passwords, phone numbers, home addresses, or other private information in this repository.

## 2. Fork the course repository

1. Sign in to GitHub.
2. Open the course repository.
3. Select **Fork**.
4. Keep the default repository name and select your account as the owner.
5. Create the fork.

Your work belongs in your fork. Projects are submitted back to the course repository through pull requests.

## 3. Choose an editing environment

### Option A — GitHub Codespaces

From your fork, select **Code → Codespaces → Create codespace on main**.

### Option B — VS Code locally

Install:

- Git: <https://git-scm.com/downloads>
- Visual Studio Code: <https://code.visualstudio.com/>
- Protégé Desktop for OWL work: <https://protege.stanford.edu/>

Clone your fork:

```bash
git clone https://github.com/YOUR-USERNAME/World-s-Ontology-Ecosystem-Long-Course.git
cd World-s-Ontology-Ecosystem-Long-Course
```

## 4. Add the course repository as `upstream`

From your local clone:

```bash
git remote add upstream https://github.com/Applied-Ontology-Education/World-s-Ontology-Ecosystem-Long-Course.git
git remote -v
```

## 5. Create a clean branch for **each** project

Projects must not build on the previous project branch. Before beginning each project:

```bash
git fetch upstream
git checkout main
git reset --hard upstream/main
git push origin main --force-with-lease
git checkout -b project-N
```

Replace `N` with the project number. This prevents a Project 2 pull request from accidentally containing all of Project 1’s commits.

If you are uncomfortable using `reset --hard`, use the equivalent GitHub Desktop/VS Code workflow described in `resources/github-workflow.md`.

## 6. Put your work in the submission directory

Use:

```text
submissions/YOUR-GITHUB-USERNAME/project-N/
```

Follow the project README for required filenames.

## 7. Commit and push

```bash
git add .
git commit -m "Complete Project N"
git push -u origin project-N
```

## 8. Open the pull request

Open a pull request from your `project-N` branch to the course repository’s `main` branch.

Use the repository pull-request template. Make sure the title begins with the project number, for example:

```text
Project 2 — jdoe — Careful Modeling
```

## 9. Peer review

For Projects 1–4, you must submit at least one substantive review of another student’s pull request. Use the structure in [`course/peer-review.md`](course/peer-review.md).

Use GitHub’s **Review changes** interface and submit the review as **Comment** unless the instructor directs otherwise. Do not use **Approve** or **Request changes** as a grade signal.

## 10. After grading

Do not reuse the old project branch. For the next project, return to Step 5 and create a new clean branch from the current upstream `main`.
