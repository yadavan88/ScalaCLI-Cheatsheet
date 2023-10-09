# ScalaCLI-Cheatsheet
This is a cheat-sheet of handy Scala-CLI commands. I have written a [blog post](https://yadukrishnan.live/scala-made-simple-for-beginners-a-gentle-introduction-to-kickstarting-your-scala-learning) about Scala-CLI and how it can make it easy for Scala beginners. 

For installation of the Scala-CLI, please take a look at the [official documentation](https://scala-cli.virtuslab.org/install). If you already use [Coursier](https://github.com/yadavan88/coursier-cheatsheets), you can use it to install Scala-CLI:
```
cs install scala-cli
```

## Scala-CLI Commands
| Command | Description |
| -- | --|
| scala-cli Hello.scala | Compiles and runs Hello.scala file |
| scala-cli compile Hello.scala | Compiles Hello.scala file without running |
| scala-cli run Hello.scala | Runs Hello.scala file (same as scala-cli Hello.scala) |
| scala-cli setup-ide . | Prepares the config files needed to open in IDE. Now we can open in IntelliJ or VSCode+Metals |
| scala-cli -S 2.13.10 Hello.scala | Compiles and runs Hello.scala using the compiler version 2.13.10. Scala-CLI automatically downloads relevant version |
| scala-cli fmt Hello.scala | Formats Hello.scala using scalafmt | 
| scala-cli clean . | Delete the `.scala-build` and clean contents of `.bsp` directories that contains compiled sources. Notice that, this deletes IDE config, so you need to do setup-ide again |
| scala-cli --power package Hello.scala -o app | Creates an executable application with name `app` for the file Hello.scala |
| scala-cli --jvm zulu:21.0.0 Hello.scala | Uses Zulu JDK 21 to execute Hello.scala. It downloads the JDK automatically |
| scala-cli --jvm 19 Hello.scala | Uses Open JDK 19 to execute Hello.scala |

## Scala-CLI Directives
Directives are special statements in Scala-CLI. They are added as comments with a special syntax as part of the Scala code. 
Directives starts with the syntax `//>`. Scala-CLI differentiates them from normal comments and process them in a special way. 
Here are some of the useful directives:

| Directive | Description |
| -- | --|
| //> using scala 3 | This informs Scala-CLI that the following code is written in Scala 3.x version (not 2.x). Hence it uses Scala 3 for the code compilation even though local version of Scala is something else|
| //> using scala "2.13.12" | Uses the specific version of Scala for the compilation |
| //> using jvm "19" | Scala-CLI uses JVM 19 (adopt open jdk by default) for compilation and execution |
| //> using jvm "zulu:21.0.0" | Uses the specific version of the JDK |
| //> using dep com.lihaoyi::os-lib:0.9.1 | Downloads and brings the os-lib library to the scope so that we can use it
