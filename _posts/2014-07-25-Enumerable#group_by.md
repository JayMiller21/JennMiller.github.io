---
layout: post
title:  "Enumerable#group_by"
date:   2014-07-25 11:53:03
categories: technical
comments: true
---


The Ruby group_by method belongs to the Enumerable class. This method allows one to create collections of elements based on criteria. The method takes an input array and a block of code an it outputs a hash. The syntax are as follows:

{% highlight ruby linenos %}
# array.group_by{ |obj| block }

# returns a hash
{% endhighlight %}

Here is a simple example that uses group_by to group a list of students by the first letter of their first names:

{% highlight ruby linenos %}
students = ["Jennifer Miller", "Jason Miller", "Barack Obama", "Hillary Clinton"]

grouped_hash = students.group_by { |name| name[0]}

print grouped_hash

# returns : {
# "J"=>["Jennifer Miller", "Jason Miller"], 
# "B"=>["Barack Obama"], 
# "H"=>["Hillary Clinton"]
# }
{% endhighlight %}

### A More Complex Example

The previous example isn't particularly useful. But the group_by method could be extended to accomplish much more complex tasks. Take for example a university that wants to assign unique email addresses to each of it's 10,000 students. The basic template for a student's email address is the first letter of his first name concatenated with the first four letters of his last name. However, some students will have identical addresses if the name creation ends there. Taking for example the 'students' array above, group_by could be used to group together all students with email address beginning jmill. Then, each student in the array corresponding to key 'jmill' in the group_by hash would have a unique number appended to 'jmill'. This would ensure a unique email address for each student.

{% if page.comments %}
<div id="disqus_thread"></div>
<script type="text/javascript">
    /* * * CONFIGURATION VARIABLES * * */
    var disqus_shortname = 'techsplore';
    
    /* * * DON'T EDIT BELOW THIS LINE * * */
    (function() {
        var dsq = document.createElement('script'); dsq.type = 'text/javascript'; dsq.async = true;
        dsq.src = '//' + disqus_shortname + '.disqus.com/embed.js';
        (document.getElementsByTagName('head')[0] || document.getElementsByTagName('body')[0]).appendChild(dsq);
    })();
</script>
<noscript>Please enable JavaScript to view the <a href="https://disqus.com/?ref_noscript" rel="nofollow">comments powered by Disqus.</a></noscript>
{% endif %}