---
layout: post
title:  "Manipulate Strings in Ruby with Iteration"
date:   2017-04-25
excerpt: "Today we look at manipulating strings by iterating through them."
tag:
- Dev Bootcamp
- Ruby
- control flow
- iteration
---

## String Manipulation

We are tasked with the assignment of creating a method that takes in a string of a person's first and last name, and then performs the following manipulation on it:

* Swaps the first and last name
* Change all of the vowels to the next vowel in 'aeiou'
* Changes all of the consonants to the next consonant in the alphabet.

Phew. This is going to be tough! Now let's get started.

First of all, let's think about ways we can use Ruby's built-in array methods to swap the first and last name, so that we can get to work on the rest of our task. A great place to start is the official [Ruby documentation].

When we search through the documentation for the `String` class, we encounter a method called `.split()`. This method divides a string into substrings, based on a delimiter. We can use it as such:

```ruby
name = 'Billy Bagpipes'
name.split(' ')

# => ['Billy', 'Bagpipes']
```

Now that we have the first and last name separated into an array, we need to find a way to reverse the two in place. Let's go through the docs to find...oh wait, that's it: reverse!

```ruby
name = 'Billy Bagpipes'
name.split(' ').reverse

# => ['Bagpipes', 'Billy']
```

Awesome. Now that we have the names in reverse order, we just have to find a way to join the two together. As we search through the Array class methods available to us, we find -- voila! -- `.join()`!

```ruby
name = 'Billy Bagpipes'
name.split(' ').reverse.join(' ')

# => 'Bagpipes Billy'
```

Boom. Now we have the first step of our method complete and can work on the difficult tasks ahead.

Given that we need to change the vowels in the name to the next vowel in the string `'aeiou'`, we will want to be able to iterate over those letters and determine whether any of the vowels in the string match the letters in the name. If so, let's change that vowel to the next vowel in the list.

The first thing we will want to do is set a variable to store the name, and perform the actions above to reverse and join the name backwards. Next, we can call a the `.split` method on it, so that we can iterate through each letter of the first and last name in an array.

```ruby
name = 'Billy Bagpipes'
split_name = name.split(' ').reverse.join(' ').split('')

# => ["b", "a", "g", "p", "i", "p", "e", "s", " ", "b", "i", "l", "l", "y"]
```

Let's also throw the vowels and consonants into their own arrays so we can make use of them as well, during our comparison check:

```ruby
vowels = "aeiou".split("")
consonants = "bcdfghjklmnpqrstvwxyz".split("")

p vowels
# => ["a", "e", "i", "o", "u"]

p consonants
# => ["b", "c", "d", "f", "g", "h", "j", "k", "l", "m", "n", "p", "q", "r", "s", "t", "v", "w", "x", "y", "z"]
```

Okay, now we have the three arrays that we will need to iterate through, and manipulate. Let's go back to the Ruby docs and see which `Array` methods we can use to manipulate the original `split_name` array.

Searching through the docs, we find a method called `.map` which will allow us to iterate through an array and return a new array, as long as we save it to a variable. Next, we need to use conditionals and control flow to search for vowels and consonants, and change them to the appropriate letters. We can do this using simple `if/elsif`statements.

```ruby
  new_name = split_name.map do |letter|
    if letter == "u"
      letter = "a"
    elsif letter == "z"
      letter = "b"
    elsif letter == ' '
      letter = ' '
    elsif index = vowels.index(letter)
      letter = vowels[index+1]
    elsif index = consonants.index(letter)
      letter = consonants[index+1]
    end
  end
```

Above, we also account for the edge cases at the end of the respective strings (or arrays, in the current form). Otherwise, we just assign the value of the next index to each vowel and consonant, and save the results into a `new_name` array that we need to now assemble back into a readable string name.

```ruby
spy.join('').split.map(&:capitalize).join(' ')
```

Now we have our full method, which takes in a first and last name as one string, and then manipulates it into a sort of spy name. 

```ruby
def spy_name(name)

new_name = name.downcase.split(' ').reverse.join(' ').split('')
vowels = "aeiou".split("")
consonants = "bcdfghjklmnpqrstvwxyz".split("")

  new_name = new_name.map do |letter|
    if letter == "u"
      letter = "a"
    elsif letter == "z"
      letter = "b"
    elsif letter == ' '
      letter = ' '
    elsif index = vowels.index(letter)
      letter = vowels[index+1]
    elsif index = consonants.index(letter)
      letter = consonants[index+1]
    end
  end
  new_name.join('').split.map(&:capitalize).join(' ')
end
```

```ruby
spy_name('Billy Bagpipes')

# => "Cehqoqit Commz"
```

Get your spy gadgets, and you're ready to go undercover overseas!


[Ruby documentation]: (http://www.ruby-doc.org)

