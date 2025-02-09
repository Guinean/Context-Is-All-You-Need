# Choose a specific Python version
FROM python:3.13.2-slim-bookworm  

#make sure git is installed so that building this from a repo will have vscode highlighting
RUN apt-get update && apt-get install -y --no-install-recommends git

# Set working directory inside the container
WORKDIR /workspaces/context_is_all_you_need  
#  /workspaces/your-project-name will be mounted to your local project folder

# Copy requirements.txt if it exists and install dependencies
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# [Optional] You can install other tools here if needed, e.g.,  `RUN apt-get update && apt-get install -y --no-install-recommends vim`
