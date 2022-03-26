## Delegates
 - Delegates provide a late binding mechanism in .NET
 - Delegates provide a mechanism that enables software designs involving minimal coupling between components.
 - One excellent example for this kind of design is LINQ. 
 - The LINQ Query Expression Pattern relies on delegates for all of its features
### Late Binding
   The binding of the function calls an object at the run time is called run time or dynamic or late binding

   For example, consider sorting a list of stars in an astronomy application. You may choose to sort those stars by their distance from the earth, or the magnitude of the star, or their perceived brightness.
   
   In all those cases, the Sort() method does essentially the same thing: arranges the items in the list based on some comparison. The code that compares two stars is different for each of the sort orderings.

### Function pointers 
    - Function pointers were added to C# 9 for similar scenarios, where you need more control over the calling convention.

C# has two inbuilt generic delegates Action and Func which takes upto 16 arguments.

### Events
 - Events are, like delegates, a late binding mechanism. 
 - In fact, events are built on the language support for delegates
 - Events are a way for an object to broadcast that something has happened
 * You've probably used events in some of your programming. 
 * Many graphical systems have an event model to report user interaction. Ex., Mouse Movement, Button presses
 * Subscribing to an event creates a coupling between two objects (the event source, and the event sink)

The syntax for defining events, and subscribing or unsubscribing from events is an extension of the syntax for delegates

``` C#

// at Publisher

// To define an event you use the event keyword:
public event EventHandler<FileListArgs> Progress;

// When you want to raise the event, you call the event handlers using the delegate invocation syntax:
Progress?.Invoke(this, new FileListArgs(file));

```

``` C#

// at Subscriber

// To subscribe to an event by using the += operator:
EventHandler<FileListArgs> onProgress = (sender, eventArgs) =>
    Console.WriteLine(eventArgs.FoundFile);

fileLister.Progress += onProgress;

// To unsubscribe using the -= operator:
fileLister.Progress -= onProgress;

```
In the above example FileListArgs should inherit System.EventArgs class. This restrictions has been relaxed in .NET Core.