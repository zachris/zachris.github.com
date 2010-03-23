---
layout:default
title: Converting a Proc to a Lambda
---
How to convert a ruby Proc to a Lambda.

{% highlight ruby %}

    def foo(&blk)
       l = lambda &blk
       retval  = l.call :one, :two
          
       puts "this gets executed"
            
       retval
    end
              
              
    puts "Call to foo returned: " << foo {|a,b| return a.to_s+b.to_s}
	
	{% endhighlight %}
