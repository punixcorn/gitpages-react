# Script to set up GitHub pages

sets up the configuration for **gitpages** </br>
 
just pass in your **github username** and the **repo name ( the name of the repo in github )** </br>
###### NB : replace **\<repo name\>**  with your repository name  and **\<username\>** with your github username


### RUN

-   clone the file
```
  wget  https://raw.githubusercontent.com/punixcorn/gitpages-react/main/main.sh
  chmod +x main.sh
```

-   run

```bash
  ./main.sh <username> <repo name>
```
- then push your changes to your repo ( newly created one or not, it should exist )
```bash
  git remote add origin git@github.com:<username>/<repo name>
  git branch -M main
  git push -u origin main
```
- finally deploy using:
```bash
    npm run deploy
```
- your deployed app should be at
```
https://<username>.github.io/<repo name>/
```

# offical Documentation

[react git pages](https://create-react-app.dev/docs/deployment/#github-pages)
