<img align="right" src="https://github.com/braingu/tadpole/blob/master/images/TLP/TLPAmber.png">

## Contents

- [Breaking Down Problem Solving: Matt’s Best Practices](#breaking-down-problem-solving--matt-s-best-practices)
- [Regex 101](#regex-101)
- [Automation 101](#automation-101)
  * [Basics](#basics)
  * [Problem definition](#problem-definition)
  * [Troubleshooting](#troubleshooting)



## Breaking Down Problem Solving: Matt’s Best Practices


## Regex 101

Learn regex. Knowing how to manipulate regular expressions easily will help you with everything else.

*   [https://regexcrossword.com/](https://regexcrossword.com/)


## Automation 101


### Basics

*   Start by breaking down a problem into what the manual way is, and then asking if that can be automated.
*   Understand communication paths between the back end and the front end. If you’re trying to determine a problem, start with, “how was the problem discovered?” It’s usually through someone trying at the front end — it wasn’t someone in the backend. If the problem is discovered, you can reproduce it from the front end.


### Problem definition

The front end is sending info to the back end. Based on the request from front to back, break apart where the info is set.

First look at the problem as the user on the front end, then figure out how they’re connected.

  *   The network logs from front end communicating to back end. If the front end isn’t providing info, the backend isn’t running because the front end didn’t tell it to. Watching what the actual network does can tell you where the issue is.
  *   That delineation, and then from there, how is the user communicating? Is it a button? Text entry? Classification?
  *   You need to run through the decision tree based on your program by understanding the pathways through which information is gathered and saved.
  *   As you build context around an application and understand how it communicates with itself and its dependencies, that context will let you make decisions faster.


### Troubleshooting

Once the issue is defined, then you set about resolving it.

1. There are lots of types of sorts.
2. Build the blocks you’re going to sort based on a decision tree
    * Is the problem in the front end or the back end? Determine that by seeing what the front end is sending to the back end.
    * If it’s receiving good data and outputting bad, that tells you the back end is the issue, so then you go into the back end and determine the incoming path.
3. For a full stack developer, walk through the application the way a request will walk through the application. Preferably, actually walking through it with a debugger. If a debugger isn’t available (rare), then write out the path, or keep track of it in your head.
4. Then analyzing what the backend is doing, what’s the comparison, what are the variables? If you’re stepping through with a debugger, you can find issues that aren’t apparent just while reading it.
5. Understand the fundamentals. Different languages handle variables differently. If you don’t know how they do it, you’re going to come to the wrong conclusions. If you use a debugger, that makes it better and helps you find the problem faster.
    *  If you’re doing standard development, there’s always a debugger. The only cases where there aren’t are really special. Classified systems, limited toolsets, etc.
    *  Standard now is VSCode, but that standard changes all the time. Sublime, Atom to PyCharm. VSCode has a better capability set. Microsoft has been excellent about this, because Visual Studio was the best for MS programming. VSCode is the open source version of that.
6. Analyzing the front end — if it’s a front end issue, the data the user is entering is not making it to the back end. So the #1 thing that people do wrong is they try to find the connection and where people enter the data from the top level, pathing down to the base. Use search to find the term — start from the source of the issue.
7. On the back end, start at the top, and work your way into the issue, to figure out how the info passes.
8. On the front end, start specific and work your way up.

He harps on regex, but you have to know when it is the right time to use a search. When you recognize that a problem can be solved by finding and placing a thing. If we change just this bit, it would be correct, or the data is there but needs to appear differently. If the information is all there and it only needs to change, then regex can probably solve and change for you.

Say you have a large list of complex objects and you need to sort them. You literally have the text of objects, and you have to sort and send to another thing; how do you do that? With regex, you can pull out the value you need to sort by, add a tab at the end, and put that value again. Copy all of that, paste into google sheets, and sort the column. Then everything’s sorted. Copy, and done.

If doing it manually takes you five minutes and you’re only doing it a few times, then don’t automate. There are plenty of things you just have to manually do. It’s just getting better at the estimation of your time, building a tool or using regex to do it.

A lot of real time development is front end UX, and updating the UI to give a better experience. But it’s also “oh, the backend should handle that”. A user was creating a mission, and the first thing they’d do is create meetings. Then create a new mission and create the same meetings over and over. So then he told the backend to automatically create the meetings.

You need to pick up patterns in user behavior: How do they move their mouse, how are they looking for things? A lot of design principles, at the heart, are how to give users the best interaction and access to the software for stuff they need to do faster. Hamburger menu is awful for mobile; adds an additional click for every interaction.
