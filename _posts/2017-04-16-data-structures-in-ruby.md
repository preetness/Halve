---
layout: post
title:  "Data Structures in Ruby"
date:   2017-04-16
excerpt: "Data structures are critical for us as programmers."
tag:
- Dev Bootcamp
- Ruby
- data structures
- arrays
- hashes
---

Data structures are an important part of any programming language. When we have smaller sets of information, such as `age = 65`, it is easier to work with and pass around that information. However, what if need to work with a larger set of information, such as the ages of hundreds of users? That is where data structures come in. We can store large sets of data in arrays, or hashes, and then manipulate those data sets as we need to for our program.

For example, let's say we need to store the grades of a particular student in our class. Here is one way we could do so:

`tims_grades = [87, 92, 76, 81, 96, 79, 90]`

How can we access a particular grade from this array? By using the index of the position in the array. Like in most other programming languages arrays and hashes are zero indexed, meaning the first element of the collection is accessed using the index of 0. So to access the first of Tim's grades, we would simply use `tims_grades[0]`. Ruby also has other built-in methods that allow us to access the first or last element by simply typing:

```ruby
tims_grades.first
# => 87

tims_grades.last
# => 90
```

We can also use a negative index to retrieve the last element of the collection, as such:

```ruby 
tims_grades[-1]
# => 90
```

Ruby allows us the flexibility to use various methods to access and change data in collections. What if we wanted to sort the collection of elements from lowest to highest? Simple.

```ruby
tims_grades.sort
# => [76, 79, 81, 87, 90, 92, 96]
```

Hashes are another data structure in Ruby, which allow us to store data. They are a collection of various key-value pairs. Unlike arrays though, they are not indexed by integers, but by their keys. Here is an example of a Ruby hash, creating a collection of students and their favorite books:

```ruby
high_school_students = {
  :Michael => 'Catcher in the Rye',
  :Carter => 'Harry Potter',
  :Jillian => 'The Grapes of Wrath',
  :Emilia => 'Treasure Island'
}
```
To access the values of the hash, we simply use the keys of the hash

```ruby
high_school_students[:Jillian]
# => 'The Grapes of Wrath'
```

Note that although Ruby allows us to use symbols for keys (`:Michael`) and a hash rocket (`=>`), we can also write the previous hash as follows:


```ruby
high_school_students = {
  'Michael': 'Catcher in the Rye',
  'Carter': 'Harry Potter',
  'Jillian': 'The Grapes of Wrath',
  'Emilia': 'Treasure Island'
}
```

To access the values of these keys, we can do the same (use the string version of the key)

```ruby
high_school_students['Emilia']
# => 'Treasure Island'
```

Arrays and hashes are very valuable data structures that we use as programmers, to create, store and manipulate large data sets. This is but a simple introduction into how they can be used and accessed in Ruby.