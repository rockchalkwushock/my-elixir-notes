# About

`elixir` is a functional programing (FP) language. This concept is different from that of the object oriented programing (OOP) present in languages like `ruby`, `java`, and the majority of `javascript`.

## The OOP Approach

For the example in Grider's tutorial we are making a cards game so we might have something like

```js
class Card {
  constructor() {
    this.suit = 'hearts',
    this.value = 'two'
  }
}
class Deck {
  constructor() {
    this.cards = Card
  }
  // These methods are only available on instances of Deck
  shuffle = () => {}
  save = () => {}
  load = () => {}
}

const deck = new Deck()
deck.cards() // [<Card1>, <Card2>, <Card3>]
deck.shuffle() // [<Card1>, <Card2>, <Card3>]
deck.load() // <Deck[<Card1>]>
```

## The FP Approach

The Cards _module_ is a standalone object, and has no idea what an instance variable is. In `elixir` when I call `Cards.create_deck` it will return to me an array of cards. Should I want to shuffle those cards `Cards.shuffle` accepts an array of strings and outputs a shuffled array of strings. Kind of a _"what goes in must come out"_ idea. `shuffle` is not dependent on anything from `Cards` no `this.xyz`. You could pass any array of strings to this function and it will return a **copy** of the original array of strings shuffled. `elixir` practices _immutability_ by default. This makes my chest hair tingle with joy :joy:

```elixir
def module Cards do
  def create_deck do
  end
  def shuffle do
  end
  def save do
  end
  def load do
  end
end
```

In `elixir` we can have multiples of the same named function:

```elixir
def shuffle do
end
def shuffle(deck) do
end
def shuffle(deck, times) doe
end
```

In the case of the example app running `Cards.shuffle` will return an error message:

```sh
** (UndefinedFunctionError) function Cards.shuffle/0 is undefined or private. Did you mean one
of:

      * shuffle/1

    (cards) Cards.shuffle()
```

`iex` is smart enough to say:

> _"Hey guy, you called `shuffle` with no arguments and I don't have a shuffle with 0 arguments; but I do have a shuffle with 1 argument. I'm thinking you mean that right?" (`iex` under it's assembly code whispers, "This guy is an idiot!")_

> NOTE: 'arity' the number of arguments of a function written as `function/#`

`elixir` comes with a **TON** of native modules. This is like the batman utility belt to end all batman utility belts! The docs page [here](https://hexdocs.pm/elixir/Kernel.html) lists all them out and gives descriptions with examples for all the methods under those modules :rocket:

There are also docs for `mix`, `iex`, etc that can be accessed [here](https://elixir-lang.org/docs.html) make sure you look at the **stable** branch dude!