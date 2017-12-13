# Keyword Lists

```sh
$ iex(1)> colors = [{:primary, "red"}, {:secondary, "green"}]
[primary: "red", secondary: "green"]
$ iex(2)> colors[:primary]
"red"
$ iex(3)> colors = [primary: "red", secondary: "blue"]
[primary: "red", secondary: "blue"]
```

Both line 1 & 3 are valid. `Maps` can only have unique keys.

```sh
$ iex(1)> colors = %{primary: "red", primary: "blue"}
%{primary: "blue"} # second primary overwrites first
$ iex(2)> colors = %{primary: "red", primary: "blue"}
[primary: "red", primary: "blue"]
```

This is very useful in `ecto`. Whatever that thing is?

Grider's example of this concept in practice:

```sh
$ iex(1)> query = User.find_where([where: user.age > 10, where: user.subscribed == true])
```

You can choose to remove the [] on the keyword list if and **ONLY** if the keyword list is the last argument to the function:

```sh
$ iex(1)> query = User.find_where(where: user.age > 10, where: user.subscribed == true)
```