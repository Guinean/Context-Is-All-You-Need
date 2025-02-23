# Choose a specific Python version
# FROM python:3.13.2-slim-bookworm #doesn't seem to work with knowledge-storm, some lower level linux packages needed must not be present?
FROM python:3.13.2-bookworm

#make sure git is installed so that building this from a repo will have vscode highlighting
RUN apt-get update && apt-get install -y --no-install-recommends git

# #add neo4j
# RUN wget -O - https://debian.neo4j.com/neotechnology.gpg.key | sudo gpg --dearmor -o /etc/apt/keyrings/neotechnology.gpg
# RUN apt-get install -y neo4j
# RUN echo "dbms.security.auth_enabled=true" >> /etc/neo4j/neo4j.conf
# # Use an environment variable in real setup #TODO
# RUN echo "dbms.security.initial_password=YOUR_INITIAL_PASSWORD" >> /etc/neo4j/neo4j.conf
# # Expose the Neo4j ports
# # HTTP
# EXPOSE 7474
# # Bolt
# EXPOSE 7687
# # Start Neo4j (you might want to customize this)#TODO # Or "neo4j", "start" and manage it with a process manager??
# CMD ["neo4j", "console"]

# Set working directory inside the container
WORKDIR /workspaces/context_is_all_you_need
#  /workspaces/your-project-name will be mounted to your local project folder

# Copy requirements.txt if it exists and install dependencies
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# [Optional] You can install other tools here if needed, e.g.,  `RUN apt-get update && apt-get install -y --no-install-recommends vim`
