# Puzzle #77 - Unhelpful Errors

Carl and Jeff try to solve a problem with a simple Blazor app that's throwing some errors that aren't very helpful.

This puzzle comes from alert viewer **Justin Lamping**, who will receive a Blazor Puzzle mug for sending it in!

YouTube Video: https://youtu.be/

Blazor Puzzle Home Page: https://blazorpuzzle.com

## The Challenge

We received an email this week from a member of our Blazor community that's having some a problem with a very simple Blazor app.

It's a .NET 9 Blazor Web App with Global Server Interactivity

We have created a page called `Task.razor` and provided a link to it in `NavMenu.razor`

However, it does not build. We get some strange errors:

```
'Weather.OnInitializedAsync()': return type must be 'Task' to match overridden member 'ComponentBase.OnInitializedAsync()'
```

and

```
The return type of an async method must be void, Task, Task, a task-like type, IAsyncEnumerable, or IAsyncEnumerator
```

WTF?

## The Solution

The rule that applies here is that you can't name a page or component the same as a class in the .NET Core Framework. 

Therefore, the solution is to rename Task.razor to something else. We renamed it to Tasks.razor and also changed the @page directive at the top.

BOOM!

