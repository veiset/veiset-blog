CoffeeW8
========

CoffeeW8, a web-interface for the coffee machine located at the reading area of the 
Institute of Informatics, at the University of Bergen. 
You can find the [source code](https://github.com/veiset/CoffeeW8) hosted
publicly on github. Project by [@veiset](https://github.com/veiset) and
[@HaskellElephant](https://github.com/HaskellElephant).

Introduction
------------

Are you tired of walking to the coffee maker just to discover that there is no coffee 
left, or that the coffee that is left is cold? We, the CoffeeW8 team, are trying to 
solve precisely that problem. No more walking without reason, no more disappointment, 
no more cold  coffee. With this brand new revolutionary, patented, in-the-cloud, open-source,
web 2.0, buzzword, ajax, json, and practical solution you will always be the
one who is there when the coffee is ready, and only be there when the coffee is 
ready. This way you can stay sharp and focus on doing important and fun stuff: coding.

![Coffee and Programming](https://raw.github.com/veiset/veiset-blog/master/static/img/coffeeW8-project/coffee_and_programming.png) 


Problem description
-------------------

We have our top scientists working twenty-four seven at solving the problem at
hand; Is warm coffee available at the reading area / study hall of the institute
of informatics? 

![Coffee pot](https://raw.github.com/veiset/veiset-blog/master/static/img/coffeeW8-project/coffee_machine.png)

It is very important to ask the right questions:

+ Is there any coffee ready to be consumed by thirsty students?  
+ Is the coffee warm?
+ How many minutes do I have before it is all gone?

If and only if we are able to answers the questions with: 
"yes", "yes", "minutes are equal to, or less than the time it would take to arrive at the coffee maker"
are we interested in the current batch of coffee. We might then, after careful
evaluation consider walking to the coffee maker and grab a cup of coffee.


Our goal 
--------
Our goal is simple: Coffee awareness. People need to know when hot coffee available.
Hot, free and delicious coffee turns grumpy informatics students into happy people 
with the ability to communicate and socialize with their fellow students. Joy!

![Happy drinkers](https://raw.github.com/veiset/veiset-blog/master/static/img/coffeeW8-project/happy_drinkers.png)


The technology behind
---------------------

Electronics -> Phidget -> Java -> Haskell -> MongoDB -> Ruby -> Javascript

Worklog - Prototyping
---------------------

We want to weight the coffee machine and figuring out how heavy it is, and thus if
there is any liquid motivation (coffee) available for consumption. 

What to do? Disassemble a kitchen weight, of course. Brilliant idea. I am quite sure we just voided the warranty.


### Prototype 1 

Our first working prototype, connected to the PC through a Phidget interface.
It was not very good at doing measurements. It was giving us the value 605 
when we did not applying force to the load-cell, 605 if we were, and 606 if
we applied a lot of force.

![Prototype1](https://raw.github.com/veiset/veiset-blog/master/static/img/coffeeW8-project/prototype1.png)

### Prototype 2

We had no clue what we were doing, so we had to hire in some help to design 
the circuit for us. A few email later, and this was the result:

![Expertise](https://raw.github.com/veiset/CoffeeW8/master/docs/veiecelle-diff-amp.gif)

After following the schematics, stuff started to make sense and work. 
Our sencond prototype was working, and giving the desired result for one
connected load cell. 

![Prototype2](https://raw.github.com/veiset/veiset-blog/master/static/img/coffeeW8-project/prototype2.png)

Cute cats and actual results

![Cute cats and results](https://raw.github.com/veiset/veiset-blog/master/static/img/coffeeW8-project/values_prototype2_screenshot.png)



Deployment
----------

Location is key. Figuring out the optimal area for deployment is very
important as informatics students tend to break anything they can get
their hands on. We should hide it so that other students will not be
tempted to break it.

![Location is Key](https://lh5.googleusercontent.com/-VJWDo9LpVQg/UHGUm-76L6I/AAAAAAAADLs/1vceDCwSf4g/s972/IMG_20121007_164024.jpg)


In action
---------


Contributors
------------
+ [Vegard Veiset](https://github.com/veiset) - programming, design, electronics
+ [Eivind Jahren](https://github.com/HaskellElephant) - programming, design, electronics


Disclaimer
----------
We, the CoffeeW8 team, is not to be held responsible if the CoffeeW8 achieves 
sentience and start committing heinous crimes against such as, but not limited to:
attaching lazers to sharks, creating an army of minion robots, and/or serving cold coffee. 
The CoffeeW8 team does not endorse any attempts to summon Cthulu by such ancient rituals as
brewing coffee with human blood, or similar misuse of the technology.
