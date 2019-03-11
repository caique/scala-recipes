# Scala Recipes: A "HelloWorld" in Scala

![](https://cdn-images-1.medium.com/max/1600/1*zE8AhLfLHuqA85F_9_u0SA.png)

Today I decided to stop putting it off and finally started to study
[Scala](https://www.scala-lang.org/) formally, from basic concepts to advanced
practices.

I had already worked with Scala in production but I always relied on the
existent code, my Java background, and my knowledge on functional programming.

I had a minor understanding of the philosophy behind Scala, its code style, best
practices, common tools, among other important aspects that any professional
developer must comprehend about a given programming language.

To make this learning even more fun, I'm going to register my progress and
learning pathway through code recipes while I expose some of the concepts and
practices that I might judge relevant.

Like always, let's start with a "*Hello World*" application in order to explain
the basics of Scala environment.

**Be aware!** To [keep it simple,
stupid](https://en.wikipedia.org/wiki/KISS_principle), I won't bother with any
explanation on how to set up your environment to avoid any OS-specific issue.
I'll assume that you have a working Scala environment.

For reference purposes, I'm using:

* Mac OSX
* IntelliJ IDEA
* Scala 2.12.4
* sbt 1.2.8

## Managing Scala and *sbt*

I’m a fan of tools for environments management because with them is extremely
simple to set up or tear down the support to any programming language.

For Scala I chose [scalaenv](https://github.com/scalaenv/scalaenv).

I just executed `brew install scalaenv sbt` to install *scalaenv* and *sbt* on
Mac OSX using [Homebrew](https://brew.sh/).

## What is sbt?

[As explained in sbt
documentation](https://www.scala-sbt.org/1.x/docs/Faq.html#What+does+the+name+âsbtâ+stand+for,+and+why+shouldnât+it+be+written+âSBTâ?),
the name isn't an initialism and simply doesn't mean anything specific. Since
it's creation was referred to as "sbt" and "sbt" only.

This is a build automation tool written in Scala and vastly used by the Scala
community.

Any file with the suffix `.sbt` is recognized but the `build.sbt` is commonly
used.

Since these files are simply pure Scala files, you can leverage Scala's
programming language features when writing your build tasks. This approach is
very similar to [Gradle](https://gradle.org/) (that uses Groovy).

## Our first build.sbt

In the command-line run `mkdir helloworld` to create the root folder for our
application.

Inside the `helloworld` folder, create a file called `build.sbt` with the
following content:

    := 
    := 
    := 

*sbt* offers an interactive shell that can be used to perform common tasks such
as *compile*, *run*, *test*, among others. To enter the interactive shell,
simply type: `sbt` in a terminal window.

![](https://cdn-images-1.medium.com/max/1600/1*YaTG3KDBjiTAMdAOTXrjMg.png)
<small>Image of a Terminal window where the command "sbt" was executed inside the
directory "helloworld". The execution of this command brought some informative
messages about the environment and started a new session of the interactive
*sbt* shell.</small>

## Our first Scala file

Create a new file called `HelloWorld.scala` with the following content:

```scala
object HelloWorld extends App {
  println("Hello World");
}
```

This simple piece of code already contains some interesting features of Scala
that worth our attention.

In Scala, while *Classes *(defined by the `class` keyword) are used to declare
blueprints to create new instances of objects, the `object` keyword creates a
s[ingleton object](https://docs.scala-lang.org/tour/singleton-objects.html)* —
*which is a class that has exactly one instance — and holds static members that
are not related to any instance of a given class.

**Be aware!** The term "object" can be used to describe *Singleton Objects*
and/or instances of a given class.

Our *singleton object* `HelloWorld` extends from `App` which is a `trait`.
*Traits* define interfaces for methods and attributes. *Traits* can't be
instantiated but can be extended by *Classes* and/or *Objects*.

The trait `App` is a special one that is compiled to the main method. Everything
inside an object that extends from this trait will be executed as the main
method.

## Running the code

Using the *sbt* shell, we can *compile* and *run* our first Scala file.

![](https://cdn-images-1.medium.com/max/1600/1*D47vfd9nFR5Qa0BzN5lf4A.png)
<small>Image of a Terminal window where the "sbt" command was executed to enter the sbt
shell. After the sbt shell initialization, the "compile" command was executed
and a success message was displayed together with other useful information.
Finally, the "run" command was executed and the output contains the "Hello
World" message from our Scala file.</small>

If you prefer, it's possible to run any command directly from the Terminal
without bypassing the sbt shell. In this case, we can just type: `sbt compile
run`.

![](https://cdn-images-1.medium.com/max/1600/1*uuQvin5l3iONWr1Se7B2CA.png)
<small>Image of a Terminal window where the command "sbt compile run" was executed
inside the "helloworld" folder. The output shows some useful information and
contains the "Hello World" message from our Scala file.</small>
