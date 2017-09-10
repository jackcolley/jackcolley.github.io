---
layout: post
title: "How Instagram doubled its iOS app ratings in a week and how you can too"
author: "Jack"
---

I’m sure you’ve already either seen this story posted around the web or you’ve heard someone talking about it. How Instagram doubled their iOS app ratings in a week with more than 2 million reviews given. Just in case you haven’t read the story or want to read it again. You can read it [here](https://medium.com/huggingface/instagram-doubled-its-ios-reviews-in-a-week-thanks-to-this-new-in-app-review-popup-52333d4f4ce6).

# The Problem

Prior to iOS 10.3 if you wanted to ask your user to submit a review for your app. You had to either place a UI element somewhere within your app. Or an alternative was to present a UIAlertController asking the user to leave a review. Either way, this meant that you had to interrupt the user from using your app to kick the. Out to the App Store.

For the user, this felt like a lot of work and probably 6 times out of 10 I would either press ‘later” if the option was given of simply decline. 

# The Solution

Enter iOS 10.3. One of the major changes that Apple made in iOS 10.3 was the addition of a review API to StoreKit. This means that if our app is running on a device that has either iOS 10.3 or newer, we can ask for a review and the user can submit a review without having to leave your app. Sound like music to your ears? Well it’s definitely a start. It does come with a few kneed to knows’.

Firstly, when you request for StoreKit to show the review prompt, it’s not always going to show it instantly. Apple added an algorithm to try and automatically detect when its most appropriate for the prompt to be shown. So if you linked up the request to a button touch event, then the prompt might not always show instantly. Causing the user to think your app isn’t working.

One other thing to remember is that when developing your app, the prompt will show every time you request it. This is so that you can test any logic around making the request reliably. Finally, before we look at how to implement the new review API, my final bit of advice is to make sure that you wait until your users have used your app a few times before you request a review. If you request a review on the first app launch, users aren’t going to have much to say or base their review off and would likely not leave a review.

# The implementation

1. First we need to import StoreKit

{% highlight swift %}

import StoreKit

{% endhighlight %}

2. Now all we need to do is request the review

{% highlight swift %}

SKStoreReviewController.requestReview()

{% endhighlight %}

If your app supports older versions of iOS then it’s easy to link this in with your existing review logic. Simply add the following:

{% highlight swift %}

if #available(iOS 10.3, *) {

    SKStoreReviewController.requestReview()
    
} else {

    // Fallback to previous review logic
    
}

{% endhighlight %}

Hopefully you’ve got enough there to implement the new review prompt into your apps. If you would like to see some more examples of how this could be used, or the logic I use to check if I should request a review, then drop me a tweet @jackcolley and I’ll get back to you