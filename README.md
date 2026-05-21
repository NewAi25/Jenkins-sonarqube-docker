# Jenkins + SonarQube + Docker Pipeline

A sample web project that demonstrates a Dockerised CI/CD pipeline powered by Jenkins and SonarQube for automated builds, static code analysis and quality gating.

## What this project shows

This repo packages a small static site (HTML / CSS / JS) and the pipeline configuration needed to pull source from GitHub, build the project inside a Docker container, run SonarQube static analysis on every commit, enforce a quality gate before promoting the build, and publish the artifact or container image.

## Stack

Jenkins for orchestration and pipeline-as-code. SonarQube for code quality and security scanning. Docker for a reproducible build environment. HTML / CSS / JS for the sample application under test.

## Repository layout

index.html is the sample application entry point. tooplate-winter-gallery.css is the stylesheet. tooplate-winter-scripts.js holds the front-end logic. text.txt contains pipeline notes.

## Prerequisites

Docker installed locally. A running Jenkins instance with the SonarQube Scanner plugin. A SonarQube server reachable from Jenkins.

## Run Jenkins and SonarQube locally with Docker

```bash
docker run -d -p 8080:8080 -p 50000:50000 --name jenkins jenkins/jenkins:lts
docker run -d -p 9000:9000 --name sonarqube sonarqube:lts-community
```

Open Jenkins at http://localhost:8080 and SonarQube at http://localhost:9000, then configure the Jenkins job to point at this repo.

## Notes

This project is intended as a learning sandbox for CI/CD with quality gates. Use it as a starting point and replace the sample HTML site with your own application.

## License

MIT
