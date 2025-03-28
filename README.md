# ci-cd-python-demo

## Verify the Pipeline Execution
1. Go to your GitHub repository.
2. Click on the "Actions" tab.
3. You should see your CI/CD pipeline running.
4. It will:
   5. Checkout your code. 
   6. Set up Python and install dependencies. 
   7. Run your unit tests. 
   8. Simulate deployment.

## If you want to deploy to a server (e.g., DigitalOcean, AWS EC2), add a deployment step using SSH or Docker.

### Example (SSH Deployment):
```
- name: Deploy to server
  uses: appleboy/ssh-action@v0.1.7
  with:
    host: ${{ secrets.SERVER_HOST }}
    username: ${{ secrets.SERVER_USER }}
    key: ${{ secrets.SERVER_KEY }}
    script: |
      cd /path/to/app
      git pull origin main
      pip install -r requirements.txt
      systemctl restart app.service
```

## Key Takeaways
1. Pipeline Trigger: On push and pull_request events to the main branch.
2. CI/CD Workflow:
   3. Checkout code. 
   4. Set up Python. 
   5. Install dependencies. 
   6. Run unit tests. 
   7. Simulate deployment. 
8. GitHub Secrets: Use secrets for sensitive information when deploying to external servers.