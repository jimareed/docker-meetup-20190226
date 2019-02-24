# Intro to Docker

<img src="./images/docker.png" align="right"
     title="Docker" width="50%" height="50%">

A brief introduction to Docker.  Very high level, designed for beginners.  Here's what we'll cover:
- Before containers
- What is Docker
- Why we like it
- How it works
- Dockerfile
- Build and run a container
- Deploy to Heroku
- Docker Compose
- Orchestration

## Before containers

- Before VM's and containers, traditional server architecture required large servers that were designed peak load, typically running a single application in production.  
- Common complaint from customers for large enterprise software deployments:
We've spent millions on hardware but it's normally running at 10% utilization.
- Virtual machines made it much easier to better utilize large servers.  But they still had the overhead that each VM had to run it's own operating system.
- Containers allow you to package only what you need to run your app. 

<p  align="center">
    <img src="./images/traditional-2-containers.png" alt="Traditional Servers to Containers"
       width="80%" height="80%">
    </img>
</p>


## What is Docker
<img src="./images/docker.png" align="right"
     title="Docker" width="25%" height="25%">

- A tool that makes it easy to create, deploy, and run containers.  
- Bundles an application with all of it’s dependencies into a single self contained package.
- Always runs the same way in any environment.

## Why we like it
- Build and test the same way on your laptop as in the cloud.
- Super fast to start/stop containers.
- Efficient use of resources.
- Portable, easy to move across cloud vendors.
- Easy to connect containers together so that you can abstract dependencies to other services.
- Well suited for cloud, microservices and continuous delivery.

## How it works

## Dockerfile

## Build and run a container
## Deploy to Heroku
Now that we've build our first Docker container, it is easy to deploy it anywhere.  Here are steps to deploy it to Heroku.

Install Heroku CLI
> https://devcenter.heroku.com/articles/heroku-cli

Pull image from docker hub
```
docker pull jimareed/restapi
```

Login to heroku registry
```
heroku container:login
```

Create a heroku app (must be unique across Heroku)
```
heroku create --app jimareed-restapi
```

Tag image to be deployed to heroku
```
docker tag jimareed/restapi registry.heroku.com/jimareed-restapi/web
```

Push container to heroku
```
docker push registry.heroku.com/jimareed-restapi/web
```

Create a new release
```
heroku container:release web --app jimareed-restapi
```

Test the app

> https://jimareed-restapi.herokuapp.com/fruit

Cleanup
```
heroku destroy --app jimareed-restapi
```
## Docker Compose
## Orchestration

