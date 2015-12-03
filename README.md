
#fork for reading


# Volley: Easy, Fast Networking for Android

Volley is a library that makes networking for Android apps easier and most importantly, faster.


## Google I/O 2013 Video

We'll give an overview of how it works, common patterns that work well with it, and a walkthrough of how you can easily load thumbnail images for your ListView from the network in parallel.

* [Announcement of Volley at Google I/O 2013][google-io-2013-volley]


## Project origin

This repository is a clone of the [original source code][google-repository]. Some modifications to the project setup have been made to allow Gradle usage.

## How to use?

In order to install the library into your **local Maven repository** run the following command:

```bash
$ ./gradlew clean install
```

This will build the library named `volley-1.0.0.aar` which can be found in the local Maven repository. The path for the Maven folder should be:

```bash
~/.m2/repository/com/android/volley/1.0.0/
```

The library can now be referenced in an Android application project in the `app/build.gradle` as follows:

```groovy
dependencies {
    compile 'com.android:volley:1.0.+'
}
```

Make sure to also reference the local Maven repository in your root `build.gradle` as shown here:

```groovy
buildscript {
    repositories {
        mavenCentral()
    }
    dependencies {
        classpath 'com.android.tools.build:gradle:0.9.+'
    }
}

allprojects {
    repositories {
        mavenCentral()
        mavenLocal() // When you forget this, the library will not be found
    }
}
```


## JavaDoc and sources

The build script includes tasks to generate JavaDoc and sources archives. The tasks are executed automatically when the library is installed into the local Maven repository. The archives can be found in the same folder as the library itself:

```bash
~/.m2/repository/com/android/volley/1.0.0/volley-1.0.0-javadoc.jar
~/.m2/repository/com/android/volley/1.0.0/volley-1.0.0-sources.jar
```


## More about

* [Comparison of Android Networking Libraries: OkHTTP, Retrofit, Volley][compare-networking-libs]
* [Volley Android Networking Library][volley-networking-lib]
* [Solving the Android image loading problem: Volley vs. Picasso][volley-networking-lib]



[google-io-2013-volley]: https://www.youtube.com/watch?v=yhv8l9F44qo
[google-repository]: https://android.googlesource.com/platform/frameworks/volley/
[compare-networking-libs]: http://stackoverflow.com/questions/16902716/comparison-of-android-networking-libraries-okhttp-retrofit-volley
[volley-networking-lib]: http://stackoverflow.com/questions/16659620/volley-android-networking-library
[volley-vs-picasso]: http://blog.bignerdranch.com/3177-solving-the-android-image-loading-problem-volley-vs-picasso/
