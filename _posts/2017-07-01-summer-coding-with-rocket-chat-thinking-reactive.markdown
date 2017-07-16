---
layout: post
title:  "Summer Coding with Rocket.Chat - #1 | Thinking Reactive"
date:   2017-07-01 16:00:00 +0530
categories: [Rocket-Chat, Summer-of-Code]
hero_image: /assets/images/rcsoc.png
excerpt: "Summer Coding with Rocket.Chat- #1 | Thinking Reactive"
---

>#### TL;DR
>
>Coding begins, How Do I handle this much of asynchronicity 🌀🌀🌀, **Functional Reactive Programming** to the Rescue.
>

![Summer of Code with Rocket Chat](/assets/images/rcsoc.png)

>
>
>**Between stimulus and response there is a space. In that space is our power to choose our response. In our response lies our growth and our freedom.**
> --<cite>Viktor E. Frankl</cite>
>

As I mentioned, Earlier in June, I got into Rocket.Chat after [this turnaround]() and started laying out the plans for coding the React App for Rocket.Chat's Progressive Web App Client with my Mentors [Karl Prieb]() and [Guilhermme Gazzo]().

Everything was going well (Atleast that is what I thought at that time, I didn't know what storm was brewing out there.) I thought, how hard could it be to build a Chat Application. I went all out for the first week, initializing the a pretty React App Starter of my own (I love making things from scratch, that way I always know what is going on, with every line of code written). Finished this task of stater app easily, A piece of cake, then there was this next Card on trello board saying ***Implementation of Interface to Rocket.Chat's Realtime API*** for interactions with the Rocket.Chat's Server. I went onto the docs, reading the first line saying "It all based on WebSockets", I was happy, I had worked on some pretty websocket things earlier, and then again I thought ***"Its going to be a piece of cake"***.

But (there's always a but ), When I saw the list of methods and responses and subscriptions and events, I realized that it was not going to be a piece of cake. I discussed with Karl and thought about some of the features for Implementation.

- Building a Redux Middleware, that would handle the API.
- Building, Somekind of wrapper to Abstract the RealTime API.
- Handling the Asynchronous Behaviour of Websockets.


That is when Karl, told me to checkout, ***Rx (Reactive Extensions)*** for the Implementation. I did, and I was baffeled 🌀🌀🌀 by the long chain of operators one after another, the Marble Charts and the All new Reactive Programming Paradigm. I watched some online conferences and I was surprised how little code in Rx could do stuff that required 100s of LOC in Callbacks. It was like I hit a gold mine. 

<div>
    <blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">Seeing <a href="https://twitter.com/hashtag/RxJS?src=hash">#RxJS</a> for the first time! and I am Awed <a href="https://twitter.com/BenLesh">@BenLesh</a> <a href="https://twitter.com/_jayphelps">@_jayphelps</a> <a href="https://t.co/Z0CQ8y69IE">pic.twitter.com/Z0CQ8y69IE</a></p>&mdash; Viraj Trivedi (@inf3cti0n95) <a href="https://twitter.com/inf3cti0n95/status/874131779862614017">June 12, 2017</a></blockquote>
    <script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>
</div>

Rx sure had some learning curve but once you get your hands dirty with some Observables, You'll love it.

Enough of the Lousy talk, Now Let's talk about this Gold Mine of Rx.

#### What is Rx ?

As described in docs of RxJS

>
> Think of RxJS as Lodash for events.
>

ReactiveX combines the Observer pattern with the Iterator pattern and functional programming with collections to fill the need for an ideal way of managing sequences of events.

In other terms, if you have ever used iterator, they pull the value from the collection, where as the observable pushes value to the subscriber. Thus, you can think of it as Iterator turned inside out. Not getting what I said, checkout the documentation of RxJS where it explains [Observables](http://reactivex.io/rxjs/manual/overview.html#observable)

Essentially, Rx is made up of things such as 

- Observable: represents the idea of an invokable collection of future values or events.
- Observer: is a collection of callbacks that knows how to listen to values delivered by the Observable.
- Subscription: represents the execution of an Observable, is primarily useful for cancelling the execution.
- Operators: are pure functions that enable a functional programming style of dealing with collections with operations like map, filter, concat, flatMap, etc.
- Subject: is the equivalent to an EventEmitter, and the only way of multicasting a value or event to multiple Observers.
- Schedulers: are centralized dispatchers to control concurrency, allowing us to coordinate when computation happens on e.g. setTimeout or requestAnimationFrame or others.