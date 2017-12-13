# Maps

These are similar to objects in JS.

A map in `elixir`: `%{key: value}`

## Creating Maps

```sh
$ iex(1)> colors = %{primary: "red"}
$ iex(2)> colors.primary
"red"
$ iex(3)> colors = %{primary: "red", secondary: "blue"}
$ iex(4)> colors.secondary # dot notation
"blue"
```

Works with Pattern Matching

```sh
$ iex(1)> colors = %{primary: "red", secondary: "blue"}
$ iex(2)> %{secondary: secondary_color} = colors
$ iex(3)> secondary_color
"blue"
```

## Updating Maps

Remember _immutability_ is built into `elixir` by default so you cannot just change the value on a property and expect it to work!

### With a native function

```sh
$ iex(1)> Map.put(colors, :primary, "blue")
```

`Map.put()` does **NOT** update the map it returns a copy of the original map with the updated values.

### With syntax

```sh
$ iex(1)> %{ colors | primary: "blue" }
```

This is similar to the spread operator in JS.

```js
{ ...colors, primary: 'blue' }
```

The difference is you cannot use the above for _adding_ to an existing map you must use one of the native methods on the `Map` module!