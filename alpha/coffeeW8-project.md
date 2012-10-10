CoffeeW8
========

Web-interface for the Coffee machine located at the reading area of the 
Institute of Informatics, at the University of Bergen.

Problem description
-------------------

We have our top scientists working twenty-four seven at solving the problem at
hand; Is warm coffee available at the reading area / study hall of the institute
of informatics? 

![Coffee pot](https://lh5.googleusercontent.com/-Aw_DG2tbNiA/UEdubrThDCI/AAAAAAAACa8/3l3VF2lgjoU/s1296/IMG_20120905_172201.jpg)


Our idea
--------

We want to weight the coffee machine and figuring out how heavy it is, and thus if
there is any liquid motivation (coffee) available for consumption. 

What to do? Disassemble a kitchen weight, of course. Brilliant idea. 
I am quite sure we just voided the warranty.
![Weight](https://lh4.googleusercontent.com/-2newWaUs4z0/UEdzPrPu7vI/AAAAAAAACcI/gCpc-Pmcq94/s1296/IMG_20120905_174252.jpg)


The technology behind
---------------------

Electronics -> Phidget -> Java -> Haskell -> MongoDB -> Ruby -> Javascript

Progression
-----------

Our first working prototype, connected to the PC through a Phidget interface.
It was not very good at doing measurements. It was giving us the value 605 
when we did not applying force to the load-cell, 605 if we were, and 606 if
we applied a lot of force.
![First working prototype](https://lh6.googleusercontent.com/-huSx9e1iCB8/UEefUFDSqQI/AAAAAAAACiw/Dh6FEEvpVUI/s1296/IMG_20120905_205014.jpg)


We had no clue what we were doing, so we had to hire in some help to design 
the circuit for us.
![Expertise](https://raw.github.com/veiset/CoffeeW8/master/docs/veiecelle-diff-amp.gif)


After following the schematics, stuff started to make sense and work. 
Our sencond prototype was working, and giving the desired result for one
connected load cell. 
![On](https://lh3.googleusercontent.com/-D8EEIymfn8A/UHGMGbcWH9I/AAAAAAAADI4/Cco2YCkzaYU/s972/IMG_20121007_160356.jpg)

Cute cats and actual results
![Results](https://lh6.googleusercontent.com/-pIGLVbaNEbg/UHGPpFVk7aI/AAAAAAAADKE/5zcwDlEJZOQ/s972/IMG_20121007_161913.jpg)


Location is key. Figuring out the optimal area for deployment is very
important as informatics students tend to break anything they can get
their hands on. We should hide it so that other students will not be
tempted to break it.
![Location is Key](https://lh5.googleusercontent.com/-VJWDo9LpVQg/UHGUm-76L6I/AAAAAAAADLs/1vceDCwSf4g/s972/IMG_20121007_164024.jpg)


Deployment
----------


In action
---------



