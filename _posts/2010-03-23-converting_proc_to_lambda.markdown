---
layout:default
title: Converting a Proc to a Lambda
---
How to convert a ruby Proc to a Lambda. 

There is alot of posts around the net pointing to differences between Proc.new, lambda, and blocks. 
However I have not seen any that relly point out how easy it is to convert from one to the other. 


{% highlight ruby %}
    def foo(&blk)
	   
	   #get the "block" from the proc and create a new lambda
	   l = lambda &blk
	   
	   #call it, and  save return value
       retval  = l.call :one, :two
          
       puts "this *get* executed"
            
       retval
    end
              
    puts "Call to foo returned: " << foo {|a,b| return a.to_s+b.to_s}
	
{% endhighlight %}
