# CRUD: Status Codes Based On REST Methods

## In your own words, describe what each group of status code represents:


__*100’s = they usually tell the client that the header part of the request has been received and the server will try to comply with the demand of the client.*__

__* 200’s = They tell the client that its request was accepted. In case of asynchronous processing of a request (202)*__

__* 300’s = They tell the client that the resource they are requesting isn’t available at the expected location anymore*__


__* 400’s =  They are all about invalid requests a client sent to a server. *__


__* 500’s = These are the server error codes. Often they indicate problems with overwhelmed servers or unreachable servers behind proxies*__


## What is a status code 202? 

__* Accepted, This code tells the client that the request was valid*__


## What is a status code 308? 

__*Permanent Redirect ,This tells the client to use another URL to access the resource and not use the current URL anymore.*__


## What code would you use if an update didn’t return data to a client? 

__*204 No Content*__


## What code would you use if a resource used to exist but no longer does?

## 414 Request-URI Too Long - 


## What is the ‘Forbidden’ status code?

__* 404 Not Found*__




## Why do we need to pull our MongoDB database string out of our server and put it into our .env?


__* when we deploy our application we are going to want to use something that's not our localhost so we need to pull this out into an enviroment variable *__
  
## What is middleware?

__*is essentially code that runs when the server gets the request but before it gets passed to our routes *__

## What does app.use(express.json()) do?


__* which will allow us to use any middleware that we want *__

## What does the /:id mean in a route?


__* this is aparameter that we can access by typing req.pqrqms.id this would give us access to whatever they pass in after the first slash*__

## What is the difference beween PUT and PATCH?


__* patch : when we need to update based on what the user passes us put : it will update all the info to describe it all at once instead of the info that gets passed *__

## How do you make a defalut value in a schema?


__* so we are just going to use default and set this to date.now ,if we don't pass our date it is just going to default it to current date  *__
 
