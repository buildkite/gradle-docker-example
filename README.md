# Gradle Buildkite docker-compose example
[![Build status](https://badge.buildkite.com/a0977fb3a7441cbabcab56a5e92d045a5110198f1ec6007668.svg)](https://buildkite.com/buildkite/gradle-docker-example)

This repository demonstrates how to run a Java project using [Gradle](https://gradle.org/) on [Buildkite](https://buildkite.com), using the [Docker Compose Buildkite Plugin](https://github.com/buildkite-plugins/docker-compose-buildkite-plugin).

👉 **See this example in action:** [buildkite.com/buildkite/gradle-docker-example](https://buildkite.com/buildkite/gradle-docker-example)

See the full [Getting Started Guide](https://buildkite.com/docs/guides/getting-started) for step-by-step instructions on how to get this running, or try it yourself:

[![Add to Buildkite](https://buildkite.com/button.svg)](https://buildkite.com/new)

<a href="https://buildkite.com/buildkite/gradle-docker-example/builds/latest?branch=main">
  <img width="2400" alt="Screenshot of example pipeline build page" src=".buildkite/screenshot.png" />
</a>

## How it works

This example:
- Uses Gradle to build and test a multi-project Java application.
- Uploads generated artifacts to Buildkite.
- Runs inside the official [Gradle Docker image](https://hub.docker.com/_/gradle) via Docker Compose.
- Configures the [Gradle Enterprise plugin](https://docs.gradle.com/enterprise/gradle-plugin/) to enable build scans.
- Works with Gradle 7.6+ and uses the `com.gradle.enterprise` plugin (replacing the legacy `build-scan` plugin).
- Is designed to work well with the [Elastic CI Stack for AWS](https://github.com/buildkite/elastic-ci-stack-for-aws).

The Java project is based on [Gradle's db-example-large-multi-project](https://github.com/gradle/db-example-large-multi-project).

### Running it locally

To try the build locally with Docker Compose:

```bash
docker compose -f .buildkite/docker-compose.yml up
```

---

## Requirements

- A [Buildkite agent](https://buildkite.com/docs/agent)
- Docker and Docker Compose installed on the agent machine
  - ✅ No need to manually install Gradle or Java — the Docker container handles that

---

## To try it yourself

1. [Create a new pipeline on Buildkite](https://buildkite.com/new)
2. Select "Import repository", and link this example repo (or your fork of it)
3. Add a Buildkite agent with Docker and Docker Compose installed
4. Run a build - the pipeline will automatically use Docker Compose and Gradle inside the container!

## Build scans (optional)

You can enable [Gradle Build Scans](https://scans.gradle.com/) by setting the `GE_URL` environment variable.

```bash
export GE_URL=https://scans.gradle.com
```

---

## License

See [LICENSE.md](LICENSE.md) (MIT)
