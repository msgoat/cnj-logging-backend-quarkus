# cnj-logging-backend-quarkus

Cloud native Quarkus backend with support of cluster logging using an EFK stack:
* everything is logged to stdout (no file appenders)
* uses JSON logging format

The application is packaged as a multi-architecture docker image which supports the following platforms:
* linux/amd64
* linux/arm64/v8

## Synopsis

### Enable JSON logging in Quarkus

In order to switch Quarkus to JSON logging output format, you will have to proceed through the following steps:

#### Add a dependency to the JSON logging extension

Add a dependency to the JSON logging extension to your POM:

```xml
<dependency>
    <groupId>io.quarkus</groupId>
    <artifactId>quarkus-logging-json</artifactId>
</dependency>
```
### Temporarily switching off JSON logging

JSON formatted log files are hard to read for humans. Fortunately, you can switch off JSON logging by adding
a profiled configuration property to your application.properties file:

```properties
%dev.quarkus.log.console.json=false
```
Now if you activate profile __dev__, JSON logging will be switched off, although the JSON logging extension has been added to your application.

> Quarkus profiles are activated by adding an envvar `QUARKUS_PROFILE` with the name of the profile to activate to your Docker container configuration.

## Status

![Build status](https://codebuild.eu-west-1.amazonaws.com/badges?uuid=eyJlbmNyeXB0ZWREYXRhIjoiN2FHN1daY05KUjNEbUgvSXdMUmd3YnZscVNCUklGU2xqeWVjSFBFOWZiZ1NMSFBOSHg2ZVNuVHFmeW5PWlVuN1hFUTNDQkVma1NLbzRESklPeTFIRkdVPSIsIml2UGFyYW1ldGVyU3BlYyI6IjFZS1VaM21xbCtLN0gvYlIiLCJtYXRlcmlhbFNldFNlcmlhbCI6MX0%3D&branch=main)

## Release information

Check [changelog](changelog.md) for latest version and release information.

## Docker Pull Command

`docker pull docker.cloudtrain.aws.msgoat.eu/cloudtrain/cnj-logging-backend-quarkus`

## Helm Pull Command

`helm pull docker.cloudtrain.aws.msgoat.eu/cloudtrain-charts/cnj-logging-backend-quarkus`

## HOW-TO build this application locally

If all prerequisites are met, just run the following Maven command in the project folder:

```shell 
mvn clean verify -P pre-commit-stage
```

Build results: a Docker image containing a Spring Boot application.

## HOW-TO run this showcase locally

In order to run the whole showcase locally, just run the following docker commands in the project folder:

```shell 
docker compose up -d
docker compose logs -f 
```
The showcase application will be accessible via `http://localhost:38090`.

Press `Ctlr+c` to stop tailing the container logs and run the following docker command to stop the show case:

```shell 
docker compose down
```
