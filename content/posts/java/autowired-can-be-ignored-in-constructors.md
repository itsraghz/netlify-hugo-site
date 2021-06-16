---
title: "Autowired can be ignored in Constructors"
date: 2021-06-17T00:32:00+05:30
draft: false
tags: ["Technical", "Java", "Spring"]
toc: true
author: Raghs
---

In this blog post, we will see the `@Autowired` Annotation in the *Constructor Injection* in `Spring` Framework.

<!--more-->

## Spring's relaxation on the Autowired Annotation

Till Spring version 4.3, the `@Autowired` annotation was mandatory in the *Constructor* injection. However, Spring 4.3 version has relaxed that a bit.

If a class has a single constructor, the `@Autowired` annotation can be ignored and Spring framework will supply that for you behind the scenes. However, if the class has more than one constructor, any one of them must be annotated with the `@Autowired` annotation for the parameters you want to injected. Otherwise, you get an error for the obvious fact and doubt that which one should be annotated. 

## Code 1 - Class with a Single Constructor

```java
import com.example.springdatajpademo.repository.EmployeeRepository;
import org.springframework.boot.CommandLineRunner;
import org.springframework.stereotype.Component;

@Component
public class CheckDataRunner implements CommandLineRunner {

    private final EmployeeRepository employeeRepository;

    public CheckDataRunner(EmployeeRepository repository) {
        System.out.println("CheckDataRunner() - invoked, repository : " + repository);
        this.employeeRepository = repository;
    }

    @Override
    public void run(String... args) throws Exception {
        System.out.println("CheckDataRunner - executed");
        System.out.println(employeeRepository.findAll());
    }
```

> The class has a single constructor and hence it gets the relaxation of omitting the `@Autowired` annotation. 

## Code 2 - Class with more than one constructor

```java
import com.example.springdatajpademo.repository.EmployeeRepository;
import org.springframework.boot.CommandLineRunner;
import org.springframework.stereotype.Component;

@Component
public class CheckDataRunner implements CommandLineRunner {

    private final EmployeeRepository employeeRepository;

    public CheckDataRunner() {
        System.out.println("Default constructor invoked!");
    }

    public CheckDataRunner(EmployeeRepository repository) {
        System.out.println("CheckDataRunner() - invoked, repository : " + repository);
        this.employeeRepository = repository;
    }

    @Override
    public void run(String... args) throws Exception {
        System.out.println("CheckDataRunner - executed");
        System.out.println(employeeRepository.findAll());
    }
```

> The class has more than one version of constructor and the parameterized constructor does NOT have the `@Autowired` annotation which causes a compiler error on the field - `employeeRepository`. The IDE will complain that the `variable might not have been initialized`. 

## Solution for the Code 2 - class with more than one constructors

You can solve this issue by doing the following:

* Make the field `employeeRepository` non-final.
* Add the `@Autowired` annotation for the parameterized constructor

```java
// Imports are ignored for brevity.

@Component
public class CheckDataRunner implements CommandLineRunner, Ordered {

    private EmployeeRepository employeeRepository;

    private CheckDataRunner() {
    }

    @Autowired
    public CheckDataRunner(EmployeeRepository repository) {
        System.out.println("CheckDataRunner() - invoked, repository : " + repository);
        this.employeeRepository = repository;
    }

    @Override
    public void run(String... args) throws Exception {
        System.out.println("CheckDataRunner - executed");
        System.out.println(employeeRepository.findAll());
    }
}    
```

> Note: If you forgot to annotate the parameterized constructor with the `@Autowired` annotation, you get a `NullPointerException` due to the fact that field `employeeRepository` not being initalized and the reference invoked on the 2nd line of the `run()` method will be null. 


## References

* https://spring.io/blog/2016/03/04/core-container-refinements-in-spring-framework-4-3
* https://docs.spring.io/spring-framework/docs/4.3.x/spring-framework-reference/htmlsingle/#beans-autowired-annotation
* https://stackoverflow.com/a/62846048/1001242
* https://stackoverflow.com/questions/41092751/spring-injects-dependencies-in-constructor-without-autowired-annotation/41092831  

Cheers,\
RM...\
_Raghavan alias Saravanan Muthu_\
17 Jun 2021 | Thu | 00 32 00 AM IST
