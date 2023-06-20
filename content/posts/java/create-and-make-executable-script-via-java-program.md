---
title: "Create and Make Executable Script via Java Program"
date: 2023-06-20T08:09:30+05:30
draft: false
tags:
  - Technical
  - Java
toc: true
author: Raghs
---

# Create and Make Executable Script via Java Program

Let us see how we can create a script and make it executable via a Java Program.

<!--more-->

## Creating a Script File

Creating a file and storing it in the FileSystem (writing) is a trivial task in any programming language and Java has no exception to this.

For the betterment, we will see the new/improved API classes introduced in *Java 11* (`JDK11`), than the typical/old school [`FileWriter`](https://docs.oracle.com/javase/8/docs/api/java/io/FileWriter.html), (or its wrapper [`BufferedWriter`](https://docs.oracle.com/javase/8/docs/api/java/io/BufferedWriter.html)) classes. 

The sample programs use the language constructs introduced in *Java 10, 11 and 13*. So any version of *JDK13* or higher is recommended to try out the programs listed in this article. Also, I use `zsh` as a preferred shell and hence the prompt displayed in the terminal is prefixed with the text `zsh`. 

> *Note*: It is recommended to always try out the latest, or close-to-the-latest version of the JDK.

```java
import java.nio.file.Files;
import java.nio.file.Path;
import java.io.IOException;

public class WriteAShellScript
{
    public static void main(String... args)
    throws IOException
    {
        //First, let us keep the content of the script file ready
        //We use var construct introduced in Java 10, 
        // and the text blocks which was introduced in Java 13.
        var script = """
        #!/bin/bash
        echo "hello, world - via Java Program"
        """;

        //Let's write the content into a file, and store it 
        // in the FileSystem by specifying the file name.
        // As no directory is mentioned, it would be stored in
        // the current directory where this Program is executed.
        var path = Files.writeString(Path.of("hello.sh"), script);

        // A confirmation message to the user
        System.out.println("File [hello.sh] has been written");
    }
}
```
If we compile and execute this program, we get the following output.

```sh
➜  io git:(master) ✗ exa -l
.rw-r--r--  908 raghavan.muthu 20 Jun 08:23 WriteAShellScript.class
.rw-r--r--  389 raghavan.muthu 19 Jun 23:58 WriteAShellScript.java
➜  io git:(master) ✗ java WriteAShellScript 
File [hello.sh] has been written
➜  io git:(master) ✗ exa -l
.rw-r--r--   53 raghavan.muthu 20 Jun 08:24 hello.sh
.rw-r--r--  908 raghavan.muthu 20 Jun 08:23 WriteAShellScript.class
.rw-r--r--  389 raghavan.muthu 19 Jun 23:58 WriteAShellScript.java
➜  io git:(master) ✗ ./hello.sh 
zsh: permission denied: ./hello.sh
➜  io git:(master) ✗ 
```

If you observe, the file `hello.sh` has been created successfully in the same directory, but watch the file attributes (access markers) which is `rw-r--r--` meaning the owner can only `read` and `write` and *NOT* `execute`.  It is the standard/default file permission `644` (_User-Read,Write, Group-Read, Others-Read_).

Hence, an attempt to execute the file has failed with the message stating that `permission denied: ./hello.sh`.

## Making it executable

We can make it executable in two different ways. First, the usual old-school way of setting permissions on the terminal/ command line via `chmod` command where we add the `+x` to the user as follows.

```sh
chmod u+x <fileName>
```
However, we want to manage this as well via Java Program via the API. Let us see how we can achieve the same by writing a different version of the program.

```java
import java.nio.file.Files;
import java.nio.file.Path;
import java.io.IOException;
import java.util.Set;
import java.nio.file.attribute.PosixFilePermission;

public class WriteAndMakeExecutableShellScript
{
    public static void main(String... args)
    throws IOException
    {
        var script = """
         #!/bin/bash
         echo "hello, world - via Java Program"
        """;

        var path = Files.writeString(Path.of("hello.sh"), script);
        System.out.println("File [hello.sh] has been written");
    
        /* Set the File permission with the meaningful methods.
        setPosixFilePermission method takes two arguments:
         1. The path to the target file
         2. A `java.util.Set` that takes the list of permissions,
            each denoted by a predefinex constant defined 
            in the `PosixFilePermission` class. 
            `OWNER_XXX` for Owners, 
            `GROUP_XXX` for the Group, 
            and `OTHERS_XXX` for Others, 
            where the XXX can be of any `READ`, `WRITE`, `EXECUTE`.
        */
        Files.setPosixFilePermissions(path, 
            Set.of(PosixFilePermission.OWNER_READ, PosixFilePermission.OWNER_EXECUTE));

        System.out.println("The file permissions are set to be executed by the User!");
    }
}
```

Now, let us run the revised program and verify the changes.

```sh
➜  io git:(master) ✗ javac WriteAndMakeExecutableShellScript.java 
➜  io git:(master) ✗ exa -l
.rw-r--r-- 1.4k raghavan.muthu 20 Jun 08:42 WriteAndMakeExecutableShellScript.class
.rw-r--r--  683 raghavan.muthu 20 Jun 08:42 WriteAndMakeExecutableShellScript.java
.rw-r--r--  389 raghavan.muthu 19 Jun 23:58 WriteAShellScript.java
.rw-r--r--  389 raghavan.muthu 19 Jun 23:58 WriteAShellScript.class
.rw-r--r--   53 raghavan.muthu 20 Jun 08:24 hello.sh
➜  io git:(master) ✗ java WriteAndMakeExecutableShellScript 
File [hello.sh] has been written
The file permissions are set to be executed by the User!
➜  io git:(master) ✗ exa -l
.r-x------   53 raghavan.muthu 20 Jun 08:43 hello.sh
.rw-r--r-- 1.4k raghavan.muthu 20 Jun 08:42 WriteAndMakeExecutableShellScript.class
.rw-r--r--  683 raghavan.muthu 20 Jun 08:42 WriteAndMakeExecutableShellScript.java
.rw-r--r--  389 raghavan.muthu 19 Jun 23:58 WriteAShellScript.java
```

> Note: If you observe the file permissions of the `hello.sh` carefully, the permission bits are actually overwritten by the Java Program. 

Earlier, the permission bits were set to `644`, but now we have explicitly overwritten with the `setPosixPermission()` method by passing in the *required* attributes to be applied - which was an instance of `java.util.Set` with `PosixFilePermission.OWNER_READ`, and `PosixFilePermission.OWNER_EXECUTE`. This is indeed the appropriate one as we are taking control over the file permission bits via the API.

```sh
➜  io git:(master) ✗ ./hello.sh 
hello, world - via Java Program
➜  io git:(master) ✗ 
```

No surprise, we can run / execute the program now without any hassles.

## Source Code

The Source codes for this article are available in the Github repository &rarr; [TechNotes - javaNotes - WriteMakeExecutableShellScript](https://github.com/itsraghz/TechNotes/tree/master/javaNotes/javaPrograms/basics/io/WriteMakeExecutableShellScript)

Cheers,\
RM...\
_Raghavan alias Saravanan Muthu_\
20 Jun 2023 | Tue | 08:09:30 AM IST
