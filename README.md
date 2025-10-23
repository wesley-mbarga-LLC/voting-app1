# Procedure to create a dynamic Runner:
1- Install jq (used to parse JSON):
    sudo apt-get install -y jq
2- Export your GitHub PAT (Personal Access Token):
    export GITHUB_PAT=ghp_xxx123456789yourtoken (use your real generated token here)

3- Run your script:(example ,run your actual script)
    chmod +x setup-github-runners.sh
    ./repo-runners.sh


# One-time GCP setup (run on your local terminal or Cloud Shell)

 # Set your project
gcloud config set project tactile-visitor-469118-d8

# (A) Add a network tag to your VM (use any tag name you like; we'll use "voting-runner")
gcloud compute instances add-tags wesley-vm \
  --zone=us-central1-c \
  --tags=voting-runner

# (B) Create a firewall rule that allows TCP 5000-5001 to VMs with that tag
gcloud compute firewall-rules create allow-voting-app-5000-5001 \
  --network=default \
  --direction=INGRESS \
  --priority=1000 \
  --action=ALLOW \
  --rules=tcp:5000-5001 \
  --source-ranges=0.0.0.0/0 \
  --target-tags=voting-runner \
  --description="Allow external access to Voting App (ports 5000-5001)"


    
