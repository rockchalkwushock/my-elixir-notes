# Command-Line-Interface

There are a few commands installed by `elixir` I will be making used of. At the moment `mix` & `iex` are what I know about.

`iex` the _interactive elixir shell_

This is where I can run `elixir` code just like using `node`, `mongo`, or `psql`.

```sh
$ iex
$ iex(1)> 1 + 1
$ 2
```

`mix` is how I can make new project, docs, run tests, and I'm sure there is more!

## Running Elixir Code

`iex -S mix` the code is compiled by `elixir` and now I am in the `iex` shell where I can execute the code.

```
iex(1)> Cards
Cards
iex(2)> Cards.hello
:world
iex(3)> # Ctrl + C will lead to a menu
BREAK: (a)bort (c)ontinue (p)roc info (i)nfo (l)oaded
       (v)ersion (k)ill (D)b-tables (d)istribution
a
```

> Auto-tab completion is available in `iex` :rocket:

I can leave `iex` open and work on the project; however this isn't like hot module reloading when I save. `iex` still has the previous code. I don't have to `abort` and re-enter `iex` though. I can instead just run the `recompile` command:

```iex
iex(2)> recompile
Compiling 1 file (.ex)
:ok
```

## Creating a New Project

`mix new <project>`

```sh
mix new cards
* creating README.md
* creating .gitignore
* creating mix.exs
* creating config
* creating config/config.exs
* creating lib
* creating lib/cards.ex
* creating test
* creating test/test_helper.exs
* creating test/cards_test.exs

Your Mix project was created successfully.
You can use "mix" to compile it, test it, and more:

    cd cards
    mix test

Run "mix help" for more commands.
```