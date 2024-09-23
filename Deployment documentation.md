# Deploy on Azure using Github Actions

1. Connect to the VM machine using SSH
2. Follow the instructions to install Docker engine on https://docs.docker.com/engine/install/ubuntu/
3. Fork the repository and go to the settings of your forked repository, then click on "Secrets and Variables" -> "New Repository Secret".
4. Add your VM IP address to the GitHub secret named `SERVER_HOST`.
5. Add your VM user name (ubuntu) to the GitHub secret named `SERVER_USERNAME`.
6. Add your private key (key.pem) content into a new secret in GitHub named `SSH_KEY`. Make sure you replace all line breaks with '\n' for this field.
7. Create a new account on Docker Hub, then go to settings -> Security and add a new token with read/write access. Name this token as `DOCKERHUB_TOKEN` in your repository secrets.
8. Add your Docker Hub username to the GitHub secret named `DOCKERHUB_USERNAME`.
9. Make your changes and commit them, then push it to Github either on main or staging branch.
10. The deployed application should now be accessible via `http://<SERVER_HOST>:8000`.