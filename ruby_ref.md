# Ruby Reference

#### Check Ruby version (in terminal)
```
ruby -v
```

#### Execute `main.rb`
```
ruby main.rb
```

#### Class
```Ruby
class Rectangle
  attr_accessor :s1, :s2

  def initialize s1, s2
    @s1 = s1
    @s2 = s2
  end

  def area
    @s1*@s2
  end
end

rect1 = Rectangle.new 3, 4
puts rect1.area
rect1.s1 # this works because attr_accessor

```

#### User input
```Ruby
puts "Say something!"
answer = gets.chomp
puts "You said, '#{answer}'"
```
notice that `.chomp` is to neglect the new line when user press the `Enter key`.


#### Proc
```Ruby
def sayHello
  puts "Hello!"
end

# turn method into proc (object)
say_hello = Proc.new do
  sayHello
end

# call someProc twice
def twiceDo someProc
  someProc.call
  someProc.call
end

twiceDo say_hello
```
