# GitHub Workflow for Projects

## Start each project from current upstream `main`

```bash
git fetch upstream
git checkout main
git reset --hard upstream/main
git checkout -b project-N
```

Work only on the project branch.

## Submit

```bash
git add .
git commit -m "Complete Project N"
git push -u origin project-N
```

Open a pull request to the course repository.

## Review a classmate

1. Open the assigned project pull request.
2. Read the project README before reviewing.
3. Inspect the changed files.
4. Use **Files changed** to comment on specific content where helpful.
5. Use **Review changes → Comment** to submit the required structured review.
6. Include Strength, Question or Concern, and Recommendation.

Do not merge another student’s pull request.
