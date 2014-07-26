##Enumerable#group_by

In this post, I'll discuss the group_by method of the Enumerable Ruby class.

The Ruby group_by method belongs to the Enumerable class. This method allows one to create collections of elements based on criteria. The method takes an input array and a block of code an it outputs a hash. The syntax are as follows:

```ruby
# array.group_by{ |obj| block }

# returns a hash
```

Here is a simple example that uses group_by to group a list of students by the first letter of their first names:

```ruby
students = ["Jennifer Miller", "Jason Miller", "Barack Obama", "Hillary Clinton"]

grouped_hash = students.group_by { |name| name[0]}

print grouped_hash

# returns : {
# "J"=>["Jennifer Miller", "Jason Miller"], 
# "B"=>["Barack Obama"], 
# "H"=>["Hillary Clinton"]
# }
```

###A More Complex Example

The previous example isn't particularly useful. But the group_by method could be extended to accomplish much more complex tasks. Take for example a university that wants to assign unique email addresses to each of it's 10,000 students. The basic template for a student's email address is the first letter of his first name concatenated with the first four letters of his last name. However, some students will have identical addresses if the name creation ends there. Taking for example the 'students' array above, group_by could be used to group together all students with email address beginning jmill. Then, each student in the array corresponding to key 'jmill' in the group_by hash would have a unique number appended to 'jmill'. This would ensure a unique email address for each student.