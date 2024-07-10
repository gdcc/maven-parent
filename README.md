# maven-parent

A common Maven Parent for all GDCC and IQSS Java projects:

```xml
<parent>
    <groupId>io.gdcc</groupId>
    <artifactId>parent</artifactId>
    <version>x.y.z</version>
</parent>
```

## Important variables

| Maven Property | Description                                         |
|----------------|-----------------------------------------------------|
| `jdk.version`  | The minimum Java version a project can be used with |
| `skipUT`       | Skip executing unit tests with Surefire             |
| `skipIT`       | Skip executing integration tests with Failsafe      |

(There are more, docs to be done)

## Profiles

| Maven Profile | Description                                      |
|---------------|--------------------------------------------------|
| `release`     | Prepare a package for releasing to Maven Central |
| `coverage`    | Run JaCoCo, also contains some Sonar properties  |
