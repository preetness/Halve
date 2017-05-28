---
layout: post
title:  "Using Classes in Ruby"
date:   2017-05-07
excerpt:
tag:
- Dev Bootcamp 
- learn to code
- Ruby
- classes
---

In Ruby, every object belongs to a class. We can always check to see which class an object belongs to by using the `.class` or `is_a?` methods:

```ruby
'Hello'.class

# => String

123.is_a?(Fixnum)

# => true
```

Every object is an instance of a class and derives any special built-in methods from that class. For example, the `String` class gives us access to a `.length` method, which allows any instance of that class to then use. We can explicitly instantiate a new String object in this way:

```ruby
hello = String.new('hi')
hello.length 

# => 2
```

Or Ruby allows us to just set a variable equal to the string, and it will implicitly create a new instance of the String class:

```ruby
hello = 'hi'
hello.length

# => 2
```

We want to create classes in our programs, to allow for flexibility and to adhere to the design principle of 'single responsibility'. 

(To be continued...)