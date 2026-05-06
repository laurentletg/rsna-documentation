# rsna-documentation
View documentation at : https://anw1998.github.io/rsna-documentation/
* Ask one of your colleagues for the password!
* To avoid having to enter the password at every page, press `Ctrl` + `Enter` instead of `Enter` as you confirm the password input.

I followed this tutorial: https://www.youtube.com/watch?v=Q-YA_dA8C20&t=292s

Clone the repo and edit .md files in /docs


## Setting password locally

At build time:
```bash
echo "password: your_password" > _config.yml
```



## Setting password on GitHub Pages

### Add the secret in GitHub
- Go to your repo → Settings → Secrets and variables → Actions
- Click New repository secret
- Name: MKDOCS_PASSWORD, Value: your chosen password
- Save, then re-run the CI workflow (or push a commit to trigger it)
After the redeploy the site will prompt for the password.