---
description: 'By: Thomas Lee'
---

# 26. Prefix Operations and Tries

{% embed url="https://www.youtube.com/watch?ab_channel=JoshHug&v=i-OuY5o_G8g" %}

### The Search Problem

To motivate this next section, let us consider the **search problem**. In this problem, we are given a stream of data, and our goal is to retrieve the information of interest. For example, a website which allows users to post content to their personal page could want to serve that content only to friends. Another example is if a new station receives logs from thousands of weather stations, and it wants to display a weather map for a specified date and time.&#x20;

Both of these are examples of the search problem, just in different flavors! The data structures we have built so far have been to solve the search problems for various domains of interest.

Let us review the data structures we have seen so far:

<table><thead><tr><th width="101">Name</th><th width="222">Storage Operations</th><th width="241">Primary Retrieval Operation</th><th>Retrieve By</th></tr></thead><tbody><tr><td>List</td><td><code>add(key)</code>, <code>insert(key, index)</code></td><td><code>get(index)</code></td><td>index</td></tr><tr><td>Map</td><td><code>put(key, value)</code></td><td><code>get(key)</code></td><td>key identity</td></tr><tr><td>Set</td><td><code>add(key)</code></td><td><code>containsKey(key)</code></td><td>key identity</td></tr><tr><td>Priority Queue</td><td><code>add(key)</code></td><td><code>getSmallest()</code></td><td>key order (smallest to largest)</td></tr><tr><td>Disjoint Sets</td><td><code>connect(int_a, int_b</code></td><td><code>isConnected(int_a, int_b)</code></td><td>two integer values</td></tr></tbody></table>

All of these data structures are used to solve different instances of the search problem. They all have their own applications depending on how the data of interest needs to be retrieved. \
One important thing to note is that these are **abstract** data types (ADTs), which means that we define the behavior of the data structure, not the implementation. There are multiple possible implementations for each of the data structures, and we can even use one data structure in the implementation of another! We often use these ADTs to create even more complex data structures.&#x20;

### Abstraction

Abstraction is the idea of only being concerned with the behavior of something and not the underlying implementation. This concept is not as foreign as you might think! We apply principles of abstraction in our day to day lives without even realizing it. For example, using a keyboard can be considered an abstraction of writing text onto a computer. There can be multiple implementations of a keyboard's circuitry depending on what company produced it, but we do not worry about what is going on under the hood, we just care that it can allow us to type text onto a computer.&#x20;

Abstraction is often applied in _layers_ when creating data structures.&#x20;

When implementing a Priority Queue, we could choose to use a Heap Ordered Tree to store the elements of the priority queue. We do not worry about the implementation of the Heap Ordered Tree--we just care about the methods that a Heap Ordered Tree provides.&#x20;

In the same vein, the Heap Ordered Tree does not care about the implementation of the Tree data structure that it uses in it's underlying implementation.&#x20;

Finally, whoever ends up using the Priority Queue we create is also unconcerned with how we made the Priority Queue. They would only care that our Priority Queue is able to support adding elements and returning the smallest element efficiently.&#x20;

In summary, we can often think of an ADT by the use of another ADT. ADTs have layers of abstraction, each defining behavior that is more specific than the idea that came before&#x20;
