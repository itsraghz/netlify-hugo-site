---
title: "Springboot ApplicationRunner vs CommandLineRunner"
date: 2021-06-17T01:29:30+05:30
draft: true
tags:
  - TODO
  - Java
  - Technical
  - Spring
toc: true
author: Raghs
---

Springboot offers two different `Runner`s to get a way to run any piece of code right after the application launch, and before servicing any client requests. It is a potential opportunity to run any of the critical prequisites like intializing certain state of the application, load the cache etc., 

<!--more-->

## General Strategy

Both of them are `interface`s in Java with a *SAM* (Single Abstract Method) - `run()`, and we need to implement a class of our choice of the Interface and override the `run()` method with the logic we want to get executed before serving any clients.

## CommandLineRunner Interface

* Defined in the package `org.springframework.boot`
* A *Functional Interface* with a *SAM* - `run()` method
* Parameter - `String[]` - array of Strings
* Since `Spring Boot V 1.0.0`

## ApplicationRunner Interface

* Defined in the package `org.springframework.boot`
* A *Functional Interface* with a *SAM* - `run()` method
* Parameter - An instance of `ApplicationArguments`
* Since `Spring Boot V 1.3.0`
  
## Comparison

## Special case - Multiple Runner implementations with `@Order`

## Code Sample

## References 

* https://docs.spring.io/spring-boot/docs/current/api/org/springframework/boot/CommandLineRunner.html
* https://docs.spring.io/spring-boot/docs/current/api/org/springframework/boot/ApplicationRunner.html
* https://docs.spring.io/spring-boot/docs/current/api/org/springframework/boot/ApplicationArguments.html
* https://docs.oracle.com/javase/8/docs/api/java/lang/FunctionalInterface.html


Cheers,\
RM...\
_Raghavan alias Saravanan Muthu_\
17 Jun 2021 | Thu | 01 29 30 AM IST
