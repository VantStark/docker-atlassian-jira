[![Open Issues](https://img.shields.io/github/issues/VantStark/docker-atlassian-jira.svg)](https://github.com/VantStark/docker-atlassian-jira/issues) [![Stars on GitHub](https://img.shields.io/github/stars/VantStark/docker-atlassian-jira.svg)](https://github.com/VantStark/docker-atlassian-jira/stargazers) [![Forks on GitHub](https://img.shields.io/github/forks/VantStark/docker-atlassian-jira.svg)](https://github.com/VantStark/docker-atlassian-jira/network) [![Stars on Docker Hub](https://img.shields.io/docker/stars/techzero/atlassian-jira.svg)](https://hub.docker.com/r/techzero/atlassian-jira/) [![Pulls on Docker Hub](https://img.shields.io/docker/pulls/techzero/atlassian-jira.svg)](https://hub.docker.com/r/techzero/atlassian-jira/)

# Supported tags and respective `Dockerfile` links

- [`8.13.0`, `8.13`, `8`, `latest`](https://github.com/VantStark/docker-atlassian-jira/blob/main/8.13.0/Dockerfile)

# Atlassian JIRA Software in a Docker container

This is a containerized installation of Atlassian JIRA Software with Docker, and it's a match made in heaven for us all to enjoy. The aim of this image is to keep the installation as straight forward as possible, but with a few Docker related twists.

## Get started

To quickly get started running a JIRA Software instance, use the following command:

```bash
docker run --name jira \
    -d \
    -v /path/to/jira:/var/atlassian/jira \
    -e TZ=<timezone> \
    -e X_PROXY_NAME="example.com" \
    -e X_PROXY_PORT="8080" \
    -e X_PROXY_SCHEME="https" \
    -p 8080:8080 \
    techzero/atlassian-jira:latest
```

Then simply navigate your preferred browser to `http://[dockerhost]:8080` and finish the configuration.

## Configuration

You can configure a small set of things by supplying the following environment variables

| Environment Variable | Description                                                                                      |
| -------------------- | ------------------------------------------------------------------------------------------------ |
| X_PROXY_NAME         | Sets the Tomcat Connectors `ProxyName` attribute                                                 |
| X_PROXY_PORT         | Sets the Tomcat Connectors `ProxyPort` attribute                                                 |
| X_PROXY_SCHEME       | If set to `https` the Tomcat Connectors `secure=true` and `redirectPort` equal to `X_PROXY_PORT` |
| X_PATH               | Sets the Tomcat connectors `path` attribute                                                      |
