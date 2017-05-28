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

[Ruby documentation]: (http://www.ruby-doc.org)

