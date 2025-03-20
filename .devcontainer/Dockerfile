# FROM mcr.microsoft.com/devcontainers/python:1-${templateOption:imageVariant}
FROM python:3.12.9-bookworm

ENV PYTHONUNBUFFERED=1

#make sure git is installed so that building this from a repo will have vscode highlighting
RUN apt-get update && apt-get install -y git

# Copy requirements.txt if it exists and install dependencies
COPY requirements.txt /workspaces/ciayn/requirements.txt
RUN pip install --no-cache-dir -r /workspaces/ciayn/requirements.txt

# COPY PostCreateLast_requirements_frozen.txt .
# RUN pip install --no-cache-dir -r PostCreateLast_requirements_frozen.txt

# RUN pip freeze > requirements_last_frozen.txt #This didn't work as i expected. Before having issues with working dir. so maybe will if that was ongoing and is fixed in the future?

# [Optional] You can install other tools here if needed, e.g.,  `RUN apt-get update && apt-get install -y --no-install-recommends vim`

#Optional. Start the r2r server in the docker container. I will just run this in a bash shell manually while developing since I may need to restart it etc.
# CMD ["python", "-m", "r2r.serve"]


