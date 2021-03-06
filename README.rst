Ant Based Java Desktop App Project Template for packaging a Java App for distribution on a Mac
==============================================================================================

.. image:: https://travis-ci.org/vorachet/AntBasedJavaDesktopAppProjectTemplate4MAC.svg?branch=master
    :target: https://travis-ci.org/vorachet/AntBasedJavaDesktopAppProjectTemplate4MAC

Creating cross-platform executable JAR and DMG file for OS X software installer within an ANT build script saved me a lot of time. This project was inspired by the ANT script developed by https://github.com/kolovos/markingmate. I customized a few configurations for my perfect Java desktop app project template. 

Java Desktop App Project Template is an ANT based java desktop project template that comes with a complete set of ANT tasks and pre-configured local JAR files for packaging a Java App for distribution on a Mac. The template has a number of features below:

- ANT script based Java project template with pre-configured local JAR files. The build script contains a default task that can be used to build cross-platform executable JAR and DMG file for OS X software installer
- Eclipse project and classpath description file are provided for Eclipse coding environment.
- Travis CI build file is provided  
- JUNIT 4 and SLF4J 1.7 integrated in build and coding environment.
- Ant task for running JUnit
- Project was tested on TravisCI

Enjoy your desktop app development

Building and running the Java desktop app example
=================================================

Ant (http://ant.apache.org/) is required 

..  code-block::

    $ git clone https://github.com/vorachet/AntBasedJavaDesktopAppProjectTemplate4MAC.git
    $ cd AntBasedJavaDesktopAppProjectTemplate4MAC
    $ ant

        Buildfile: AntBasedJavaDesktopAppProjectTemplate4MAC/build.xml

        clean:
           [delete] Deleting directory AntBasedJavaDesktopAppProjectTemplate4MAC/bin
           [delete] Deleting directory AntBasedJavaDesktopAppProjectTemplate4MAC/dist
            [mkdir] Created dir: AntBasedJavaDesktopAppProjectTemplate4MAC/bin

        compile:
            [javac] Compiling 3 source files to AntBasedJavaDesktopAppProjectTemplate4MAC/bin

        test:
            [junit] Running com.example.test.TestMyApp
            [junit] Tests run: 1, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 1.514 sec

        package:
              [jar] Building jar: AntBasedJavaDesktopAppProjectTemplate4MAC/dist/MyApp.jar
              [zip] Building zip: AntBasedJavaDesktopAppProjectTemplate4MAC/dist/MyApp4Win.zip
        [bundleapp] Creating app bundle: MyApp
          [copydir] DEPRECATED - The copydir task is deprecated.  Use copy instead.
          [copydir] Copying 1 file to AntBasedJavaDesktopAppProjectTemplate4MAC/dist/MyApp.app/Contents/Home/resources
             [exec] created: AntBasedJavaDesktopAppProjectTemplate4MAC/dist/MyApp4Mac.dmg

        default:

        BUILD SUCCESSFUL
        Total time: 14 seconds

Folder structure
=================

..  code-block::

    ├── LICENSE
    ├── README.rst
    ├── build.xml
    ├── lib
    │   ├── MacWidgets.jar
    │   ├── appbundler-1.0.jar
    │   ├── hamcrest-core-1.3.jar
    │   ├── junit-4.12.jar
    │   ├── libquaqua.jnilib
    │   ├── libquaqua64.dylib
    │   ├── libquaqua64.jnilib
    │   ├── quaqua.jar
    │   ├── slf4j-api-1.7.25.jar
    │   └── slf4j-jdk14-1.7.25.jar
    ├── resources
    │   └── app.icns
    └── src
        ├── main
        │   └── java
        │       └── com
        │           └── example
        │               ├── MyApp.java
        └── test
            └── java
                └── com
                    └── example
                        └── test
                            └── TestMyApp.java


Bin and Dist folder after successfully running the Ant script
=================================================================

..  code-block::

    ├── bin
    │   ├── TEST-com.example.test.TestMyApp.txt
    │   ├── TEST-com.example.test.TestMyApp.xml
    │   └── com
    │       └── example
    │           ├── MyApp$1.class
    │           ├── MyApp.class
    │           ├── test
    │           │   └── TestMyApp.class
    ├── dist
    │   ├── MyApp.app
    │   │   └── Contents
    │   │       ├── Home
    │   │       │   └── resources
    │   │       │       └── app.icns
    │   │       ├── Info.plist
    │   │       ├── Java
    │   │       │   ├── MacWidgets.jar
    │   │       │   ├── MyApp.jar
    │   │       │   └── quaqua.jar
    │   │       ├── MacOS
    │   │       │   ├── JavaAppLauncher
    │   │       │   ├── libquaqua.jnilib
    │   │       │   ├── libquaqua64.dylib
    │   │       │   └── libquaqua64.jnilib
    │   │       ├── PkgInfo
    │   │       ├── PlugIns
    │   │       └── Resources
    │   │           ├── app.icns
    │   │           └── en.lproj
    │   │               └── Localizable.strings
    │   ├── MyApp.jar
    │   ├── MyApp4Mac.dmg
    │   └── MyApp4Win.zip

