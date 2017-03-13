---
layout: post
title: "JSON Basics"
image: JSON.png
date: 2017-03-10
author: Doug Harper
tags: [Fundamentals, JavaScript, JSON]
published: true
---

![JSON Basics](/images/JSON.png "JSON Basics Header Image")

I’m tired of *“sorta”* understanding JSON and fighting with it in my projects, so I’m committing myself to learning the in’s-n-out’s over the next month.  My plan is start with the basics and move along in separate blog posts.

Writing about [enums](https://endodoug.github.io/blog/exploring-enums "Exploring Enums") a while back was very helpful to my overall understanding and how to use them effectively.  Hopefully I'll get the same benefit after I write a few posts about JSON.  Honestly, slowing down and writing about the very basics of JSON has been extremely helpful already. 


An interesting little thing… after spending my time working with Swift exclusively, I feel very comfortable using Javascript and noticed many similarities. 


## JSON Data Basics - Recognition

>JSON Strings that create a JavaScript Object always start and end with curly braces.  

I get this, but didn't really *understand* what it meant until breaking it down.

- JSON is text - a browser and a server can only exchange text data.  
- JSON can be converted into a JavaScript object and vice versa.
- This allows anyone to work with the data as a JavaScript object.

## Sending JSON Data

    {% highlight javascript %}
      var myJavaScriptObject = {“name”: “John Snow”, “title”: “King of the North”}; //1
      var myJavaScriptObjectConvertingToJSON = JSON.stringify(myJavaScriptObject); //2
      window.location = "example_url.php" + myJavaScriptObject; //3
    {% endhighlight %}

1. Store data in a JavaScript object.
2. Convert the object to JSON. `stringify()` is a function that creates a string (text) from the object.
3. Send it (text) to the server.

## Receiving JSON Data

Most of the time I'm the one receiving data and then putting it into my app or website.  A couple important points to keep in mind... JSON Data always includes key/value pairs & JSON keys **must** be strings with double quotes -> "jsonKey"

<p data-height="182" data-theme-id="0" data-slug-hash="VpbLJM" data-default-tab="js" data-user="endodoug" data-embed-version="2" data-pen-title="JSON Basics - Receive Data" class="codepen">See the Pen <a href="http://codepen.io/endodoug/pen/VpbLJM/">JSON Basics - Receive Data</a> by doug harper (<a href="http://codepen.io/endodoug">@endodoug</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script async src="https://production-assets.codepen.io/assets/embed/ei.js"></script>

1. JSON received is comes as a string (text.)
2. Convert the string (text) to a JavaScript object. `parse()` is a function that converts a string to a JavaScript object.
3. Do something with the new object, like displaying it `<h1 id="hello"></h1>`

Next up -> See how this plays out with Swift.

### Educational Sources:

- [Lynda.com - Processing and Interchanging JSON Data](https://www.lynda.com/Web-Development-tutorials/Processing-Interchanging-JSON-Data/560344-2.html "Processing JSON via Lynda.com") by Sasha Vodnic
- [W3Schools](https://www.w3schools.com/js/default.asp "JSON Introduction")
