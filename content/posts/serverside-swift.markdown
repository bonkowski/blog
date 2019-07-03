---
title: "Serverside Swift"
date: 2019-07-03T17:54:10+02:00
draft: false
categories: [programming]
tags: [Swift, Serverside]
---

I read this [article](https://www.raywenderlich.com/3858252-how-to-think-in-server-side-swift) today on raywenderlich.com, which was fun since I last night started playing around a little with Swift on the server-side. 

To be able to use Swift on the server-side appeals to me because I really like the language. As earlier mentioned, I started looking into this last night, wanting to replicate a "Mock" server written in Go, just for fun. This server makes it easy for us to simulate a real environment while developing our iOS and Android apps.

In most of my 34 years as a professional developer, I have mainly worked on the backend and primarily on JVM based languages such as Java, and later also Clojure and Kotlin. In the Java days, we often had to use the Spring Framework, which I never want to do again. I have also worked with a couple of Ruby on Rails apps, and while it was fun and productive, especially in the beginning, is also something I don't want to go back to.

My two latest backend projects used Clojure and Kotlin. In Clojure, we do not use frameworks (I don't think it even exists), but we prefer small and focused libraries that do one thing only but does it well. 

Having experienced how gratifying this is, on my next project where we used Kotlin, we wanted to do the same. We did not want to build on frameworks that tell us how to structure and write our code. 

What we ended up with was a simple micro web framework called Jooby, but only used it to serve content. It would take a minimum of effort to replace Jooby with another similar library. For the rest of the application functionality, we selected a few libraries such as [Kotlin Query](https://github.com/seratch/kotliquery) for accessing and using the database and [Kotson](https://github.com/SalomonBrys/Kotson) for JSON, and of course, a few more. The most important library (or collection of libraries) we selected to use was [Arrow](https://arrow-kt.io) since we wanted to write our code in a functional style.

The project was a great success, it's easy to work with, very testable, and the codebase is surprisingly small. Many other projects and developers in the organization I'm hired to work for have shown a great interest in how we built the system.

To create my replica of the beforementioned Mock server in Swift, I looked around to see what existed, and I decided to play a little with Vapor. Unfortunately, almost immediately, it gave me a feeling of wearing a straightjacket, and the simple things I wanted to start with was not as simple as I hoped it would be. What I wanted was something like a Swift version of Sinatra.

After a few more Google searches, I found [Perfect](https://perfect.org), which looks a little more like what I want. I have only played around with this framework/library for an hour or so, but then I had a working spike of what I wanted to do, which I had to fight Vapor to get working, after spending a lot more time than with Perfect. 

It's too early to say if Perfect is the perfect "framework" for me (nothing is perfect), but it seems to give more flexibility than Vapor or Kitura if you want to decide for yourself how to write your application. 


