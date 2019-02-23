# Intro to Docker

## Install Heroku CLI
> https://devcenter.heroku.com/articles/heroku-cli

## Deploy to Heroku

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

push container to heroku, it will start automatically
```
docker push registry.heroku.com/jimareed-restapi/web
```

Create a new release
```
heroku container:release web
```

Test the app

> https://jimareed-restapi.herokuapp.com/fruit

Cleanup
```
heroku destroy --app jimareed-restapi
```