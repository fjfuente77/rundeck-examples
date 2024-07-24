FROM rundeck/rundeck:5.4.0

# Install dependencies
USER root
RUN apt-get update && \
    apt-get install -y curl && \
    apt-get clean

# Install the Rundeck CLI tool (rd)
RUN mkdir -p /opt/rundeck-cli && \
    curl -L "https://github.com/rundeck/rundeck-cli/releases/download/v2.0.8/rd-2.0.8.zip" -o /opt/rundeck-cli/rundeck-cli.zip && \
    unzip /opt/rundeck-cli/rundeck-cli.zip -d /opt/rundeck-cli/ && \
    ln -s /opt/rundeck-cli/rd-2.0.8/bin/rd /usr/local/bin/rd

# Set the PATH environment variable
ENV PATH="/opt/rundeck-cli:$PATH"

USER rundeck
