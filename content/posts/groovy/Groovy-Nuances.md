---
title: "Groovy Nuances"
date: 2021-06-01T23:41:23+05:30
draft: false
tags: ["Technical", "Groovy"]
toc: false
author: Raghs
---

# Groovy Nuances - Map in Groovy

Map is a data structure that takes a set of key,value pairs. Remember, Map is 
NOT a Collection. It is not a member of `Java Collection` family. It is a 
data structure of its own. 

Groovy Map offers a few flexible ways to manipulate the contents.
Totally there are 6 ways to add an element (Key,Value pair) to Map, as follows.

<!--more-->

Let us define a Map (empty map) as follows.

```
def myMap = [:]
```

To add an element (key,value pair) we can do any of the following.

```
myMap[Name] = 'Raghavan'
```

> The above Array like Syntax allows you to access a key within the square brackets
> and lets you specify the value after the equals sign.

....

We can use the `get(key)` method to get a value of a particular key.

```
println myMap.get(Age) //prints null
```

The Map does not have a key called `Age` and hence it prints null, which is no different
from the Traditional Java way.

## Nuance

The nuance comes in the 6th step, where we use the `get(key)` method with a default value.

```
println myMap.get('Department', 'Projects')
```

The above statement attempts to print the value associated with the key `Department` in the Map `myMap` if exists, else it automatically adds a key, value (Deparment=Projects) into the Map.

```
println myMap
println myMap.get('Department')` //subsequent attempt will not throw any nulls, as it was recently inserted
```


Cheers,\
RM...\
_Raghavan alias Saravanan Muthu_\
16 Jan 2021 | Tue | 07 46 PM IST 
