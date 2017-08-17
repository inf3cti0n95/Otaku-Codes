---
layout: post
title:  "Summer Coding with Rocket.Chat - #1 | My Very First NPM Package"
date:   2017-07-01 16:00:00 +0530
categories: [Rocket-Chat, Summer-of-Code]
hero_image: /assets/images/rcsoc.png
excerpt: "Summer Coding with Rocket.Chat- #1 | My Very First NPM Package"
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

Everything was going well (Atleast that is what I thought at that time, I didn't know what storm was brewing out there.)

I thought, how hard could it be to build a Chat Application. I went at it, initializing a pretty React App Starter of my own (I have a weird OCD of making things from scratch, that way I always know what is going on, with every line of code written). Finished this task of stater app easily, A piece of cake, then there was this next Card on trello board saying ***Implementation of Interface to Rocket.Chat's Realtime API*** for interactions with the Rocket.Chat's Server. I thought, "How hard Could it be?"

But (there's always a but ), When I saw the list of methods and responses and subscriptions and events, I knew it isn't going to be a piece of cake.

- Handling the Asynchronous Behaviour of Websockets.
- Building a Redux Middleware, that would handle the State of the App.
- Building, Somekind of wrapper to Abstract the RealTime API.
- and Doing all the stuff simultaneously.

That is when Karl told me to checkout, ***Rx (Reactive Extensions)*** for the Implementation. I did, and I was baffled 🌀🌀🌀 by the long chain of operators one after another, and the All new Reactive Programming Paradigm. 

Watched some online conferences and I was surprised how little code in Rx could do stuff that required 100s of LOC in Callbacks.

<div>
    <blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">Seeing <a href="https://twitter.com/hashtag/RxJS?src=hash">#RxJS</a> for the first time! and I am Awed <a href="https://twitter.com/BenLesh">@BenLesh</a> <a href="https://twitter.com/_jayphelps">@_jayphelps</a> <a href="https://t.co/Z0CQ8y69IE">pic.twitter.com/Z0CQ8y69IE</a></p>&mdash; Viraj Trivedi (@inf3cti0n95) <a href="https://twitter.com/inf3cti0n95/status/874131779862614017">June 12, 2017</a></blockquote>
    <script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>
</div>

#### What is Rx ?

>
> Think of RxJS as Lodash for events.
> --<cite>[RxJS Documentation](http://reactivex.io/rxjs/manual/overview.html)</cite>

ReactiveX combines the Observer pattern with the Iterator pattern and functional programming with collections to fill the need for an ideal way of managing sequences of events. 

Not getting what I said, checkout the documentation of RxJS where it explains [Observables](http://reactivex.io/rxjs/manual/overview.html#observable)

Rx sure has some learning curve but once you get your hands dirty with some Observables, You'll love it.

#### Rx + Redux + React 😍😍😍

RxJS is pretty much the only thing needed for handling everthing, Angular 2 + has RxJS built in for everything, That's when I thought there must be something to couple Rx and React, and found out [***Redux Observables***](https://redux-observable.js.org/) ( the Three Ducks 🦆🦆🦆 ) Observables as guys from Rx like to call it.


***Redux Observables*** is a [Redux](http://redux.js.org/) middleware that solves managing states and the async behaviours with so called [***"Epics"***](https://redux-observable.js.org/docs/basics/Epics.html), an Epic is Stream of redux actions which returns a stream of actions. That sounds familiar, right ?. Yes, an Epic is an Observable of redux actions.

```
const actionEpic = (action$) => newAction$;

```

Redux-Observable makes handling states on the async actions slick !!!

This is what I needed for a chat application like Rocket.Chat which has a lot of complex async actions, and handling state of the app on the basis of those actions is very difficult task.

After understanding, bits of RxJS and Redux Observables, I made a wrapper to handle the Methods and Subscriptions of the Rocket.Chat's Real Time API, that's when I with help of mentors at Rocket.Chat ([karl.prieb](https://github.com/karlprieb) and [ggazzo](https://github.com/ggazzo)) published an npm package called [***Rocket.Chat.RealTime.API.RxJS***](https://www.npmjs.com/package/rocket.chat.realtime.api.rxjs)
