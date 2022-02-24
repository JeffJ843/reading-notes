Read 6
JavaScript
JavaScript (JS) is a lightweight, interpreted, or just-in-time compiled programming language with first-class functions. While it is most well-known as the scripting language for Web pages, many non-browser environments also use it, such as Node.js, Apache CouchDB and Adobe Acrobat. JavaScript is a prototype-based, multi-paradigm, single-threaded, dynamic language, supporting object-oriented, imperative, and declarative (e.g. functional programming) styles. Read more about JavaScript.

In the first article we saw how to change the DOM to display something, and then we saw how to handle user events. This time we are going to see how to get input from the user and combine that with the other two, to create a simple page that can great you.

examples/js/pure_js_greating.html
1. <html>
2. <head>
3.   <title>Hello World</title>
4. </head>
5. <body>
6.  
7. First name: <input id="first_name">
8. Last name: <input id="last_name">
9. <button id="say">Say hi!</button>
10.  
11. <hr>
12. <div id="result"></div>
13.  
14. <script>
15. function say_hi() {
16.     var fname = document.getElementById('first_name').value;
17.     var lname = document.getElementById('last_name').value;
18.  
19.     var html = 'Hello <b>' + fname + '</b> ' + lname;
20.  
21.     document.getElementById('result').innerHTML = html;
22. }
23.  
24. document.getElementById('say').addEventListener('click', say_hi);
25. </script>
26.  
27. </body>
28. </html>
29.  
Try!
In this example we have a bit more HTML than earlier. In addition to having a button, and a div element where we'll show our results, we also have two input elements. Each one with its own ID.
If you click on the Try link, you'll see two input boxes and a button:
￼

In the JavaScript code we have a function called say_hi. It used the getElementById we have already seen to locate the DOM element representing the input element with the id first_name. The object returned has a method value that will return the text the user has typed in that field.
We use this technique to retrieve the content of both input fields and assign their content to two variables: fname and lname.
Then, using these variable we create an HTML snippet and assign it to a new variable called html.
Then we set the innerHTML attribute as earlier to show the HTML we generated. The result might look like this:
￼


Creating HTML is cumbersome
Even in such a simple HTML we wanted to create we had to use + several time and the code is quite unreadable. Imagine what would happen if we wanted to build a more complex application where we might want to build a list of items, or even a table. Building the HTML on the fly and the inserting in the DOM would be quite nasty.
In the back-end systems written in Perl, Python or Ruby, people have encountered the same problem and the solution was the creation of various templating engines. Basically a template would be an HTML snippet with some place holders and then a function call that gets the HTML snippet (the template) as a parameter, and gets several key-value pairs. The function then returns a new HTML snippet in which the place holders were replaced by the value of the appropriate key.
In a similar way, there are many templating system for JavaScript as well. We are going to look at HandlebarsJS, the JavaScript templating engine.
