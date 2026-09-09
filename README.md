Dynmap-WorldGuard
=================

Dynmap-WorldGuard adds WorldGuard region overlay support to dynmap.

This branch targets Paper v26.x and uses Gradle instead of the Maven build
used by the master branch.

Compatibility
-------------

| Component | Version |
| --- | --- |
| Java bytecode target | 25 |
| Gradle wrapper | 9.7.1 |
| Paper API | 26.2.build.+ |
| dynmap API | 3.8 |
| WorldEdit Bukkit | 7.4.5 |
| WorldGuard Bukkit | 7.0.0 |

The build must be run with a JDK that can target Java 25. A newer JDK, such as
JDK 26, can also run the build.

Building
--------

Use the included Gradle wrapper:

```sh
./gradlew build
```

The plugin jar is produced by the Shadow plugin under `build/libs/`.

Useful build tasks:

```sh
./gradlew compileJava
./gradlew shadowJar
./gradlew packageZip
./gradlew printJavaCompatibility
```

Changes from master
-------------------

- Replaced the Maven build files with Gradle wrapper files, `settings.gradle`,
  `build.gradle`, and a Gradle version catalog.
- Switched from the Bukkit API dependency to Paper API
  `io.papermc.paper:paper-api:26.2.build.+`.
- Added Paper's `paper-plugin.yml` metadata with required `dynmap` and
  `WorldGuard` server dependencies.
- Raised the compile target from Java 8 to Java 25.
- Updated dynmap API from `3.3-SNAPSHOT` to `3.8`.
- Kept WorldEdit Bukkit `7.4.5`, WorldGuard Bukkit `7.0.0`, and SquirrelID
  `0.2.0`.
- Removed bStats usage and the bStats shaded dependency from the plugin.

Runtime Dependencies
--------------------

Install this plugin on a Paper v26.x server with dynmap and WorldGuard present.
The Paper plugin metadata declares both as required server dependencies.
