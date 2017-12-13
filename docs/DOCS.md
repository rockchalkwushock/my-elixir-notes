# Creating Documentation for Elixir Projects

First install `ex_doc`

```elixir
# inside `mix.exs`
defp deps do
  [{:ex_doc, "~> 0.12"}]
end
```

```sh
mix deps.get
```

Now that `ex_doc` is present I can create two different kinds of docs: Module and Function.

Module docs just give a description of what the module does or entails.

```elixir
defmodule Cards do
  @moduledoc """
    Provides methods for creating and handling a deck of cards.
  """
```

Function docs tell what the function does and I can provide example code.

```elixir
@doc """
    Determins whether a deck contains a given card

  ## Example

      iex> deck = Cards.create_deck
      iex> Cards.contains?(deck, "Ace of Spades")
      true

  """

  def contains?(deck, card) do
    Enum.member?(deck, card)
  end
```

To generate the documentation:

```sh
mix docs
```

Note that the syntax/styling for the documentation is very specific, especially for the example code. The example code will be ran by my test suite unless I remove it from this block from the tests

```elixir
defmodule CardsTest do
  use ExUnit.Case
  doctest Cards # Remove if don't want to test doc examples
```