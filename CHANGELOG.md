# Changelog

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/), and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

---
## [18.0.4-bb.0] - 2023-09-20
### Changed
- Updated to latest chart upstream
- Updated to 7.2.1 redis version
- Updated redis-exporter to v1.54.0

## [17.15.4-bb.0]
### Changed
- Updated to latest chart upstream
- Updated to 7.2.0 redis version
- Updated redis-exporter to v1.52.0

## [17.13.2-bb.0]
### Changed
- Updated to latest chart upstream
- Updated to 7.0.12 redis version

## [17.10.2-bb.1]
### Changed
- Updated imagePullSecrets to de-duplicate

## [17.10.2-bb.0]
### Changed
- Updated to Redis 7.0.11 and 17.10.2 upstream chart

## [17.9.3-bb.0]
### Changed
- Updated redis-exporter to v1.50.0

## [17.9.1-bb.0]
### Changed
- Updated redis to v7.0.10
- Updated redis-exporter to v1.48.0

## [16.12.3-bb.4]
### Changed
- Updated redis-exporter to v1.45.0

## [16.12.3-bb.3]
### Changed
- Added support foro mTLS metrics config, and scheme

## [16.12.3-bb.2]
### Added
- Added capabilities: drop: all

## [16.12.3-bb.1]
### Changed
- Updated BB base image to 2.0.0

## [16.12.3-bb.0]
### UPGRADE NOTICE
- Updated to Redis 7.0.2 and 16.12.3 upstream chart

## [16.9.2-bb.0]
### UPGRADE NOTICE
- Updated to Redis 6.2.6 and 16.9.2 upstream chart

## [16.4.0-bb.0]
### UPGRADE NOTICE
- Updated to Redis 6.2.5 and 16.4.0 upstream chart

## [14.1.0-bb.7]
### Changed
- Fixed indentation in prometheusRule leading to errors in templating when being read by the kube-operator

## [14.1.0-bb.6]
### Changed
- Uncommented prometheusRule rule examples within chart. When enabled via BigBang, 3 prometheusRule templates will be created in cluster

## [14.1.0-bb.5]
### Changed
- Disabled clean upgrade job. Job was only needed when upgrading to Redis 6.2.2 and the 14.1.0 upstream chart. Keeping in for users upgrading from old version of BB

## [14.1.0-bb.4]
### Changed
- Removed `sidecar.istio.io/inject: 'false'` annotation from clean upgrade job and added `curl -X POST http://localhost:15020/quitquitquit` to cleanly terminate the istio sidecar container when the job completes. This was done to resolve OPA Gatekeeper violations

## [14.1.0-bb.3]
### Changed
- Updated clean upgrade job to include resource requests and limits in order to resolve OPA Gatekeeper violations

## [14.1.0-bb.2]
### Changed
- Changed cleanUpgrade image from gitlab/kubectl to bigbang/base.

## [14.1.0-bb.1]
### Added
- NetworkPolicy to ensure API access

## [14.1.0-bb.0]
### UPGRADE NOTICE
- A clean upgrade job will run which requires complete deletion of the previous redis instance, which means downtime can be expected
- Multiple values were changed and shifted around - most importantly `password` is now `auth.password`
- By default your old password (whatever is in the secret) will be used and will override any values specified
### Changed
- Updated to Redis 6.2.2 and 14.1.0 upstream chart
