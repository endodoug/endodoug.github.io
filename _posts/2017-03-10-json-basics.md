---
layout: post
title: "JSON Basics"
date: 2017-03-10
author: Doug Harper
tags: [Fundamentals, JavaScript, JSON]
published: false
---


I’m tired of *“sorta”* understanding JSON and fighting with it in my projects, so I’m committing myself to learning the in’s-n-out’s over the next month.  My plan is start with the basics and move along in separate blog posts.

Writing about enums a while back was very helpful to my overall understanding and how to use them effectively.  Hopefully I'll get the same benefit after I write a few posts about JSON.  Honestly, slowing down and writing about the very basics of JSON has been extremely helpful already. 

An interesting little thing… after spending my time working with Swift exclusively, I feel very comfortable using Javascript and noticed many similarities. 

## JSON Data Basics - Recognition

JSON Strings that create a JavaScript Object always start and end with curly braces.  I get this, but didn't really understand what it meant.  

- JSON is text - a browser and a server can only exchange text data.  
- JSON can be converted into a JavaScript object and vice versa.
- This allows anyone to work with the data as a JavaScript object.

## Sending JSON Data

    var myJavaScriptObject = {“name”: “John Snow”, “title”: “King of the North”}; //1
    var myJavaScriptObjectConvertingToJSON = JSON.stringify(myJavaScriptObject); //2
    .send(myJavaScriptObjectConvertingToJSON); //3


1. Store data in a JavaScript object.
2. Convert the object to JSON. stringify() is a function that creates a string from the object.
3. Send it to the server.

## Receiving JSON Data

    var myJSONIsAString = '{ "name": "Doug", "age": "50", "state": "TX" }'; //1
    var convertToAJavaScriptObject = JSON.parse(myJSONIsAString); //2
    document.getElementById("demo").innerHTML = convertToAJavaScripthObject.name; //3

1. JSON received is comes as a string.
2. Convert the string to a JavaScript object. parse() is a function that converts a string to a JavaScript object.
3. Do something with the new object, like displaying it `<p id="demo"></p>`
