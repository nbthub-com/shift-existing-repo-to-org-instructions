# NbtHub Instructions for shifting existing Git projects to the organization's GitHub profile

## **Prerequisites**

1. Verify you have an account on [GitHub.com](github.com)
2. Verify that you have joined the organization through the invitation
3. Make sure you have no pending changes on your local before executing the shifting process
4. Please read all the instructions before execution
5. Please contact [me](mailto:awais.jameel@ymail.com "CTO") if you have any questions

## Create new repo

1. Go to [https://github.com/new](https://github.com/new)
2. select "nbthhub-com" as the owner
3. select the project domain name as the {git-repository-name} or use the appropriate project name as {git-repository-name}
4. (opt) add project a brief description.
5. select private
6. leave all the other options as is the default
7. click "Create Repository"

## Pushing existing projects to the new repo from your local machine

```bash
git checkout main
git remote remove origin
git remote add origin https://{your-github-username}@github.com/nbthub-com/{git-repository-name}.git
git branch -M main
git push -u origin main
git config --local user.name "{your-GitHub-username}"
git config --local user.email "{your-GitHub-email}"
git branch --set-upstream-to=origin/main
```

## Shifting the existing project to the new repo on the server

```bash
git remote remove origin
git remote add origin https://{your-GitHub-username}:{personal-excess-token}@github.com/nbthub-com/{git-repository-name}.git
git pull origin main
git branch --set-upstream-to=origin/main
```
