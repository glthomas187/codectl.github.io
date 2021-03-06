---
layout: default
title: Bundle
parent: User Guide
nav_order: 2
---

# Low Side Artifact Bundle
### Koffer Collector Plugins
  - [Infrastructure]    
  - [Operators]    
  - [Applications]    
    
  1. Create Platform Artifacts Staging Directory
```
 mkdir -p /tmp/bundle ;
```
  2. Build Openshift Infrastructure, Operators, & App Bundles
```
sudo podman run -it --rm \
    --privileged --device /dev/fuse \
    --volume /tmp/bundle:/root/deploy/bundle:z \
  docker.io/codesparta/koffer bundle \
    --repo collector-infra \
    --repo collector-operators \
    --repo collector-apps
```
    
  3. Paste [Quay.io Image Pull Secret] when prompted
  3. Review your artifacts
```
 du -sh /tmp/bundle/*
```
    
## Continue [Artifacts AirGap Pivot](https://codectl.io/docs/user-guide/airgap)    
[Operators]:https://github.com/CodeSparta/collector-operators
[Applications]:https://github.com/CodeSparta/collector-apps
[Infrastructure]:https://github.com/CodeSparta/collector-infra
[Quay.io Image Pull Secret]:https://cloud.redhat.com/openshift/install/metal/user-provisioned
