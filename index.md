delete-repo

```bash
#!/bin/bash

token=<Personal access token>
username=anothergithubber

repo_name=$1

curl -X DELETE -H "Authorization: token $token" https://api.github.com/repos/$username/$repo_name
```

[Personal access tokens](https://github.com/settings/tokens)

---

eval-agent

```bash
#!/bin/bash
eval $(ssh-agent -s)
ssh-add id_rsa
```

```bash
. eval-agent 
```

---

create-repo-push-readme

```bash
#!/bin/bash

DIRECTORY=~/$1

if [ ! -d "$DIRECTORY" ]; then
    token=<Personal access token>
    username=anothergithubber

    repo_name=$1

    curl -u "$username:$token" https://api.github.com/user/repos -d '{"name":"'$repo_name'"}'

    mkdir ~/$1 && cd ~/$1
    git init
    git remote add origin git@github.com:anothergithubber/$1.git
    touch README.md
    git add .
    git checkout -b gh-pages
    git commit -m "Initial commit"
    git push origin gh-pages
else
    echo 'Directory exists!'
fi
```
