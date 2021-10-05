---
title: "How to Resolve STS Maven XMLNS XSD Issue"
date: 2021-10-02T19:10:00+05:30
draft: false
tags:
  - Technical
  - Java
  - Troubleshooting
  - Tools
toc: true
author: Raghs
---

In this post, we will see how can we resolve the error shown in the `pom.xml` file inside the STS IDE (Spring Tool Suite), upon creating a new Maven Project. 

<!--more-->

## Issue 

I created a new Maven project inside the STS IDE, whose version details are given below for your reference. Upon creating a new project, there was an error in the `pom.xml` file that states that there was an error in the `maven-4.0.0.xsd`.  

Artifact | Details |
| ----- | --- |
| STS Version | `sts-4.12.0.RELEASE` |
| Platform | Windows 10 |
| Edition | 64 bit |
| Extractable JAR file Name | `spring-tool-suite-4-4.12.0.RELEASE-e4.21.0-win32.win32.x86_64.self-extracting.jar` - 540 MB |
| JDK Used | Oracle JDK 14 |
  
*pom.xml*

```xml
<project xmlns="http://maven.apache.org/POM/4.0.0"
	xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
	xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 
	https://maven.apache.org/xsd/maven-4.0.0.xsd">
	<modelVersion>4.0.0</modelVersion>
	<groupId>com.raghsonline</groupId>
	<artifactId>SpringFirstApp</artifactId>
	<version>0.0.1-SNAPSHOT</version>
</project>  
```

|Description	| Resource	| Path	| Location	 | Type |
| --- | ---- | --- | --- | --- |
|There is '1' error in 'maven-4.0.0.xsd'.	| pom.xml	| /SpringFirstApp | line 4	| Language Servers |

### Screenshot 

<img src="https://raghsonline.com/tools/sts/maven-xmlns-xsd-issue/01_error.JPG" alt="Maven XMLNL XSD Issue in STS IDE"/>

## Fix 

This seemed to be a bug in the STS when creating a new Maven Project. I tried a few other hacks, but this was the simple and best :) 

Basically the `xmlns` attribute has two values within a double quote, and both of them were not in sync - as one was referring to `http` and other was `https`. Keeping them in sync did the trick.

```xml
<project xmlns="http://maven.apache.org/POM/4.0.0"
	xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
	xsi:schemaLocation="https://maven.apache.org/POM/4.0.0 
	https://maven.apache.org/xsd/maven-4.0.0.xsd">
	<modelVersion>4.0.0</modelVersion>
	<groupId>com.raghsonline</groupId>
	<artifactId>SpringFirstApp</artifactId>
	<version>0.0.1-SNAPSHOT</version>
</project>  
```

> If you observed carefully, the change was on the line 4 where the `schemaLocation` attribute has now got the `https` for the `xsi:schemaLocation="http://maven.apache.org/POM/4.0.0` instead of the `http` as earlier, and thus in sync with the other value in teh same attribute `https://maven.apache.org/xsd/maven-4.0.0.xsd`

### Screenshot 

<img src="https://raghsonline.com/tools/sts/maven-xmlns-xsd-issue/02_fixed.JPG" alt="Maven XMLNS XSD Issue Fixed in STS IDE"/>

Cheers,\
RM...\
_Raghavan alias Saravanan Muthu_\
02 Oct 2021 | Sat | 19:10:00 PM IST
