# Asynchronous-Programming-in-dart-and-Flutter

I have various challenges understanding Asychronous concepts for quite sometime. Its hard to write a code if you dont know Asynchronous concepts . Asynchronous programming is an equivalent type of programming that allows a unit of work to run independently of the basic application thread. When the work is complete, it tells the main thread. UI widgets accessible in the Flutter structure use Dart's asynchronous programming highlights to achieve extraordinary results, help maintain code coordination, and prevent UI security on the client.
In this short essay , I  will explore asynchronous programming in Dart & Flutter. I will Look at how the asynchronous code pattern can help prepare user interaction and recover data from the network, and see the actions of several asynchronous Flutter widgets in your Flutter application.

Dart Async is related to asynchronous programming. It executes the asynchronous operation in a thread. It ensures that the critical functions to be executed until completion. The asynchronous operation is executed, separately the main application thread. In Dart, one operation cannot interrupt the other operation; it means one operation can execute at a time no other part of the program can avert it. Let's understand the following example -

<!-- GETTING STARTED -->
# Aync and await 
The **async** and **await** approaches in **Dart** are very similar to other languages, which makes it a comfortable topic to grasp for those who have used this pattern before. However, even if you don’t have experience with asynchronous programming using async/await, you should find it easy to understand .

When an async function is called, a Future is immediately returned and the body of the function is executed later.
As the body of the async function is executed, the Future returned by the function call will be completed along with its result. 
In the above example, calling demo() results in the Future.

Any functions you want to run asynchronously need to have the async modifier added to it. This modifier comes right after the function signature, like this;

``` void hello() async {
print('something exciting is going to happen here...');
}
```

Typically, the function you want to run asynchronously would have some expensive operation in it like file I/O (an API call to a RESTful service).

### Await expressions:

Await expressions makes you write the asynchronous code almost as if it were synchronous. In general, an await expression has the form as given below:

`void main() async { await hello();
print('all done');
}`


Typically, it is an asynchronous computation and is expected to evaluate to a Future. The await expressions evaluate the main function, and then suspends the currently running function until the result is ready–that is, until the Future has completed. The result of the await expression is the completion of the Future.

- There are **two** important things to grasp concerning the block of code above. First off, we use the async modifier on the main method because we are going to run the hello() function asynchronously.
- Secondly, we place the await modifier directly in front of our asynchronous function. Hence, this is frequently referred to as the async/await pattern.
- Just remember, if you are going to use await, make sure that both the caller function and any functions you call within that function all use the **async** modifier.

### Futures:

Dart is a single-threaded programming language. Future<T> object represents the result of an asynchronous operation which produces a result of type T. If the result is not usable value, then the future’s type is Future<void>. A Future represents a single value either a data or an error asynchronously

There are 2 ways to handle Futures:

- Using the Future API
- Using the async and await operation.

Now, Let’s write a program and see the output.

**Example:**

`Future delayedPrint(**int**` `seconds, String msg) {`

`final duration = Duration(seconds: seconds);`

`**return**` `Future.delayed(duration).then((value) => msg);`

`}`

`main() async {`

`print('Dart  ');`

`await delayedPrint(2, "Is").then((status){`

`print(status);`

`});`

`print('Good');`

`}`

---

### Output-

```
Dart
Is
Good

```

In this case, I used async and await keywords. Await basically holds the control flow, until the operation completes. To use await within a function, we have to mark the function by async keyword. Which means, this function is an asynchronous function.

Combined with the Futures class, the async / await pattern in Dart is a powerful and expressive way of doing asynchronous programming.

In summary , asynchronies programing in dart consists  on these key concepts  ; 

1. Asynchronous function is a function that returns the type of **Future**.
2. Put `await` in front of an asynchronous function to make the subsequence lines waiting for that future's result.
3. Put `async` before the function body to mark that the function support `await`.
4. An `async` function will automatically wrap the return value in **Future** if it doesn't already.

## Reference

[https://issuecloser.com/blog/understanding-future-async-and-await-in-flutter](https://issuecloser.com/blog/understanding-future-async-and-await-in-flutter)

[https://sarunw.com/posts/how-to-use-async-await-in-flutter/#what-is-future](https://sarunw.com/posts/how-to-use-async-await-in-flutter/#what-is-future)

Flutter Dart Dev

https://dart.dev/codelabs/async-await


