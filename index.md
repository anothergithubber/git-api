```bash
#!/bin/bash

token=<Personal access token>
username=anothergithubber

repo_name=$1

curl -X DELETE -H "Authorization: token $token" https://api.github.com/repos/$username/$repo_name
```

[Personal access tokens](https://github.com/settings/tokens)

eval-agent

```bash
#!/bin/bash
eval $(ssh-agent -s)
ssh-add id_rsa
```

```bash
. eval-agent 
```
