# Pivotal Cloud Foundry Blog

Welcome to our little slice of the internets!  This blog is dedicated to technical (and cultural) posts by the Pivotal Cloud Foundry Engineering team.  If that's you, then *please*, *please*, *please* contribute!

## Running Locally

This site uses [Hugo](http://gohugo.io) v0.14, which is easy to install:

~~~
$ brew install hugo
$ hugo version
Hugo Static Site Generator v0.14 BuildDate: 2015-06-16T21:41:12+01:00
~~~

Now, run `./bin/watch` in a terminal, and browse to [http://localhost:1313](http://localhost:1313) to see your local copy.

Hugo has [LiveReload](http://livereload.com/) built in, so if you have that configured in your browser, your window will update as soon as you make a change.  Hugo is *fast*, so you might not realize the reload has already happened.

## Writing a Post

1. Fork this repo to a copy you can push to.
1. Add yourself as an author (first time only, obvs.):

    ~~~
    $ cp ./data/authors/tammer.yml ./data/authors/bob.yml
    $ vi ./data/authors/bob.yml
    ~~~

1. Create a new draft post with `./bin/new_post name-of-post`.  It's just markdown, and the template provides instructions on any advanced bits.  Be sure to change the metadata in the file's YAML front-matter -- one thing to change immediately is the `author:` value should be the name of your author file (`bob` in the example above).

1. *Meta:* If you want to change the default new post template, it's in `./archetypes/post.md`.

## Publishing Your Copy

You can publish your fork to your own cf org by running `./bin/publish`.  That script will push your blog to `pivotal-cf-blog-$USER` (where `$USER` is your local unix username.  You'll need to make sure you've `cf target`ed the org and space you want to push to.

## Publishing to Production

It's all about PRs.  Submit your post as a pull-request, gather feedback, iterate, etc.

Once the PR's ready, the engineering directors can then publish via `./bin/publish prod`.

## Changing the style

`./themes/pivotal-ui` is a port of the [Pivotal UI](https://github.com/pivotal-cf/pivotal-ui) project.  I basically copied the compiled css and image files over.  If you want to change the look of this site, then you should edit the templates in there.
