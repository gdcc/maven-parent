# maven-parent

🚨 **BREAKING CHANGE** 🚨

☝️ *THIS PARENT POM HAS BEEN UPGRADED TO ENABLE CENTRAL PORTAL PUBLISHING* ☝️  
See also https://central.sonatype.org/news/20250326_ossrh_sunset/ for more information.
Make sure to adapt your CI workflows: new server id `central` and it will require new tokens in CI secrets!

----

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

| Maven Property          | Description                                                         |
|-------------------------|---------------------------------------------------------------------|
| `jdk.version`           | The minimum Java version a project can be used with                 |
| `skipUT`                | Skip executing unit tests with Surefire                             |
| `skipIT`                | Skip executing integration tests with Failsafe                      |
| `skipFlatten`           | Skip executing the Maven Flatten plugin                             |
| `enable.snapshot.repos` | Set to true to enable usage of Maven Central Snapshot repositories  |
| `project.github.org`    | Default `gdcc`, influencing project info                            |
| `project.github.repo`   | Default `${project.artifactId}`, influencing project info           |

(There are more, docs to be done)

## Profiles

| Maven Profile | Description                                      |
|---------------|--------------------------------------------------|
| `release`     | Prepare a package for releasing to Maven Central |
| `coverage`    | Run JaCoCo, also contains some Sonar properties  |
