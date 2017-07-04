# Docker-in-Docker on CircleCI example

This uses the CircleCI 2.0 YAML format with a remote docker engine to do the
following:

1. Build a Docker-in-Docker image, also containing a folder with tests
2. Run that image
3. Using `exec` commands, build a test image inside the running dind image
4. Using `exec` commands, run the test container inside the running dind image

The runtime diagram would look something like:

```
CircleCI
|
CircleCI Remote Docker Engine
|
`-> dind Image defined in this repo (Dockerfile)
    |
    `-> Test image defined in this repo (test/Dockerfile)
```

