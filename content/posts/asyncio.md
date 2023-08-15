---
title: "Asyncronous programming with asyncio"
date: 2020-09-15T11:30:03+00:00
# weight: 1
# aliases: ["asyncronous scraping", "asyncio", "python"]
tags: ["asyncronous scraping", "asyncio", "python"]
author: "Me"
# author: ["Me", "You"] # multiple authors
showToc: true
TocOpen: false
draft: false
hidemeta: false
comments: false
description: "In this blog, I'll share my learnings about Asyncronous programming using asyncio."
canonicalURL: "https://canonical.url/to/page"
disableHLJS: true # to disable highlightjs
disableShare: false
disableHLJS: false
hideSummary: false
searchHidden: true
ShowReadingTime: true
ShowBreadCrumbs: true
ShowPostNavLinks: true
ShowWordCount: true
ShowRssButtonInSectionTermList: true
UseHugoToc: true
cover:
    image: "<image path/url>" # image path/url
    alt: "<alt text>" # alt text
    caption: "<text>" # display caption under cover
    relative: false # when using page bundles set this to true
    hidden: true # only hide on current single page
editPost:
    URL: "https://github.com/<path_to_repo>/content"
    Text: "Suggest Changes" # edit text
    appendFilePath: true # to append file path to Edit link
---
## Concurrent Programming vs Parallel Programming

Concurrent programming deals with managing mulitple tasks at the same time (eg: through context switching), whereas Parallel programming deals with involves executing multiple tasks or processes simultaneously often on different cores or processors.

Concurrent programming is not true parallelism.

## Asyncronous Programming
The benefit is *while one task is waiting for I/O operation, another task can utilize the CPU*.

While Asyncronous programming gives impression that tasks are running in parallel, this isn't always the case. tasks can run "concurrently" on single thread.

Asyncronous programming allows multiple tasks to run concurrently, ie, while one task is waiting for I/O operations, another can progress. eg: An I/O operation can be downloading a file from Internet, we can shift to another task while this task is handling its I/O.

## Event Loop
It is the heart of 'asyncio', this is a loop that constantly checks if there are coroutines to run and then runs them. The event loop shits to the next coroutine (task), when there is an await/async operation came up.

## Coroutines
These are special functions that we can pause and resume. They are defined using **`async def`** instead of usual **`def`**. They don't return values immediately; instead they return a coroutine objects which you can await using **`await`** keyword. 

The eventloop handles the pause and resume of the coroutines. When an **`await`** keyword is encountered, the current coroutine is paused and the event loop can execute the next tasks.

## async and await keywords
They both are essential components of asyncronous programming, but they do serve different roles.

### **async**

* **Usage**: The `async` keyword is used to declare a function or a method as a coroutine. It modifies `def` in function/method declarations.
* **Behaviour**: An `async` function does not run the code immediately when called. Instead it returns a coroutine object.
* **Example**:
```python
async def my_coroutine():
    print("Inside coroutine")
```
If we call `my_coroutine()` object, the print statement won't be executed, **you need to either `await` this coroutine or schedule the run on the next event loop.**

### **await**

* **Usage**: The `await` keyword is used within an `async` function to call another `async` function and wait for it to finish. It essentially pauses the current coroutine, allowing other tasks to run and resumes the current task once the awaited coroutine finishes.
* **Behaviour**: When the `await` keyword is encountered, the function's state is saved, control is given back to the event loop, which can execute other tasks. Once the awaited tasks is complete, the function resume from where it left off.
* **Example**:
```python
async def another_coroutine():
    return "Result from another_coroutine"

async def main():
    result = await another_coroutine()
    print(result)

```
The `print` statement is `main` won't execute until `another_coroutine` is finished.

Think of **`async`** as saying, "This function is special because it will be doing things asynchronously." And think of **`await`** as saying, "I'm going to wait right here for this other asynchronous thing to finish."


## Challenge: Asynchronous Web Scraper
**Objective**: Write an asynchronous web scraper using asyncio and aiohttp that fetches the content of multiple URLs concurrently and prints out the HTTP status and the first 100 characters of the content for each URL.

```python
import aiohttp
import asyncio

urls = ["https://www.example.com", "https://www.example.org", "https://www.example.net"]

async def fetch_content(url):
    async with aiohttp.ClientSession() as session:
        async with session.get(url) as response:
            text = await response.text()
            print(f"URL: {url}\nStatus: {response.status}\nContent: {text[:100]}...\n")

async def main():
    tasks = [fetch_content(url) for url in urls]
    await asyncio.gather(*tasks)

asyncio.run(main()) 
```


