CoffeeW8
========

CoffeeW8, a web-interface for the coffee machine located at the reading area of the 
Institute of Informatics, at the University of Bergen. 
You can find the [source code](https://github.com/veiset/CoffeeW8) hosted
publicly on github. Project by [@veiset](https://github.com/veiset) and
[@HaskellElephant](https://github.com/HaskellElephant).
You can find the [current state off coffee available online](http://coffee.veiset.org/).

Index
-----
* [Introduction](#introduction)
* [Problem Description](#problem-description)
* [Our Goal](#our-goal)
* [Deployment](#deployment)
* [CoffeeW8 in action](#coffeew8-in-action)
* [The Technology Behind](#the-technology-behind)
* [Contributors](#contributors)
* [Disclaimer](#disclaimer)

* [Worklog](#worklog)


Introduction
------------

Are you tired of walking to the coffee maker just to discover that there is no coffee 
left, or that the coffee that is left is cold? We, the CoffeeW8 team, are trying to 
solve precisely that problem. No more walking without reason, no more disappointment, 
no more cold coffee. With this brand new revolutionary, patented, in-the-cloud, open-source,
web 2.0, buzzword, ajax, json, and practical solution you will always be the
one who is there when the coffee is ready, and only be there when the coffee is 
ready. This way you can stay sharp and focus on doing important and fun stuff: coding.

To satisfy our customers (i.e our selves) we are using a [Phidget Interfacekit
8/8/8](http://www.phidgets.com/products.php?category=0&product_id=1018_2) connected to
a [Raspberry Pi](http://www.raspberrypi.org/) to provide precise and accurate measurements of 
the actual weight of the coffee maker.
![Baking Pie](https://raw.github.com/veiset/veiset-blog/master/static/img/coffeeW8-project/compiling_phidget.png)


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

Deployment
----------

Location is key. Figuring out the optimal area for deployment is very
important as informatics students tend to break anything they can get
their hands on. We should hide it so that other students will not be
tempted to break it.

![Deployment Box](https://raw.github.com/veiset/veiset-blog/master/static/img/coffeeW8-project/box.png)
![Location](https://raw.github.com/veiset/veiset-blog/master/static/img/coffeeW8-project/deployed.png)

CoffeeW8 in action
------------------
[CoffeeW8 in action](http://coffee.veiset.org/)
![CoffeeW8 CoffeMaker graph](https://raw.github.com/veiset/veiset-blog/master/static/img/coffeeW8-project/test_first_real_data.png)

The Technology Behind
---------------------

Electronics -> Phidget -> Java -> Haskell -> MongoDB -> Ruby -> Javascript

List of requirements needed to replicate the implementation:
 + Phidget Interfacekit 8/8/8
 + Phidget Weight Sensor
 + Device capable of
   > using the Phidget Interfacekit
   > running Java 
   > hosting a simple java-based web API
 + A server with
   > MongoDB (Database)
   > Sinatra (Webserver)
   > Haskell (Used to fetch data from client)
 + Coffee Maker
 + Duct tape (no, I am not joking)

Contributors
------------

+ [Vegard Veiset](https://github.com/veiset) - programming (java, ruby, javascript), design, electronics, infrastructure, installation 
+ [Eivind Jahren](https://github.com/HaskellElephant) - programming (haskell), design, electronics, DBO (mongoDB)
+ [Alexander Hoem Rosbach](https://github.com/mapster) - axiom testing (java), code review

Disclaimer
----------
We, the CoffeeW8 team, is not to be held responsible if the CoffeeW8 achieves 
sentience and start committing heinous crimes against humanity such as, but not limited to:
attaching lazers to sharks, creating an army of minion robots, and/or serving cold coffee. 
The CoffeeW8 team does not endorse any attempts to summon Cthulu by such ancient rituals as
brewing coffee with human blood, or similar misuse of the technology.



Worklog
-------

Now, we spent hours discussing both the name and how to solve the problem. But after some thought
we figured out that weighting the coffee machine and figuring out how heavy it is would give us a
good indication on if there is any liquid motivation (coffee) available for consumption.
That ended up being our very basic idea on how to solve the problem, and hence the name 'CoffeeW8' -> (CoffeeWeight, CoffeeWait). 
What to do? Disassemble a kitchen weight and connect it to a computer, of course. Brilliant idea. 

[Full pictures worklog from prototype 1 and 2](https://github.com/veiset/CoffeeW8/wiki/worklog).

### Prototype 1 - What are we doing?

Our first working prototype, connected to the PC through a Phidget interface.
It was not very good at doing measurements. It was giving us the value 605 
when we did not applying force to the load-cell, 605 if we were, and 606 if
we applied a lot of force.

![Prototype1](https://raw.github.com/veiset/veiset-blog/master/static/img/coffeeW8-project/prototype1.png)


### Prototype 2 - Hope!

We had no clue what we were doing, so we had to hire in some help to design 
the circuit for us. A few email later, and this was the result:

![Expertise](https://raw.github.com/veiset/CoffeeW8/master/docs/veiecelle-diff-amp.gif)

After following the schematics, stuff started to make sense and work. 
Our second prototype was working, and giving the desired result for one
connected load cell. 

![Prototype2](https://raw.github.com/veiset/veiset-blog/master/static/img/coffeeW8-project/prototype2.png)

Stuff were looking really good and we were full of joy and hope. We connected the 
four load-cells in series and put them together in the original kitchen weight chassis.
We then calibrated the circuit and started taking measurements. 
Low-value 80, high-value 500. Awesome! The value when not putting pressure on 
the weight was on a stable 80... 81, 90? 85? What. After some investigation
we concluded with the sad truth: The USB output voltage from the Phidget
analog output was not 100.0000% stable, causing our fragile circuit to
behave strangely. 

### Prototype 3 - Fuck it.

The easy way out:
![Phidget pre-made load-cell](http://www.phidgets.com/images/3100_0_Functional_Web.jpg)

Prototype in action, with results good enough to differentiate between coffee 
and no coffee, with around 50 steps (~2kg/~50 = 40g).


![Prototype 3 in action](https://lh6.googleusercontent.com/-axEyCwswjT4/ULI6cbKDvPI/AAAAAAAAElM/_OMY3CEicY4/s960/IMG_20121125_163216.jpg)


