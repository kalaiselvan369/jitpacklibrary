# jitpacklibrary for android
Using your library project from github as gradle dependency.

## Create a new android studio project

From a newly created project add a new module and name it related to your usage. This module will be your library project.

## Adding plugin 

In your project level build.gradle add  
``` classpath 'com.github.dcendents:android-maven-gradle-plugin:1.3'```

In your library project or module's build.gradle add  
``` apply plugin: 'com.github.dcendents.android-maven'```

## Specify group

``` group = 'com.github.youNameInGithub'```

Once all done run this command in terminal

``` gradlew install ```

## Create a repository in github

This repository name will be used in below mentioned dependency.

## Push your above created project to github
1. Go to your android project folder in terminal
2. git init
3. git add .
4. git commit -m "your commit name "
5. git remote add origin yougithubrepositorylink
6. git push origin master
7. Go to your created repository in github and create release tag with version.

## How to user your library project from github as gradle dependency

Add this to any of your android application project level build.gradle

```java
allprojects {
 repositories {
    jcenter()
    maven { url "https://jitpack.io" }
 }
}
```

Now in your app level build.gradle add dependency as

``` compile ('com.github.yourNameInGithub:yourRepositoryName:releaseTagVersion') ```

For more info look at this link
[https://jitpack.io/docs/ANDROID/]


