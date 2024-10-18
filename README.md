# maven-parent

A common Maven Parent for all GDCC and IQSS Java projects:

```xml
<parent>
    <groupId>io.gdcc</groupId>
    <artifactId>parent</artifactId>
    <version>x.y.z</version>
</parent>
```

Aside from dependencies and plugin management, the Parent POM provides sane defaults for `<groupId>` and the extended project information bits `<url>`, `<organization>`, `<issueManagement>`, `<scm>`, `<ciManagement>` and `<distributionManagement>`.
You can always completely override them in a child project.

## Important variables

| Maven Property        | Description                                               |
|-----------------------|-----------------------------------------------------------|
| `jdk.version`         | The minimum Java version a project can be used with       |
| `skipUT`              | Skip executing unit tests with Surefire                   |
| `skipIT`              | Skip executing integration tests with Failsafe            |
| `project.github.org`  | Default `gdcc`, influencing project info                  |
| `project.github.repo` | Default `${project.artifactId}`, influencing project info |

(There are more, docs to be done)

## Profiles

| Maven Profile | Description                                      |
|---------------|--------------------------------------------------|
| `release`     | Prepare a package for releasing to Maven Central |
| `coverage`    | Run JaCoCo, also contains some Sonar properties  |
