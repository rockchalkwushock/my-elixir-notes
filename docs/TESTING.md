# Testing in Elixir

Testing is a first-class citizen and I _should_ never need to bring in any external packages to run my tests. When the project was created a `test/` was made and it contained two files: `card_test.exs` and `test_helper.exs`. I am guessing at the moment that the `_test` is the convention that the command looks for or it just looks and runs all files located in the `test/`.

`elixir` gives me the capability to test my examples in the docs to make sure they return as I'm showing the world they should :hankey:

Everything is built in so it's as simple as using `assert` or `refute` and I'm golden pony boy :rocket:

```elixir
defmodule CardsTest do
  use ExUnit.Case
  doctest Cards

  test "create_deck makes 52 cards" do
    deck_length = length(Cards.create_deck)
    assert deck_length == 52
  end

  test "shuffling a deck randomizes it" do
    deck = Cards.create_deck
    refute deck == Cards.shuffle(deck)
  end
end
```