# esa-commons-build

[![Maven Central](https://maven-badges.herokuapp.com/maven-central/io.esastack/commons-build/badge.svg)](https://maven-badges.herokuapp.com/maven-central/io.esastack/commons-build/)
[![GitHub license](https://img.shields.io/github/license/esastack/esa-commons-build)](https://github.com/esastack/esa-commons-build/blob/main/LICENSE)

Common build tool

## Checkstyle

add maven plugin

```xml
<plugin>
    <artifactId>maven-checkstyle-plugin</artifactId>
    <version>3.1.1</version>
    <executions>
        <execution>
            <id>check-style</id>
            <configuration>
                <skip>false</skip>
                <configLocation>io/esastack/commons/checkstyle.xml</configLocation>
                <encoding>UTF-8</encoding>
                <consoleOutput>true</consoleOutput>
                <logViolationsToConsole>true</logViolationsToConsole>
                <failsOnError>true</failsOnError>
                <failOnViolation>true</failOnViolation>
                <propertyExpansion>main.basedir=${basedir}</propertyExpansion>
                <sourceDirectories>
                    <sourceDirectory>${project.build.sourceDirectory}</sourceDirectory>
                    <sourceDirectory>${project.build.testSourceDirectory}</sourceDirectory>
                </sourceDirectories>
            </configuration>
            <goals>
                <goal>check</goal>
            </goals>
            <phase>validate</phase>
        </execution>
    </executions>
    <dependencies>
        <dependency>
            <groupId>com.puppycrawl.tools</groupId>
            <artifactId>checkstyle</artifactId>
            <version>8.35</version>
        </dependency>
        <dependency>
            <groupId>io.esastack</groupId>
            <artifactId>commons-build</artifactId>
            <version>${esa.commons.build.version}</version>
        </dependency>
    </dependencies>
</plugin>
```