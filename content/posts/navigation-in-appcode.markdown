---
title: "Navigation in AppCode (EAP)"
date: 2013-01-21T21:32:00+02:00
draft: false
---

![AppCode Logo](http://bonski-blog.s3.amazonaws.com/appcode-logo.png)

## Xcode

My first meeting with Xcode, which was version 3 something, did not impress me. A couple of years later, Xcode 4 was presented at WWDC 2010, and while my first impression was positive, this feeling was short lived. It crashed continually, and while it looked good, which it still does, the editing experience and feature set were far below my expectations for a modern IDE. 


## JetBrains


I know that more than 10 years experience with IDE's from JetBrains, such as IntelliJ and RubyMine, does something with your expectations of what an IDE should provide. So, when you start using an another IDE, and you don't find these features, it's easy to render it useless. But for Xcode, it was not like that. I __really__ wanted to like it. I used Xcode for over two years with my teeth clenched, (almost) without any complaints, because what other Objective-C IDE's existed?

As you maybe have guessed, I used to be a Java developer (and still am if I really have to). One of the podcast`s I used to listen to then was "The Java Posse." In October 2009 the posse had an interview with a couple of guys from JetBrains, Roman Strobl and Dmitry Jemerov, and in this talk Roman mentioned that they where working on an IDE for Objective-C. Before this I used to fantasize about a "IntelliJ for Objective-C," but I never expected it to happen, and now they actually said that they were working on it. Wow! 

Time went by, and in October 2011, I was working on a Rails project, and didn't actually code that much in Objective-C, JetBrains released their first AppCode beta. 


A couple of months later, I was hired to to work on a iOS project. I did use Xcode the first couple of weeks since the other team members used Xcode, but the frustration over Xcode and all its crashes made me do the switch. I have used AppCode everyday since then, and I have never looked back.

## Why the love?

When fellow developers ask me: "what is so great about AppCode" (and the other JetBrains IDE's), it's not easy to give one simple answer. It's not that there is one or two major features that makes it great. It is the collection of simple solutions to everyday tasks, such as quick and effective navigation in source and project, the VCS integration, the power of the editor, the refactoring support (including the speed and correctness of the refactorings), code generation, local history, completions, templates etc. 

## Key maps
AppCode support a few different key mappings, such as: Default, IntelliJ IDEA, Xcode, Visual Studio, ReSharper and Emacs. 
The video and screenshots in this blog post are taken from the Early Access Program for AppCode 2.0. This program allows developers to test and participate in discussions about the next release. I have more than once reported a bug, which has been fixed only a couple of days later. My experience with the EAP versions, is that they are quite stable, and I have had much fewer bugs and crashes using the EAP's than Xcode. 


## Navigate to class

When you want to go to a class, you use the shortcut __&#x2318;O__ to open the "Navigate to class" dialog. The video below shows different ways to use this shortcut to open a class.

{{< vimeo 236651730 >}}

## Navigate to file

What if you want to navigate to a file other than a class, such as an image file or a plist?
Open the "Navigate to file" dialog by typing __&#x21E7;&#x2318;O__

![Goto File](http://bonski-blog.s3.amazonaws.com/goto-file.png)

As you can see from the screenshot above, only so much of the filename is needed to identify the file, and any fragments of the filename can be used. This does also apply for "Navigate to class" and "Navigate to symbol" as described below. 

## Navigate to symbol

I know there is a method somewhere in the code called "initializeBadge, but I can't remember in which class. The text search in AppCode is really fast, but here an even faster solution is to use.
Open the "Navigate to symbol" dialog by typing __&#x2325;&#x2318;O__ and enter the name of the symbol you are looking for. Since'm lazy, I only type "initBad".

![Goto Symbol](http://bonski-blog.s3.amazonaws.com/goto-symbol.png)

If you have opened "Navigate to Class," but you really wanted to "Navigate to File", you don't have to close the dialog, and then type the wanted shortcut again. You can toggle between the different dialogs, and text that you have entered is restored between the dialogs. The last text you typed is also remembered to the next time you use one of these navigation dialogs. I promise, you'll going to use them a lot.


##Recently Changed Files
The shortcuts I use the most must to be __&#x21E7;&#x2318;E__ "View Recently Changed Files" and __&#x2318;E__ "View Recent Files". 
Usually, I edit a small set of related files, and are going back and forth between these files.

## Navigation in code
When I code, I often want to navigate to the definition or declaration of a method, property, variable, and so on. The shortcuts I use to do this are "Goto Declaration" __&#x2318;B__ and "Goto Definition"  __&#x2325;&#x2318;B__

If there are multiple definitions, such as for NSString, a list of the different definitions is shown. 

![Goto Definition](http://bonski-blog.s3.amazonaws.com/goto-definition.png)

You can also toggle between related files __&#8963;&#x2318;&#8593;__. Unfortunately, this does not include going to the corresponding unit tests as of now, but the 2.0 EAP roadmap contains the following bullet point: "Navigation between test and code". 

## What's next?
The next post about AppCode is about refactoring... 
