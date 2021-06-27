---
title: "Mongodb Connect to Cluster"
date: 2021-06-27T21:37:44+05:30
draft: true
tags:
  - TODO
  - Technical
  - Database
  - MongoDB
toc: true
author: Raghs
---

In this blog post, we will see how to connect to the MongoDB cluster via `mongoshell` and `vscode`. 

<!--more-->

# Prerequisites 

# Connection Parameters

# Connection via `mongoshell`

## Output 

```sql
C:\installedSoft\mongodb-win32-x86_64-windows-4.4.6\bin                                                                                                                      
λ mongo "mongodb+srv://raghscluster.lxy8a.mongodb.net/myFirstDatabase" --username m001-student                                                                               
MongoDB shell version v4.4.6                                                                                                                                                 
Enter password:                                                                                                                                                              
connecting to: mongodb://raghscluster-shard-00-00.lxy8a.mongodb.net:27017,raghscluster-shard-00-01.lxy8a.mongodb.net:27017,raghscluster-shard-00-02.lxy8a.mongodb.net:27017/m
yFirstDatabase?authSource=admin&compressors=disabled&gssapiServiceName=mongodb&replicaSet=RaghsCluster-shard-0&ssl=true                                                      
Implicit session: session { "id" : UUID("b1b797c6-0d95-42f1-b3dd-854e9319ea2f") }                                                                                            
MongoDB server version: 4.4.6                                                                                                                                                
Error while trying to show server startup warnings: user is not allowed to do action [getLog] on [admin.]                                                                    
MongoDB Enterprise RaghsCluster-shard-0:PRIMARY> show db                                                                                                                     
uncaught exception: Error: don't know how to show [db] :                                                                                                                     
shellHelper.show@src/mongo/shell/utils.js:1191:11                                                                                                                            
shellHelper@src/mongo/shell/utils.js:819:15                                                                                                                                  
@(shellhelp2):1:1                                                                                                                                                            
MongoDB Enterprise RaghsCluster-shard-0:PRIMARY> show dbs                                                                                                                    
admin  0.000GB                                                                                                                                                               
local  5.061GB                                                                                                                                                               
video  0.001GB                                                                                                                                                               
MongoDB Enterprise RaghsCluster-shard-0:PRIMARY> use video                                                                                                                   
switched to db video                                                                                                                                                         
MongoDB Enterprise RaghsCluster-shard-0:PRIMARY> show collection                                                                                                             
uncaught exception: Error: don't know how to show [collection] :                                                                                                             
shellHelper.show@src/mongo/shell/utils.js:1191:11                                                                                                                            
shellHelper@src/mongo/shell/utils.js:819:15                                                                                                                                  
@(shellhelp2):1:1                                                                                                                                                            
MongoDB Enterprise RaghsCluster-shard-0:PRIMARY> show collections                                                                                                            
movieDetails                                                                                                                                                                 
MongoDB Enterprise RaghsCluster-shard-0:PRIMARY> db.movieDetails.findOne()                                                                                                   
                                                                                                                                                                             
        "_id" : ObjectId("5d939292f2a1ca84bc3bcb02"),                                                                                                                        
        "title" : "Star Trek",                                                                                                                                               
        "year" : 2009,                                                                                                                                                       
        "rated" : "PG-13",                                                                                                                                                   
        "runtime" : 127,                                                                                                                                                     
        "countries" : [                                                                                                                                                      
                "USA",                                                                                                                                                       
                "Germany"                                                                                                                                                    
        ],                                                                                                                                                                   
        "genres" : [                                                                                                                                                         
                "Action",                                                                                                                                                    
                "Adventure",                                                                                                                                                 
                "Sci-Fi"                                                                                                                                                     
        ],                                                                                                                                                                   
        "director" : "J.J. Abrams",                                                                                                                                          
        "writers" : [                                                                                                                                                        
                "Roberto Orci",                                                                                                                                              
                "Alex Kurtzman",                                                                                                                                             
                "Gene Roddenberry"                                                                                                                                           
        ],                                                                                                                                                                   
        "actors" : [                                                                                                                                                         
                "Chris Pine",                                                                                                                                                
                "Zachary Quinto",                                                                                                                                            
                "Leonard Nimoy",                                                                                                                                             
                "Eric Bana"                                                                                                                                                  
        ],                                                                                                                                                                   
        "plot" : "The brash James T. Kirk tries to live up to his father's legacy with Mr. Spock keeping him in check as a vengeful, time-traveling Romulan creates black hol
es to destroy the Federation one planet at a time.",                                                                                                                         
        "poster" : "http://ia.media-imdb.com/images/M/MV5BMjE5NDQ5OTE4Ml5BMl5BanBnXkFtZTcwOTE3NDIzMw@@._V1_SX300.jpg",                                                       
        "imdb" : {                                                                                                                                                           
                "id" : "tt0796366",                                                                                                                                          
                "rating" : 8,                                                                                                                                                
                "votes" : 483229                                                                                                                                             
        },                                                                                                                                                                   
        "tomato" : {                                                                                                                                                         
                "meter" : 95,                                                                                                                                                
                "image" : "certified",                                                                                                                                       
                "rating" : 8.2,                                                                                                                                              
                "reviews" : 329,                                                                                                                                             
                "fresh" : 312,                                                                                                                                               
                "consensus" : "Star Trek reignites a classic franchise with action, humor, a strong story, and brilliant visuals, and will please traditional Trekkies and ne
w fans alike.",                                                                                                                                                              
                "userMeter" : 91,                                                                                                                                            
                "userRating" : 4.1,                                                                                                                                          
                "userReviews" : 743375                                                                                                                                       
        },                                                                                                                                                                   
        "metacritic" : 82,                                                                                                                                                   
        "awards" : {                                                                                                                                                         
                "wins" : 22,                                                                                                                                                 
                "nominations" : 77,                                                                                                                                          
                "text" : "Won 1 Oscar. Another 22 wins & 77 nominations."                                                                                                    
        },                                                                                                                                                                   
        "type" : "movie"                                                                                                                                                     
}                                                                                                                                                                            
MongoDB Enterprise RaghsCluster-shard-0:PRIMARY>                                
```

# Connection via `vscode`




Cheers,\
RM...\
_Raghavan alias Saravanan Muthu_\
27 Jun 2021 | Sun | 21:37:44 PM IST
