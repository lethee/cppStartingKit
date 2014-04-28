C++ Starting Kit for Sublime Text
=================================

## Features
* C, C++ and C++11 combined and improved syntax highlighting support.
* Custom C++ build system for g++ compiler.

**/!\ It is highly recommended to read the Philosophy section just below before to install and use this package. /!\**

## Philosophy
The main objective of this project is to provide a fully functional and self-contained starting toolkit for beginners(like me) with C++ and Sublime Text including :
* A syntax definition which gives you the flexibility to make precise customizations to your syntax highlighting.
* An associated theme which includes all the new scopes. (see Oasis Theme)
* An intelligible build system.
* A relevant documentation for a quick start and an accessible maintenance.

**I have to mention two major things before to continue :**

* First, I'm really new in the huge world of programming. The first release of this package is the result of my first week of learning. My original goal is to learn C++ with a lightweight and flexible tool. A tool which allow me to customize my environment and let me control things like compiling. This was not an easy task because of the huge amount of solutions available out there. Finally Sublime Text seems to suit pretty well to my needs with his reasonable learning curve. 
* The second thing I want to mention is, in my opinion, **this package is not ready for production**. Even if the main behaviors are ever described and seem to work correctly, I think it will demand you a certain investment before to make it fully functional for your professional environment. 

But don't worry, as it is my primary tool for my journey to C++, I will do my best to update it quickly and make it fully functional as soon as possible.

## Preview
**Quick overview. (Oasis Theme not included)**

![C++ Starting Kit Standard behavior](https://github.com/kodLite/cppStartingKit/blob/master/screenshot/standard-behavior.jpg?raw=true)

**Arithmetic operators are now customizable.**

![C++ Starting Kit Arithmetic Operators](https://github.com/kodLite/cppStartingKit/blob/master/screenshot/custom-arithmetic-operators.jpg?raw=true)

**More customization.**

![C++ Starting Kit Customize Everything](https://github.com/kodLite/cppStartingKit/blob/master/screenshot/customize-everything.jpg?raw=true)

**Any function support.**

![C++ Starting Kit Any Function Support](https://github.com/kodLite/cppStartingKit/blob/master/screenshot/any-function-detection.jpg?raw=true)

**Easily add to your syntax definition with the documented configuration file.**

![C++ Starting Kit Add Keyword](https://github.com/kodLite/cppStartingKit/blob/master/screenshot/Namespace-added.jpg?raw=true)

THE GUIDE
=========
This guide covers the management of this package with Sublime Text 3 under Windows. Things are pretty much the same depending on your Sublime Text version or your operating system. 

Install the package
==========================

# Manually
(To do)

# From Package Control
(To do)


Customize your Theme
====================
If you use a default theme or something downloaded from the Internet you will surely need to tweak your configuration file. This next part is a set of few tips which help you to do it as easily as possible.

**Change your theme**

* Go to `Preferences > Color Scheme` menu.

**Locate your theme configuration file**

* Default themes are located inside `Sublime Text/Packages/Color Scheme - Default.sublime-package`. (see [How to edit a *.sublime package](https://github.com/kodLite/cppStartingKit#manipulate-sublime-package-format)) 
* User themes are located in `Sublime Text/Data/Packages/User/*.tmTheme`.

If you want to tweak a default theme I recommend you to copy it and rename it in your `Sublime Text/Data/Packages/User` folder.

**Retrieve a scope name**

* Put your cursor under the scope you want to know the name.
* Type `Ctrl + Alt + Shift + P`.

**Make a search**

* Make a search by typing `Ctrl + F`.
* Type what you want to find and don't forget to look everywhere in the document by pressing `Find` and `Find Prev`.

**Add a missing scope in your theme configuration file**

If you are sure that the scope doesn't exist in your `*.tmTheme`, add the following lines and fill the fields correctly :

		<dict>
			<key>name</key>
			<string>Scope name</string> 		<!-- Enter a name for your scope here. -->
			<key>scope</key>
			<string>Scope definition</string> 	<!-- Enter your scopes here. (ex : keyword.ccpp) -->
			<key>settings</key>
			<dict>
				<key>fontStyle</key>
				<string></string> 				<!-- Choose a style (ex : italic, bold, italic bold) -->
				<key>foreground</key>
				<string></string> 				<!-- Choose a color (ex : #49a629) -->
			</dict>
		</dict>


Customize your syntax definition
================================
# What you need to know

The syntax definition allow the syntax highlighting.
In **C++ Starting Kit**, to be able to quickly get a result, only the necessary pieces of code were modified :
* `C.tmLanguage` and `C++.tmLanguage`, which were mainly responsible of the syntax definition, were merged into `CCpp.tmLanguage`.
* `C++.sublime-build`, which embed the build system, was customized and renamed in `CCpp.sublime-build`.
* `C++.sublime-settings`, which specifies the supported file types, was just renamed in `CCpp.sublime-settings`. 
* All the other files were preserved.

To keep a flexible and easily maintainable system it was necessary to analyze, cut out and document the original code. Then extract useful pieces, merge them and reorganize the whole. (see `CCpp.tmLanguage`)

The greatest part of the changes are in the `CCpp.tmLanguage`. Now it is organized and documented to facilitate his approach and his maintenance. Functional pieces like comments, quoted strings or preprocessor modules are untouched.

## C++ Starting Kit scope list

(To do)

## Important note

This package was coded with a very simple approach. A main behavior is describe then smaller tweaks came to get the desirable result.

For example the curly brackets were defined as `open.curly.bracket.ccpp` and `close.curly.bracket.ccpp`. Then `open.curly.bracket.block.ccpp` and `close.curly.bracket.block.ccpp` were added to override the first definition and define the "block detection" behavior.

If you want to follow this process you have to put the main behavior at the bottom of your overrides, and not the opposite !!! (see the example below)

![C++ Starting Kit Syntax Definition Override](https://github.com/kodLite/cppStartingKit/blob/master/screenshot/overrides.jpg?raw=true)

# How to edit a *.sublime package

`*.sublime-package` like `CCpp.sublime-package` are `*.zip` archive. If you want to modify files inside this package you have to follow these steps :
* Inside your `Sublime Text/Packages` folder you have to find the package you want to modify.
* Copy and paste it in a safe place and do your tweaks on this copy.
* To open the package you have to rename it in `*.zip` then extract it.
* Inside the extracted folder you will find the editable files.
* When finished, save your changes.
* Close Sublime Text. 
* "Re-archive" your extracted folder in `*.zip` then rename it in `*.sublime-package`.
* Copy your updated `*.sublime-package` and overwrite the one in your `Sublime Text/Packages` folder.
* Restart Sublime Text.





Use the included C++ custom build
=================================
# Prerequisite

## Install MinGW 
