# Heroku TomEE Buildpack

This is a [Heroku Buildpack](https://devcenter.heroku.com/articles/buildpacks) for running [TomEE AS](https://tomee.apache.org/).

## Usage

Put your WAR file(s) in `target/` and deploy.

## Using with the Java buildpack

You can use the standard Heroku Java buildpack to compile your WAR file, and then have TomEE run it:

```sh-session
$ heroku buildpacks:clear
$ heroku buildpacks:add heroku/java
$ heroku buildpacks:add https://github.com/pedroarapua/heroku-buildpack-tomee
```

Then deploy your Maven project with a `pom.xml`, Heroku will run the Java buildpack to compile it, and as long as you output a `target/*.war` file the Wildfly buildpack will run it.
