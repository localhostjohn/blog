---
title:  "HTTP Request In Javascript"
date:   2022-12-31 17:05:00
description: Making a HTTP Request In Javascript
---

To make an HTTP request in JavaScript, you can use the XMLHttpRequest object or the newer fetch() function.

Here's an example of making an HTTP GET request using XMLHttpRequest:

{% highlight ruby %}
function httpGet(url) {
  var xhttp = new XMLHttpRequest();
  xhttp.onreadystatechange = function() {
    if (this.readyState == 4 && this.status == 200) {
      // Action to be performed when the document is read;
    }
  };
  xhttp.open("GET", url, true);
  xhttp.send();
}
{% endhighlight %}

You can call this function with a URL as an argument to make a GET request to that URL. For example:
{% highlight ruby %}
httpGet("https://www.example.com/ajax/demo.html");
{% endhighlight %}

Here's an example of making an HTTP GET request using fetch():
{% highlight ruby %}
fetch("https://www.example.com/ajax/demo.html")
  .then(response => response.text())
  .then(data => {
    console.log(data);
  });
{% endhighlight %}

This example makes a GET request to the specified URL and logs the response text to the console.

You can also use the fetch() function to make other types of HTTP requests, such as POST, PUT, and DELETE. To do this, you can pass an additional options object as the second argument to fetch(). For example:
{% highlight ruby %}
fetch("https://www.example.com/ajax/demo.html", {
  method: "POST",
  body: JSON.stringify({
    name: "John",
    message: "Hello World"
  }),
  headers: {
    "Content-Type": "application/json"
  }
})
  .then(response => response.text())
  .then(data => {
    console.log(data);
  });
{% endhighlight %}
This example makes a POST request to the specified URL with a JSON body and "Content-Type" header set to "application/json".