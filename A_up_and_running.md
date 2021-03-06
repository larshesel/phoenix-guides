The aim of this first guide is to get a Phoenix application up and running as quickly as possible.

Before we begin, we will need to install Elixir and Erlang. The Elixir site itself has the latest and most complete [installation information](http://elixir-lang.org/install.html). Currently, Phoenix requires Elixir version 1.0.4 or greater which in turn requires Erlang version 17.5 or greater.

Let's get started.

First, lets install the `phoenix.new` mix archive:

```console
$ mix archive.install https://github.com/phoenixframework/phoenix/releases/download/v0.11.0/phoenix_new-0.11.0.ez
```

Now `mix phoenix.new` can be run from any directory to bootstrap our Phoenix application. Phoenix will accept either an absolute or relative path for the directory of our new project. Assuming that the name of our application is `hello_phoenix`, either of these will work.

```console
$ mix phoenix.new /Users/me/work/elixir-stuff/hello_phoenix
```

```console
$ mix phoenix.new ../hello_phoenix
```

Note: If we don't prepend a path to our application name, Phoenix will generate our new application inside of the Phoenix repo itself. That will work, but if we want our application to be in its own repo, we need to generate our application outside of Phoenix.

For our purposes, a relative path will do.

```console
$ mix phoenix.new ../hello_phoenix
* creating ../hello_phoenix/README.md
. . .
```

Phoenix generates the directory structure and all the files we will need for our application. When it's done, it will ask us if we want it to install our `mix` dependencies for us. Let's say yes to that.

```console
Install mix dependencies? [Yn] y
* running mix deps.get
```

The `phoenix.new` task will also prompt us to install [brunch.io](http://brunch.io) and its dependencies for asset management. This is optional, and will require that [node.js](https://nodejs.org/) and npm are installed on our system. For our example, let's say yes to that as well.

```console
Install brunch.io dependencies? [Yn]
* running npm install
npm http GET https://registry.npmjs.org/clean-css-brunch
. . .
```

Note: If we don't want to use brunch.io for our static asset compilation, we can pass the `--no-brunch` flag to `phoenix.new`.

```console
$ mix phoenix.new ../hello_phoenix --no-brunch
```

Once our brunch.io dependencies are installed, the task will prompt us to change into our project directory and start our application.

```console
We are all set! Run your Phoenix application:

$ cd ../hello_phoenix
$ mix phoenix.server

You can also run it inside IEx (Interactive Elixir) as:

$ iex -S mix phoenix.server
```

Let's do that now.

```console
$ cd ../hello_phoenix
$ mix phoenix.server
```

By default Phoenix accepts requests on port 4000. If we point our favorite web browser at [http://localhost:4000](http://localhost:4000), we should see the Phoenix Framework welcome page.

![Phoenix Welcome Page](/images/welcome-to-phoenix.png)

If your screen looks like the image above, congratulations! You now have working Phoenix application.

Locally, our application is running in an iex session. To stop it, we hit ctrl-c twice, just as we would to stop iex normally.

The next step is customizing our application just a bit to give us a sense of how a Phoenix app is put together.
