```bash
#!/bin/bash

token=<[https://github.com/settings/tokens](Personal access token)>
username=anothergithubber

repo_name=$1

curl -X DELETE -H "Authorization: token $token" https://api.github.com/repos/$username/$repo_name
```
