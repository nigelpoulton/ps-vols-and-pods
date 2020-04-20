FROM alpine
LABEL maintainer="Nigel Poulton nigelpoulton@hotmail.com @nigelpoulton"

# Install curl and latest version of kubectl
RUN apk update && \
  apk add curl && \
  curl -LO https://storage.googleapis.com/kubernetes-release/release/`curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt`/bin/linux/amd64/kubectl && \
  chmod +x ./kubectl && \
  mv ./kubectl /usr/local/bin/kubectl

# Copy main app file
COPY ambassador.sh /ambassador.sh

RUN chmod +x /ambassador.sh

# Set app to run when container is started
ENTRYPOINT /ambassador.sh