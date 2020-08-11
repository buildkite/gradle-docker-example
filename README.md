# Gradle Buildkite docker-compose example

This example uses [Gradle](https://gradle.org/) to build a Java project.

Project example was taken from [Gradle/db-example-large-multi-project](https://github.com/gradle/db-example-large-multi-project).

This example also works on the Buildkite Agent using [the Docker Compose plugin](https://github.com/buildkite-plugins/docker-compose-buildkite-plugin) to run Gradle in [the Gradle Docker container](https://hub.docker.com/_/gradle), which works great on the [Elastic CI Stack for AWS](https://github.com/buildkite/elastic-ci-stack-for-aws).

![Gradle build](https://user-images.githubusercontent.com/585588/89701317-be475100-d974-11ea-87e2-149ac676817c.png)
![Gradle artifacts](https://user-images.githubusercontent.com/585588/89701316-bab3ca00-d974-11ea-9522-9be86a06b35e.png)

[![Add to Buildkite](https://buildkite.com/button.svg)](https://buildkite.com/new)

## License

See [LICENSE.md](LICENSE.md) (MIT)
