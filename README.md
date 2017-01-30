# Heroku Subdir Buildpack

Imagine you have a single code base, which has a few different applications within it... or at least the ability to run a few different applications. Or, maybe you're Google with your mono repo?

In any case, how do you manage this on Heroku? You don't. Heroku applications assume one repo to one application. 

Enter the Heroku Subdir Buildpack, as an alternative of the [Multi Procfile Buildpack](https://github.com/heroku/heroku-buildpack-multi-procfile)).

# Usage

1. Write a bunch of Procfiles and scatter them through out your code base.
2. Create a bunch of Heroku apps.
3. For each app, set `BUILD_SUBDIR=relative/path/to/subdir/in/your/codebase`, and of course:
   `heroku buildpacks:add -a <app> https://github.com/ryanbrainard/heroku-buildpack-subdir`
4. For each app, `git push git@heroku.com:<app> master`
