---
title: "Refactoring in AppCode"
date: 2013-02-10T23:19:00+02:00
draft: false
---



AppCode offers a rich set of refactoring's, which is fast, safe, and easy to use. 

## Rename
Naming is surprisingly difficult. It's easy to get "paralyzed" if the perfect name of a class or method does not pops into place immediately. But hey, you can always rename it later!

The "Rename" refactoring in AppCode is triggered by the shortcut __&#x21E7;F6__. By using this, you can rename a file, class, method, property, ivar, local variable, and so on. In the file or project view, the shortcut triggers renaming a file or a class. 

![Rename](https://bonski-blog.s3.amazonaws.com/rename.png)

If you just are renaming a file (such as a plist or an image), AppCode will rename the file, and also change where it is referenced. If you are renaming a class, both the header, and the implementation of the class is renamed, and the references of the files in the project file. If you select __Rename__ when the cursor is on a class name used by the class, the selected class is renamed. 

If you triggers the rename from inside the source file, the name of the class, variable, and so on, is entering a "edit mode," almost like "Edit all in Scope," in Xcode. The difference is that while in Xcode you renamed only the names inside the current class, the renaming in AppCode is global. 

![Inline Rename](https://bonski-blog.s3.amazonaws.com/inline-rename.png)

In the example above, changing the name _KMRObjectViewLayout_ to something else,  will rename the _KMRObjectViewLayout_ class, it's containing file, and all the references to the class.

![Edit all in Scope](https://bonski-blog.s3.amazonaws.com/edit-all-in-scope.png)

Here is an example of how it looks like when you are renaming a method name. All instances in scope are selected and edited. 

![Rename class from file or project view](https://bonski-blog.s3.amazonaws.com/name-proposal.png)
In the next example, shown above, we want to rename an instance variable. AppCode gives us a few name proposals, based on the name of the variable, and its usage. (As you can see, contentWidth is suggested based on the method name)

## Change signature
I often begin with a method signature that after a while needs to be altered. This can be to include an additional argument, or maybe the argument is not needed anymore, or even the order of the arguments is not right. If the method is called from several places, this can be a time-consuming and error prone task. By using the __&#x2318;F6__, ___Change Signature___, this is done in a simple and safe way.

The video below shows how you can use the ___Change Signature___ refactoring.

{{< vimeo 236656940 >}}

As you can see, this is a really powerful feature, which I use a lot. You can also change the return type, and even convert a method to a function or a block, or vice versa.

## Convert 
Converting a method to a function or a block can also be done by using one of the ___Convert to___ menu items. In addition to these, you also have ___Convert to Property___ and ___Convert to Instance Variable___.

## Move

The ___Move___ refactoring allows you to move a property, ivar's and methods from one class to another. If the target class does not exist, you get a warning that tells you that. While this is correct, <s>I would expect AppCode to ask whether I want to create the non-existing class. There is a feature request for this already registered in the AppCode issue tracker, so I expect it to be in a [future build of the EAP](https://youtrack.jetbrains.com/issue/OC-6223).</s> 

__Update:__ [The "missing" feature is now fixed](https://youtrack.jetbrains.com/issue/OC-6223). 

This is one of the other great things about JetBrains. They respond to bug reports and feature requests almost immediately, and the Issue Tracker is publicly visible.


## Copy
When in the project browser, selecting a header, or an implementation file, or when inside one of these files, __F5__ will prompt you to enter the name of the new copy of the files, and where to copy them. While in the "To directory" input field __&#x2303;&#x2423;__ will provide path completion. When accepting, the class name inside the source files is changed as well.

![Copy a class](https://bonski-blog.s3.amazonaws.com/copy.png)

## Safe Delete
Before you delete a class or a file, you want to ensure that it's not used somewhere. ___Safe Delete___ does that for you, and warn you if this is the case. Besides search for usages, by default it also searches in comments and strings. The keyboard shortcut for this are __&#x2326;&#x2318;__

## Extract...

There are several Extract factoring's, and here is a short description of each:

#### Extract Variable
Let say that you have a hard coded value. You select the value, and type __&#x2325;&#x2318;V__. AppCode will declare a variable above where it's used, with the correct type, and the name of the new variable selected. To change the proposed name, just begin to type the name of the variable. If no value or expression is explicitly selected, AppCode gives you a suggestion of what to base the value of the introduced value from as shown in the example below:

![Select variable expression](https://bonski-blog.s3.amazonaws.com/select-variable-expression.png)

#### Extract Constant
This refactoring, __&#x2325;&#x2318;C__,  is similar to ___Extract Variable___, but this introduces a constant instead. If no actual value is selected, AppCode gives you an opportunity to select what the constant is based on from values and expressions in scope. When the constant is selected, AppCode asks for you if you would like to replace only this one, or all similar values found in the current file. 

#### Extract Parameter
If you are creating a variable inside a method, but you would like it to be passed as a parameter, ___Extract parameter___, __&#x2325;&#x2318; P__ is the refactoring you would like to use.

#### Extract Property
By using __&#x2325;&#x2318;E__ on a variable, AppCode shows a dialog where the declaration of the property is shown, togheter with a checkbox. If you check the checkbox, the property is generated in a private category. If not, the property is declared in the header. 

![Introduce property](https://bonski-blog.s3.amazonaws.com/introduce-property.png)

#### Extract Instance Variable
By using __&#x2325;&#x2318;I__ on a local variable, AppCode changes it into an ivar, but with the option to generate a property for the variable if the checkbox is selected. You can also select to declare the ivar in the interface (which you don't want to do).

#### Extract Define
__&#x2325;&#x2318;F__ extracts a macro from the selected value or expression 

#### Extract Typedef
As the name suggests, __&#x2325;&#x2318;F__ creates a typdef from the selected type. 

#### Extract Method	
This is one of the most my frequently used refactoring. Let say a method has too much responsibility, and you want to move some of the logic into a new method, Select the code you want to move, type __&#x2325;&#x2318;F__, and AppCode generates a new method for you, including necessary parameters.

![Extract method](https://bonski-blog.s3.amazonaws.com/extract_method.png)

As you can see from the screenshot above, it's quite similar to ___Change Signature___. The main difference is the Targets drop down. Depending on what you select in this drop down, the signature is declared in the header file, in a private category, or just in the implementation file.

#### Extract Block Parameter
By using Extract Block Parameter you select a chunk of code. A block declaration based on the selected code is created, and the signature of the method is changed to take a block of this type. Finally, the existing usages of this method are changed so that the extracted block is passed as a parameter. 

#### Extract Superclass
To create a superclass from an existing class, the easiest way to accomplish this is to select the __Extract Superclass__. This refactoring does not have a default keyboard shortcut (You can create one yourself). You will be presented with a dialog where methods, properties, and ivars are shown in a list with checkboxes, and an input field where you type the name of the new superclass. You check the name of what you want to move into the new superclass. If one of the selected methods has dependencies to other methods, properties, or ivars, you get a warning, telling you about the problem. 

![Extract Superclass](https://bonski-blog.s3.amazonaws.com/extract_superclass.png)
 
#### Extract Subclass
Here you create a subclass from a superclass. You select which methods, ivars and properties you want to take with you into the new subclass.

#### Extract Protocol and Category
Similar to the two above, except you are extracting protocols and categories.

## Inline
If you want to inline a method, AppCode will move the implementation of the method into where it's called from. If the method is called from more than one place, AppCode prompts you and asks for "Do you want to inline 'n' usages of method 'mehodName'? You options are: cancel the refactoring, execute the operation or view usages of the method you have selected to inline. If you select the latter, a list of usages is shown, and while navigating in this list, you can exclude the calls you don't want to inline by __&#x232B;__. If you change your mind, and want to include them again, you can do that by typing__&#x21E7;&#x232B;__

Below is a sample of an excluded usage of a method. This feature is also used in all refactoring where the change will affect more than in one place.

![Excluded file](https://bonski-blog.s3.amazonaws.com/excluded-file.png)

You can think of the ___Inline___ refactoring as an inverse of ___Extract Variable___, ___Extract Constant___ and so on.  

## Pull Members Up and Pull Members Down
These refactoring's are the same as ___Extract Superclass___ and ___Extract Subclass___. (At least as far as I know).  

## Refactor This...

![IRefactor this](https://bonski-blog.s3.amazonaws.com/refactor-this.png)

If your having trouble remembering all the different Refactor keyboard shortcuts, you should at least try to learn this one: __&#x2303;T__.
This shortcut will present a popup menu containing all the available refactoring's, that you can select from, by using the number in front of the name, or navigate by using the arrow keys, and select the one you want by __&#x21A9;__

If you are new to AppCode, or haven't used the Refactorings that AppCode offers, I would suggest that you take a closer look at what it have to give. 