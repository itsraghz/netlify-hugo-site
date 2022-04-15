---
title: "Grep With Whole Words"
date: 2022-04-15T08:57:12+05:30
draft: false
tags:
  - Technical
  - Linux
toc: true
author: Raghs
---

# Grep With Whole Words

We will see how to extract the whole words in Linux using the famous `grep` command in this post, which needs a tweak in the way we execute it by passing a few additional arguments. 

<!--more-->

## Typical `grep` - resulting all matching words 

By default, the `grep` command picks up all the matching entries in the file or the input stream that it is being operated upon. 

I have a list of ebooks issued from Packtpub, on a daily basis - named *EbookPerDay*, and I wanted to pick up the list of books matching with *Go* Language. When I issued a simple `grep`, I get all the other unwanted entries matching with *Algorithm*, *Google*, *Django* etc., where the term *go* is a part of those words, which I dont' want it right now as it dilutes my objective. 

```sh
SPRING_REST : ls -ltrh | grep GO
-rwxrwxrwx 1 raghs raghs  6.1M Nov 15  2020 9781789537178-BEGINNING_JAVA_DATA_STRUCTURES_AND_ALGORITHMS.pdf
-rwxrwxrwx 1 raghs raghs  4.3M Nov 15  2020 9781789537178-BEGINNING_JAVA_DATA_STRUCTURES_AND_ALGORITHMS.epub
-rwxrwxrwx 1 raghs raghs  211K Nov 15  2020 9781789537178-BEGINNING_JAVA_DATA_STRUCTURES_AND_ALGORITHMS_Code.zip
-rwxrwxrwx 1 raghs raghs   16M Dec 26  2020 9781838647940-THE_GO_WORKSHOP.pdf
-rwxrwxrwx 1 raghs raghs  5.4M Dec 26  2020 9781838647940-THE_GO_WORKSHOP_Code.zip
-rwxrwxrwx 1 raghs raghs   20M Dec 26  2020 9781838647940-THE_GO_WORKSHOP.epub
-rwxrwxrwx 1 raghs raghs   11M Mar  6  2021 9781788995573-HANDSON_DATA_STRUCTURES_AND_ALGORITHMS_WITH_PYTHON_SECOND_EDITION.pdf
-rwxrwxrwx 1 raghs raghs  268K Mar  6  2021 9781788995573-HANDSON_DATA_STRUCTURES_AND_ALGORITHMS_WITH_PYTHON_SECOND_EDITION_Code.zip
-rwxrwxrwx 1 raghs raghs  9.1M Mar  6  2021 9781788995573-HANDSON_DATA_STRUCTURES_AND_ALGORITHMS_WITH_PYTHON_SECOND_EDITION.epub
-rwxrwxrwx 1 raghs raghs   11M Apr 10  2021 9781788833738-CHash_DATA_STRUCTURES_AND_ALGORITHMS.pdf
-rwxrwxrwx 1 raghs raghs  8.9M Apr 10  2021 9781788833738-CHash_DATA_STRUCTURES_AND_ALGORITHMS.epub
-rwxrwxrwx 1 raghs raghs  1.2M Apr 10  2021 9781788833738-CHash_DATA_STRUCTURES_AND_ALGORITHMS_Code.zip
-rwxrwxrwx 1 raghs raghs  4.2M Jun 24  2021 9781789804072-HANDSON_SYSTEM_PROGRAMMING_WITH_GO.pdf
-rwxrwxrwx 1 raghs raghs  2.4M Jun 24  2021 9781789804072-HANDSON_SYSTEM_PROGRAMMING_WITH_GO.epub
-rwxrwxrwx 1 raghs raghs  308K Jun 24  2021 9781789804072-HANDSON_SYSTEM_PROGRAMMING_WITH_GO_Code.zip
-rwxrwxrwx 1 raghs raghs  5.7M Jun 25  2021 9781789618501-LEARN_DATA_STRUCTURES_AND_ALGORITHMS_WITH_GOLANG.pdf
-rwxrwxrwx 1 raghs raghs  4.5M Jun 25  2021 9781789618501-LEARN_DATA_STRUCTURES_AND_ALGORITHMS_WITH_GOLANG.epub
-rwxrwxrwx 1 raghs raghs  828K Jun 25  2021 9781789618501-LEARN_DATA_STRUCTURES_AND_ALGORITHMS_WITH_GOLANG_Code.zip
-rwxrwxrwx 1 raghs raghs  3.2M Jul 26  2021 9781785882517-LEARNING_GOOGLE_APPS_SCRIPT.pdf
-rwxrwxrwx 1 raghs raghs  8.3M Jul 26  2021 9781785882517-LEARNING_GOOGLE_APPS_SCRIPT.epub
-rwxrwxrwx 1 raghs raghs   32K Jul 26  2021 9781785882517-LEARNING_GOOGLE_APPS_SCRIPT_Code.zip
-rwxrwxrwx 1 raghs raghs  6.0M Jul 31  2021 9781788831345-DJANGO_DESIGN_PATTERNS_AND_BEST_PRACTICES_SECOND_EDITION.pdf
-rwxrwxrwx 1 raghs raghs  4.6M Jul 31  2021 9781788831345-DJANGO_DESIGN_PATTERNS_AND_BEST_PRACTICES_SECOND_EDITION.epub
-rwxrwxrwx 1 raghs raghs  1.6M Jul 31  2021 9781788831345-DJANGO_DESIGN_PATTERNS_AND_BEST_PRACTICES_SECOND_EDITION_Code.zip
-rwxrwxrwx 1 raghs raghs  4.9M Aug  8  2021 9781788995528-HANDSON_DATA_STRUCTURES_AND_ALGORITHMS_WITH_RUST.pdf
-rwxrwxrwx 1 raghs raghs  3.2M Aug  8  2021 9781788995528-HANDSON_DATA_STRUCTURES_AND_ALGORITHMS_WITH_RUST.epub
-rwxrwxrwx 1 raghs raghs  534K Aug  8  2021 9781788995528-HANDSON_DATA_STRUCTURES_AND_ALGORITHMS_WITH_RUST_Code.zip
-rwxrwxrwx 1 raghs raghs  3.6M Aug 21  2021 9781789800982-GO_PROGRAMMING_COOKBOOK_SECOND_EDITION.pdf
-rwxrwxrwx 1 raghs raghs  2.0M Aug 21  2021 9781789800982-GO_PROGRAMMING_COOKBOOK_SECOND_EDITION.epub
-rwxrwxrwx 1 raghs raghs   44M Oct  4  2021 9781789344158-HANDSON_DEEP_LEARNING_ALGORITHMS_WITH_PYTHON.pdf
-rwxrwxrwx 1 raghs raghs   72M Oct  4  2021 9781789344158-HANDSON_DEEP_LEARNING_ALGORITHMS_WITH_PYTHON.epub
-rwxrwxrwx 1 raghs raghs  128M Oct  4  2021 9781789344158-HANDSON_DEEP_LEARNING_ALGORITHMS_WITH_PYTHON_Code.zip
-rwxrwxrwx 1 raghs raghs   33M Oct  5  2021 9781789346411-HANDSON_MACHINE_LEARNING_FOR_ALGORITHMIC_TRADING.pdf
-rwxrwxrwx 1 raghs raghs   37M Oct  5  2021 9781789346411-HANDSON_MACHINE_LEARNING_FOR_ALGORITHMIC_TRADING.epub
-rwxrwxrwx 1 raghs raghs  113M Oct  5  2021 9781789346411-HANDSON_MACHINE_LEARNING_FOR_ALGORITHMIC_TRADING_Code.zip
-rwxrwxrwx 1 raghs raghs   15M Oct 14  2021 9781838647438-BUILDING_GOOGLE_CLOUD_PLATFORM_SOLUTIONS.pdf
-rwxrwxrwx 1 raghs raghs   13M Oct 14  2021 9781838647438-BUILDING_GOOGLE_CLOUD_PLATFORM_SOLUTIONS.epub
-rwxrwxrwx 1 raghs raghs  4.5M Oct 14  2021 9781838647438-BUILDING_GOOGLE_CLOUD_PLATFORM_SOLUTIONS_Code.zip
-rwxrwxrwx 1 raghs raghs   17M Oct 17 12:16 9781789138412-HANDSON_GUI_APPLICATION_DEVELOPMENT_IN_GO.pdf
-rwxrwxrwx 1 raghs raghs   16M Oct 17 12:16 9781789138412-HANDSON_GUI_APPLICATION_DEVELOPMENT_IN_GO.epub
-rwxrwxrwx 1 raghs raghs  367K Oct 17 12:16 9781789138412-HANDSON_GUI_APPLICATION_DEVELOPMENT_IN_GO_Code.zip
-rwxrwxrwx 1 raghs raghs   18M Nov  8 07:11 9781788622592-HANDSON_SOFTWARE_ARCHITECTURE_WITH_GOLANG.pdf
-rwxrwxrwx 1 raghs raghs   15M Nov  8 07:11 9781788622592-HANDSON_SOFTWARE_ARCHITECTURE_WITH_GOLANG.epub
-rwxrwxrwx 1 raghs raghs   49K Nov  8 07:12 9781788622592-HANDSON_SOFTWARE_ARCHITECTURE_WITH_GOLANG_Code.zip
-rwxrwxrwx 1 raghs raghs  3.0M Feb 26 10:04 9781788627917-SECURITY_WITH_GO.pdf
-rwxrwxrwx 1 raghs raghs  1.1M Feb 26 10:04 9781788627917-SECURITY_WITH_GO.epub
-rwxrwxrwx 1 raghs raghs  136K Feb 26 10:05 9781788627917-SECURITY_WITH_GO_Code.zip
-rwxrwxrwx 1 raghs raghs   11M Mar  4 09:42 9781838828844-CPP_DATA_STRUCTURES_AND_ALGORITHM_DESIGN_PRINCIPLES.pdf
-rwxrwxrwx 1 raghs raghs   17M Mar  4 09:42 9781838828844-CPP_DATA_STRUCTURES_AND_ALGORITHM_DESIGN_PRINCIPLES.epub
-rwxrwxrwx 1 raghs raghs  8.5M Mar  4 09:43 9781838828844-CPP_DATA_STRUCTURES_AND_ALGORITHM_DESIGN_PRINCIPLES_Code.zip
-rwxrwxrwx 1 raghs raghs  7.9M Mar  9 11:08 9781786468949-GO_PROGRAMMING_BLUEPRINTS_SECOND_EDITION.pdf
-rwxrwxrwx 1 raghs raghs  5.8M Mar  9 11:08 9781786468949-GO_PROGRAMMING_BLUEPRINTS_SECOND_EDITION.epub
-rwxrwxrwx 1 raghs raghs  4.5M Mar  9 11:09 9781786468949-GO_PROGRAMMING_BLUEPRINTS_SECOND_EDITION_Code.zip
-rwxrwxrwx 1 raghs raghs   50M Mar 12 12:26 9781789134612-HANDSON_SERVERLESS_APPLICATIONS_WITH_GO.pdf
-rwxrwxrwx 1 raghs raghs   47M Mar 12 12:27 9781789134612-HANDSON_SERVERLESS_APPLICATIONS_WITH_GO.epub
-rwxrwxrwx 1 raghs raghs   18M Mar 12 12:27 9781789134612-HANDSON_SERVERLESS_APPLICATIONS_WITH_GO_Code.zip
-rwxrwxrwx 1 raghs raghs  6.0M Apr 15 08:29 9781786468666-BUILDING_MICROSERVICES_WITH_GO.pdf
-rwxrwxrwx 1 raghs raghs  4.7M Apr 15 08:29 9781786468666-BUILDING_MICROSERVICES_WITH_GO.epub
-rwxrwxrwx 1 raghs raghs   33M Apr 15 08:29 9781786468666-BUILDING_MICROSERVICES_WITH_GO_Code.zip
SPRING_REST :
```

## Pick the right word (ONLY)

I want to pick up the entries only of the *Go* - as a full word. 

The right pattern / argument to the `grep` command would be `(^|_)<PATTERN>(_|$)` with an `-E`, where 

 * `-E` stands for an expression 
 * `(^|_)` is the prefixing pattern as I want to pick up the entries surrounded with `_`
 * `PATTERN` &rarr; the term/word we want to pick up/ search for 
 * `(_|$)` is the suffixing pattern 

*Example* : `(^|_)GO(_|$)` - to filter out all the entries matching with `_GO_`. 

```sh
SPRING_REST : ls -ltrh | grep -E "(^|_)GO(_|$)"
-rwxrwxrwx 1 raghs raghs   16M Dec 26  2020 9781838647940-THE_GO_WORKSHOP.pdf
-rwxrwxrwx 1 raghs raghs  5.4M Dec 26  2020 9781838647940-THE_GO_WORKSHOP_Code.zip
-rwxrwxrwx 1 raghs raghs   20M Dec 26  2020 9781838647940-THE_GO_WORKSHOP.epub
-rwxrwxrwx 1 raghs raghs  308K Jun 24  2021 9781789804072-HANDSON_SYSTEM_PROGRAMMING_WITH_GO_Code.zip
-rwxrwxrwx 1 raghs raghs  367K Oct 17 12:16 9781789138412-HANDSON_GUI_APPLICATION_DEVELOPMENT_IN_GO_Code.zip
-rwxrwxrwx 1 raghs raghs  136K Feb 26 10:05 9781788627917-SECURITY_WITH_GO_Code.zip
-rwxrwxrwx 1 raghs raghs   18M Mar 12 12:27 9781789134612-HANDSON_SERVERLESS_APPLICATIONS_WITH_GO_Code.zip
-rwxrwxrwx 1 raghs raghs   33M Apr 15 08:29 9781786468666-BUILDING_MICROSERVICES_WITH_GO_Code.zip
SPRING_REST :
```

## Pick up more relevant words for the same keywords. 

I just noticed that there are books matching with the term `Golang` as well ,and I wanted to include this pattern also in the `grep` command. 

All I did was to include the new pattern &rarr; `grep -E "(^|_)GO(_|$)|(^|_)GOLANG(_|$)"`, where I instruct the `grep` to pick up any entries in the list output stream and matches with either of the patterns `_GO_` OR `_GOLANG_`. 

```sh
SPRING_REST : ls -ltrh | grep -E "(^|_)GO(_|$)|(^|_)GOLANG(_|$)"
-rwxrwxrwx 1 raghs raghs   16M Dec 26  2020 9781838647940-THE_GO_WORKSHOP.pdf
-rwxrwxrwx 1 raghs raghs  5.4M Dec 26  2020 9781838647940-THE_GO_WORKSHOP_Code.zip
-rwxrwxrwx 1 raghs raghs   20M Dec 26  2020 9781838647940-THE_GO_WORKSHOP.epub
-rwxrwxrwx 1 raghs raghs  308K Jun 24  2021 9781789804072-HANDSON_SYSTEM_PROGRAMMING_WITH_GO_Code.zip
-rwxrwxrwx 1 raghs raghs  828K Jun 25  2021 9781789618501-LEARN_DATA_STRUCTURES_AND_ALGORITHMS_WITH_GOLANG_Code.zip
-rwxrwxrwx 1 raghs raghs  367K Oct 17 12:16 9781789138412-HANDSON_GUI_APPLICATION_DEVELOPMENT_IN_GO_Code.zip
-rwxrwxrwx 1 raghs raghs   49K Nov  8 07:12 9781788622592-HANDSON_SOFTWARE_ARCHITECTURE_WITH_GOLANG_Code.zip
-rwxrwxrwx 1 raghs raghs  136K Feb 26 10:05 9781788627917-SECURITY_WITH_GO_Code.zip
-rwxrwxrwx 1 raghs raghs   18M Mar 12 12:27 9781789134612-HANDSON_SERVERLESS_APPLICATIONS_WITH_GO_Code.zip
-rwxrwxrwx 1 raghs raghs   33M Apr 15 08:29 9781786468666-BUILDING_MICROSERVICES_WITH_GO_Code.zip
SPRING_REST :
```

Happy learning :) 

Cheers,\
RM...\
_Raghavan alias Saravanan Muthu_\
15 Apr 2022 | Fri | 08:57:12 AM IST
