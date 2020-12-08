# Building

## Building with Maven

This project is built with maven.

`mvn package`

## Releasing

To release, simply create a tag:

```
git tag -a v1.0.0-alpha1 -m "release v1.0.0-alpha1"
git push origin v1.0.0-alpha1
```

This triggers a new GitHub Actions build using the tag as version number and creates a draft release with the release artifact attached.
On the releases GitHub page, you can edit the release notes, set the pre-release checkbox if applicable, and publish the release.

## Versioning

Artifacts are released using semantic versioning.
You can increment the major or minor version by running:

`mvn versions:set -DnewVersion=2.0-SNAPSHOT -DgenerateBackupPoms=false`

The version number is only used for nightly builds however, release versions are based on their Git tag.
