# Building

## Building with Maven

This project is built with maven.

`mvn package`

## Building on GitHub

Each push to GitHub triggers a new GitHub Actions build using the openapi-maven-ci workflow.

## Releasing

To release, simply create a tag:

```
git tag -a v1.0.0 -m "release v1.0.0"
git push origin v1.0.0
```

This triggers a new GitHub Actions build (openapi-maven-release workflow) using the tag as version number and creates a draft release with the release artifact attached.
On the releases GitHub page, you can edit the release notes, set the pre-release checkbox if applicable, and publish the release.

The GitHub Action also publishes the artifacts to the Maven Central repository. If the release build fails for some reason, you can restart it by re-tagging:

```
git tag -d v1.0.0
git push --delete origin v1.0.0
git tag -a v1.0.0 -m "release v1.0.0" 
git push origin v1.0.0
```

On GitHub, complete the changelog and publish the drafted release.

## Versioning

Artifacts are released using semantic versioning.
You can increment the major or minor version by running:

`mvn versions:set -DnewVersion=2.0-SNAPSHOT -DgenerateBackupPoms=false`

The version number is only used for nightly builds however, release versions are based on their Git tag.
