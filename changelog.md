# Changelog
All notable changes to `cnj-logging-backend-quarkus` will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [2.1.0] - 2023-11-14
### Added
- added missing dependency on assertj
- tagging of git branch
### Changed
- Upgraded to helm-maven-plugin version 5.0.0
- Now a helm chart is packaged and pushed as an artifact during the commit-stage build
- Now the helm chart is pulled before deploying during the integration-test-stage build
- system tests are using the correct JBoss logger now
- removed dependency on cnj-common-test-jakarta by switching to model based system tests
- moved to reactive rest with jackson support to be compliant with other showcases
- upgraded Quarkus version to 3.5.0
- consolidated dependencies

## [2.0.0] - 2023-06-09
### Changed
- moved to new AWS CodeBuild build pipeline
- moved to new CloudTrain EKS cluster
- upgraded everything
- added docker-compose.yml to run the showcase locally

## [1.3.0] - 2023-02-24
### Changed
- minor changes to make build on AWS CodeBuild work

## [1.2.0] - 2022-03-12
### Added
### Changed
- re-release after repo split
