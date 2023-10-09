# ScalaCLI-Cheatsheet
This is a cheat-sheet of handy Scala-CLI commands. I have written a [blog post](https://yadukrishnan.live/scala-made-simple-for-beginners-a-gentle-introduction-to-kickstarting-your-scala-learning) about Scala-CLI and how it can make it easy for Scala beginners. 

For installation of the Scala-CLI, please take a look at the [official documentation](https://scala-cli.virtuslab.org/install). If you already use [Coursier](https://github.com/yadavan88/coursier-cheatsheets), you can use it to install Scala-CLI:
```
cs install scala-cli
```

Scala-CLI Commands
| Command | Description |
| -- | --|
| scala-cli Hello.scala | Compiles and runs Hello.scala file |
| scala-cli compile Hello.scala | Compiles Hello.scala file without running |
| scala-cli run Hello.scala | Runs Hello.scala file (same as scala-cli Hello.scala) |
| scala-cli setup-ide . | Prepares the config files needed to open in IDE. Now we can open in IntelliJ or VSCode+Metals |
| scala-cli -S 2.13.10 Hello.scala | Compiles and runs Hello.scala using the compiler version 2.13.10. Scala-CLI automatically downloads relevant version |
| scala-cli fmt Hello.scala | Formats Hello.scala using scalafmt | 
| scala-cli clean . | Deletes the `.scala-build` directory that contains compiled sources. This doesn't delete IDE config |
| scala-cli --power package Hello.scala -o app | Creates an executable application with name `app` for the file Hello.scala |
| scala-cli --jvm zulu:21.0.0 Hello.scala | Uses Zulu JDK 21 to execute Hello.scala. It downloads the JDK automatically |
| scala-cli --jvm 19 Hello.scala | Uses Open JDK 19 to execute Hello.scala |
