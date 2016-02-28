#reduce

Yesterday, I  did a kata on Codewars that involved passing iterating over an array of functions. One of the highlighted solutions used the reduce method.

Reduce, which is also know as inject, takes an array and reduces it to a single value.

You can use reduce with a symbol that names an operator:

```ruby
  ([3, 4, 5]).reduce(:+) => 12
```
Or a block, where the argument 'sum' is used as an accumulator and n is passed each value of the array:

```ruby
  ([3, 4, 5]).reduce{ |sum, n| sum + n } => 12
```

Reduce can also be passed a starting value:

```ruby
([3, 4, 5]).reduce(2, :+) => 12

([3, 4, 5]).reduce(2) { |sum, n| sum + n } => 14
```

The Codewars kata passed an intial value to each function in an array of functions and returned the final value:

```ruby
  def add num
    num + 1
  end

  def mult num
    num * 2
  end

  def chain(value, functions)
    functions.reduce(value) { |value, function| send(function, value) }
  end

  chain(2, [:add, :mult]) => 6
  ```