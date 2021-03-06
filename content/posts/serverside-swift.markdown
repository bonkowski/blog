---
title: "Serverside Swift"
date: 2019-07-03T17:54:10+02:00
draft: false
categories: [programming]
tags: [Swift, Serverside]
---

I came over this [article](https://www.raywenderlich.com/3858252-how-to-think-in-server-side-swift) today, which got my attention since I spent a few hours yesterday evening to see what options we currently have for Swift on the backend. I like the idea since Swift is a very nice programming language.  

The project I wanted to use to explore Swift on the server-side is to replicate the functionality we already got in a "mock-server" written in Go. This server simulates most of the features that our production servers provide, which helps us when developing our iOS and Android apps.

I'm on my 24th year as a professional developer, where I mainly have worked on different backends using JVM based languages such as Java, and later Clojure and Kotlin. In the Java days, we often had to use big frameworks such as the Spring Framework, which I never want to do again. I have also worked with a couple of Ruby on Rails projects, and while it was fun and productive, especially in the beginning, is also something I don't want to go back to.

Since 2015 all the JVM based backend projects I have worked on have used Clojure or Kotlin. In Clojure, we don't use frameworks (I don't think it even exists), but we prefer small and focused libraries that do one thing only but does it well. 

At my last backend project, we decided to use Kotlin, we as a team also agreed to go the "Clojure Way" and select the best libraries for the different tasks and problems we needed to solve instead of choosing a big framework that dictates how to design and implement the project. 

What we ended up with was a simple micro web framework called [Jooby](https://jooby.org), which we only use to handle requests and serve content. It would take a minimum of effort to replace Jooby with another similar library. For the rest of the application functionality, we selected a few libraries such as [Kotlin Query](https://github.com/seratch/kotliquery) for accessing and using the database and [Kotson](https://github.com/SalomonBrys/Kotson) for JSON, and of course, a few more. The most important library (or collection of libraries) we decided to use was [Arrow](https://arrow-kt.io) since we wanted to write our code in a functional style.

The project was a great success, it's easy to work with, very testable, and the codebase is surprisingly small. Many developers in the organization I'm hired to work for have shown a great interest in how we designed and built the system.

To create my replica of the beforementioned "mock-server" in Swift, I looked around to see what options that existed, and I decided to play a little with [Vapor](https://vapor.codes). I also had a look at [Kitura](https://www.kitura.io). Unfortunately, almost immediately, Vapor gave me a feeling of wearing a straightjacket, and the simple things I wanted to start with was not as simple as I hoped it would be. What I wanted was something like a Swift version of [Sinatra](http://sinatrarb.com).

After a few more Google searches, I decided to try [Perfect](https://perfect.org), which looks a little more like what I was looking for. I have only played around with this framework/library for a couple of hours, but then I had got a working spike of a feature. 

To be fair, I also got a working spike using Vapor, but I got the feeling that I had to fight the framework, instead of getting the help I wanted from it. 

It's too early to come with a conclusion based on this rather simple feature I implemented, and it's way too early to say if Perfect is the perfect "framework" for me (nothing is). What I can say is that Perfect seems to give more flexibility than Vapor and Kitura if you want to decide for yourself how to write your application. 