# polylabel-java
A Java port of <b>PolyLabel</b> from MapBox.

This repository is a mirror of https://github.com/FreshLlamanade/polylabel-java

Official repo: [https://github.com/mapbox/polylabel](https://github.com/mapbox/polylabel)

Article: https://blog.mapbox.com/a-new-algorithm-for-finding-a-visual-center-of-a-polygon-7c77e6492fbc

## Requirements
* [Java 8 or later](http://www.oracle.com/technetwork/java/javase/downloads/index.html)
* [Maven 3](http://maven.apache.org/download.html)
* [Git](https://git-scm.com/downloads)

## Installation

### Gradle

Repositories:
```
repositories {
        ...
        maven { url 'https://jitpack.io' }
}
```

Dependencies:
```
dependencies {
        implementation 'com.github.aaronjyoder:polylabel-java-mirror:1.3.0'
}
```

### Maven

Add to your repositories:
```
  <repository>
      <id>jitpack.io</id>
      <url>https://jitpack.io</url>
  </repository>
```

Add to your dependencies:
```
  <dependency>
      <groupId>com.github.aaronjyoder</groupId>
      <artifactId>polylabel-java-mirror</artifactId>
      <version>1.3.0</version>
  </dependency>
```

## Usage

<i>Using default precision (1.0), no console messages:</i>
```java
PolyLabel result = PolyLabel.polyLabel(new Integer[][][] {{{0, 0}, {10, 0}, {0, 10}}})
// result.getCoordinates() -> {3.125, 3.125}
```
<i>Using precision of 0.5, no console messages:</i>
```java
PolyLabel result = PolyLabel.polyLabel(new Integer[][][] {{{0, 0}, {10, 0}, {0, 10}}}, 0.5)
// result.getCoordinates() -> {2.8125, 2.8125}
```
<i>Using precision of 0.5, with console messages:</i>
```java
PolyLabel result = PolyLabel.polyLabel(new Integer[][][] {{{0, 0}, {10, 0}, {0, 10}}}, 0.5, true)
//    Found best 2.50 after 5 probes
//
//    Found best 2.65 after 21 probes
//
//    Found best 2.81 after 25 probes
//
//    Num probes: 25
//    Best distance: 2.812500
//
// result.getCoordinates() -> {2.8125, 2.8125}
```
