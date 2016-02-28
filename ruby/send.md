#send

Today, I was did a kata on Codewars that required the send method. In the process I discovered two slightly different applications of the method.

The ruby [docs](http://ruby-doc.org/core-2.3.0/Object.html#method-i-send) provide the following example of the send method. In this case we are calling send on an instance of Klass and passing in Klass's hello method.

```ruby
  class Klass
    def hello(*args)
      "Hello " + args.join(' ')
    end
  end
  k = Klass.new
  k.send :hello, "gentle", "readers"   #=> "Hello gentle readers"
  ```

In the solution to the kata, I used send without calling it on an instance:

```ruby
  def add num
    num + 1
  end

  def mult num
    num * 30
  end

  def chain(input, methods)
    methods.each {|method| input = send(method, input)}
    input
  end

  chain(2, [:add, :mult])
  ```

In this case, 'send' assumes an implicit 'self' as the receiver (self.send), which is the main object in this case.

I found this post, which says: Ruby allows you to define simple functions at the top level scope. How does Ruby do this? Before your script starts to run, Ruby automatically creates a hidden object known as the top self object, an instance of the Object class. This object serves as the default receiver for top level methods. The string “main” is how Ruby represents the top self object as a string.

More at [calling a method without a reciever](https://stackoverflow.com/questions/35675975/calling-a-method-without-an-explicit-receiver-in-the-main-environment).