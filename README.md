# Procedure to create a dynamic Runner:
1- Install jq (used to parse JSON):
    sudo apt-get install -y jq
2- Export your GitHub PAT (Personal Access Token):
    export GITHUB_PAT=ghp_xxx123456789yourtoken (use your real generated token here)

3- Run your script:(example ,run your actual script)
    chmod +x setup-github-runners.sh
    ./repo-runners.sh
    
