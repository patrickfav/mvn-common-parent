# Maven Common Configuration
A maven configuration which is used as commons config parent for POM files for my maven open source projects. Defines a lot of defaults in `pluginManagement` and some in `dependencyManagement` and activates some plugins.

[![Download](https://api.bintray.com/packages/patrickfav/maven/mvn-common-parent/images/download.svg)](https://bintray.com/patrickfav/maven/mvn-common-parent/_latestVersion)
[![Build Status](https://travis-ci.org/patrickfav/mvn-common-parent.svg?branch=master)](https://travis-ci.org/patrickfav/mvn-common-parent)

## Usage

Use as parent pom:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
    <modelVersion>4.0.0</modelVersion>
    <parent>
        <groupId>at.favre.lib</groupId>
        <artifactId>common-parent</artifactId>
        <version>{current-version}</version>
    </parent>
    ...
```

Don't forget to overwrite `<scm>...</scm>` config, otherwise it will be inherited from this project.

## Analyze

Check the created `pom` with

```bash
mvnw help:effective-pom
```

You may check for updates of any plugins or dependencies with

```bash
mvn versions:display-dependency-updates
```

## Project Setup

It is recommended to use [maven wrapper](https://github.com/takari/maven-wrapper) in a new project. Initialize with:

```bash
mvn -N io.takari:maven:0.7.5:wrapper
```

then you can use `mvnw` instead of `mvn`. The advantage is that everybody (+ci) uses a pre-defined maven version. Even [IntelliJ has Maven wrapper support](https://plugins.jetbrains.com/plugin/10633-maven-wrapper-support).

## Features

Here is a high level feature set of this project:

* Java 1.7 target
* [Checkstyle](http://checkstyle.sourceforge.net/)
* [Google Errorprone](https://github.com/google/error-prone) (Java 7)
* [Maven enforcer](https://maven.apache.org/enforcer/maven-enforcer-plugin/) (for Maven version)
* [Versions plugin](https://www.mojohaus.org/versions-maven-plugin/)
* [OWASP dependency checker](https://jeremylong.github.io/DependencyCheck/dependency-check-maven/)
* [Jacoco](https://www.eclemma.org/jacoco/) + [Coveralls](https://coveralls.io/)
* [Jarsigner](https://maven.apache.org/plugins/maven-jarsigner-plugin/)
* [Checksum](https://checksum-maven-plugin.nicoulaj.net/)

### Versions Plugin

Check for possible dependency updates

```bash
mvnw versions:display-dependency-updates
```

Set version through command line (or ci script)

```bash
mvnw versions:set -DnewVersion=1.2.3-SNAPSHOT
```

# License

Copyright 2019 Patrick Favre-Bulle

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
