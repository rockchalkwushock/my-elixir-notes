# Installing Dependencies

`elixir` uses `hex` as it's package manager for installing external dependencies to a project. By going into the `mix.exs` file at the root of the project I can add a dep to the segment below:

```elixir
# Run "mix help deps" to learn about dependencies.
  defp deps do
    [
      {:ex_doc, "~> 0.12"}
      # {:dep_from_hexpm, "~> 0.3.0"},
      # {:dep_from_git, git: "https://github.com/elixir-lang/my_dep.git", tag: "0.1.0"},
    ]
  end
```

`mix.exs` is basically my `package.json`.

Now I can run the command:

```sh
mix deps.get
```

On the first time running this command I was asked to install `hex` by `elixir`. Doing this generates a `deps/` directory in the project and a `mix.lock` (just like a `yarn.lock`). It will also generate a `.hex` in the home directory.