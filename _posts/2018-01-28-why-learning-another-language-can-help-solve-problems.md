---
layout: post
title: "Why Learning Another Language Can Help Solve Problems "
author: "Jack"
---

For those of you that don't know me that well. We need to start this post with a bit of background. Firstly, I'm a lead mobile developer focussing mainly on iOS for a digital agency in the north east of England. I also tinker with Android when needed. 

A vast majority of my day is spent writing Swift. However, it hasn't always been that way. When I was first hired at [Netsells](https://netsells.co.uk) I started as a backend developer writing PHP using [Laravel](https://laravel.com). What I have found over the last few years is that having knowledge of PHP and using Laravel for side projects has shown me a lot of good ways to both structure my code and document that code.

One of the things that Laravel is known for (apart from been generally amazing) is the way the code is documented and how easy it is to read / understand what is going on. As you make the transition from been a junior developer to a mid level developer and then finally a senior developer, you start to care a lot more about how your code looks as well as how it functions. 

A few generic examples of this that can be applied to any language are:

* Massive classes that don't have a single responsibility and instead do everything
* The same block of code in multiple places rather than extracted out into a function / method

If you're even a bit familar with iOS development, you'll know the temptation to just throw all of your logic into a View Controller. Its easy to do and it works. However, that might be fine for really small projects. But as soon as the app you're working on starts to grow or you come back to it in 6 months. You will really struggle to clearly see what is going on. It also makes testing really hard.

One approach I have found that works for me is to stick everything in the View Controller while you're developing a feature. Then once you have it working, extract it out either into another class or a set of functions if its not something that is suitable for a class. 

Knowing PHP and looking at the Laravel framework, its easy to take some hints from it to structure your other projects. A really simple example of this is:

* Keep your model files in a models folder
* Keep your View Controllers in a Controllers folder
* Keep your services in a Services folder

If you're going to use a set of functions throughout multiple view controllers, subclass UIViewController and then extend that subclass in all of your other View Controllers. 

That is a very iOS focussed example, but it won't be hard to translate over to another language. If I'm ever stuck and aren't quite sure how to structure / architect something in one of my projects. I look at how the same problem has been solved in other languages. I guess its the same as learning new techniques by reading other peoples source code. 


