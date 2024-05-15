# Interactive Code-Blocks

To make code blocks interactive, LiaScript provides several features:

1. **`Interactive Inputs:`** You can add interactive inputs to your code blocks using special syntax. These inputs can be sliders, text inputs, buttons, etc., allowing users to modify the code's behavior dynamically.

2. **`Execution and Visualization:`** LiaScript can execute code blocks and visualize their output. This is particularly useful for languages like JavaScript, Python, or R where the output can be visualized directly within the document.

3. **`Editable Code Blocks:`** Users can edit code blocks directly within the document and see the changes reflected in real-time. This is great for experimenting with code or following along with tutorials.

4. **`Script Tags:`** You can use `<script> `tags to execute JavaScript code blocks. This allows for more complex interactions and dynamic content generation.

## Starting simple

In the provided example, we have a JavaScript code snippet that calculates the sum of all numbers up to `i` for each iteration of the outer loop `i` from `0` to `9`. The inner loop `j` iterates from `0 to i-1`, adding each value of `j` to the result variable. Finally, the result is returned.

- **`Script Tag:`** The `<script> `tag with the @input placeholder allows users to input their own values directly into the code block.

- **`Execution:`** If the code is a full and executable example, users can click the "Run" button below the code to execute it. The console output will be displayed below the code snippet.

**`Interactive Inputs:`** Users can modify the code directly within the document. For example, they can change the number of loops or modify other parts of the code. When the modified code is executed, a new version of the output will be added to the end of the list. Users can go back and forth between versions and modify previous versions as well.

```
var i=0;
var j=0;
var result = 0;

for(i = 0; i<10; i++) {
    for(j = 0; j<i; j++) {
        result += j;
        console.log("(", i, ",", j, ") result", result)
    }
}
result;

  <script>@input</script>
```

## Projects

1. `Code Snippets:` We have two code snippets written in JavaScript and JSON. The JavaScript snippet, named `EvalScript.js`, defines a variable `who` based on the data from the JSON file. It checks if the person is online and generates a message accordingly. The JSON snippet, named `Data.json`, provides the data used by the JavaScript code.

2. `Script Tag:` The `<script>` tag serves as the glue code that brings everything together. It first inserts the JSON dataset into a local variable named `data`. Then, it evaluates the JavaScript code, substituting `@input` with the content of the JavaScript code snippet. Alternatively, we could directly use `@input(0)` to achieve the same result.

```JS
let who = data.first_name + " " + data.last_name;

if(data.online) {
  who + " is online"; }
else {
  who + " is NOT online"; }
```

```json
{
  "first_name" :  "Sammy",
  "last_name"  :  "Shark",
  "online"     :  true
}
```

```html
<script>
  let data = @input(1);
  @input
</script>
```

## Default @output

1. `Code Snippets:` We have two code snippets written in JavaScript and JSON, similar to the previous example. The JavaScript snippet defines a variable `who` based on the data from the JSON file and generates a message based on whether the person is online or not.

2. `Output Marker:` The third code block is marked with `@output`. This indicates that the content of this block should be displayed as the default output. In this case, the output asks whether "Sammy Shark" is really online.

3. `Script Tag:` The script tag serves the same purpose as before, combining the JavaScript and JSON snippets and evaluating the script.


```js
let who = data.first_name + " " + data.last_name;

if(data.online) {
  who + " is online"; }
else {
  who + " is NOT online"; }
```

```json
{
  "first_name" :  "Sammy",
  "last_name"  :  "Shark",
  "online"     :  true
}
```

```
Is Sammy Shark really online?
```

```html
<script>

  let data = @input(1);

  @input
</script>
```

## Loading external Resources

1. `Loading External Resource:` We use the `script` command in the main LiaScript header to load the Algebrite library from a CDN. This library provides a Computer Algebra System (CAS) that allows us to perform algebraic computations.

2. `Markdown Content:` Within the Markdown content, we can then utilize the loaded library directly within script tags. In this example, we're using MATLAB syntax to define an equation and perform integration.

3. `Script Tag:` The script tag executes the Algebrite module's `run` function, passing in the MATLAB equation defined in the Markdown content.

```
<!--
author: ...

script: https://cdn.rawgit.com/davidedc/Algebrite/master/dist/algebrite.bundle-for-browser.js
-->

```

This part of the code loads the Algebrite library from the specified CDN.

```
f=sin(t)^4-2*cos(t/2)^3*sin(t)

f=circexp(f)

defint(f,t,0,2*pi)
```

`<script> Algebrite.run(`@input`) </script>`

```vbnet
Here, within the Markdown content, we define a MATLAB equation and then execute it using the Algebrite library's `run` function within a script tag.

The result is a fully functional computer algebra editor where you can experiment with and modify equations, leveraging the capabilities provided by the Algebrite library.
```

## Code API

1. **`Basic Usage`**

```javascript
// This is a simple JavaScript code block
console.log("Hello, LiaScript!");
```

To execute this code, simply place it within a script tag:

```javascript
<script>
  // This is a simple JavaScript code block
  console.log("Hello, LiaScript!");
</script>
```

2. **`Asynchronous Code Execution`**

```javascript
<script>
  // This is a simple JavaScript code block
  console.log("Hello, LiaScript!");
</script>
```

To execute asynchronous code, you can use the setTimeout function:


```javascript
<script>
  // Asynchronous code example
  setTimeout(() => {
    console.log("This code executes after 2 seconds");
  }, 2000);
</script>
```

3. **`LiaScript API`**

LiaScript provides an API that allows you to interact with the runtime environment. For example, you can use the `output` function to display output directly in the LiaScript output area:

```javascript
// Using LiaScript API to display output
output("This is some output using LiaScript API");
```

To use the LiaScript API, simply call the `output` function:

```javascript
<script>
  // Using LiaScript API to display output
  output("This is some output using LiaScript API");
</script>
```

### send – Object

The `send` object in LiaScript is associated with every executed piece of code and serves as a communication interface between the code block or project and the outer environment. It provides several methods for different purposes:

`send.log:` Outputs logging information to the console.

`send.lia:` Sends messages and control commands.

`send.handle:`Handles terminal inputs.

`send.register:` Registers to a global event.

`send.dispatch:` Dispatches a global event.

In this example, we demonstrate the usage of `send.log`, which allows sending different types of outputs directly to the console.

**`Example`**

1. **Using `send.log`**

```javascript
send.log("debug", "", ["This is a debug information"]);
send.log("warn", "", ["This is a warning", 12, [1, 2, 3]]);
```

2. Using `console` shortcuts

```javascript
console.debug("These are shortcuts for send.log('debug' ... ");
console.warn("warn");
console.log("info");
console.error("This will be displayed in red for errors");
console.html("<b>Some more fancy stuff:</b> <img width='40px' src='https://www.math.uni-bielefeld.de/~jsauter/Octahedron.gif'/>");
```

### Return types

1. `Basic Output`

```javascript
33 * 33
```

2. `Stop Execution`

```javascript
33 * 33

"LIA: stop" // Stops the execution, no further output will be displayed
```


3. `Asynchronous Execution`

```javascript
setTimeout(function(){
  console.warn("End of execution")

  send.lia("Some other output")

  send.lia("LIA: stop") // Stops the execution
}, 3000)

"LIA: wait" // Indicates asynchronous execution, wait until stopped
```

4. **Using `send.lia`**

Using `send.lia` gives more control over the shell and editor.

5. `Terminal Mode`

To enable terminal mode, use "LIA: terminal" as the last statement.

```javascript
send.handle("input", input => {
  try{
    console.log(eval(input))
  } catch (e) {
    console.error(e.message);
  }
})

send.handle("stop", e => { alert("Execution stopped") })

function close(){
  send.lia("LIA: stop")
}

"LIA: terminal" // Activates the terminal
```

6. `Additional Commands`

`LIA: clear:` Clears the terminal.

`LIA: terminal:` Starts the terminal.

`LIA: stop:` Manual stop event.

`LIA: wait:` Indicates asynchronous execution.

**`Explanation`**

`Basic Output:` The result of the expression is displayed in the console.

`Stop Execution:` The string "LIA: stop" is used to stop the execution, preventing further output.

`Asynchronous Execution:` Indicates that the execution is asynchronous and waits until stopped.

`Using send.lia:` Provides more control over the shell and editor.

`Terminal Mode:` Activates the terminal mode, allowing interactive input.

`Additional Commands:` Commands to clear the terminal, start the terminal, stop execution, or indicate waiting.

### Ping Pong: register & dispatch

These code blocks demonstrate how to use the `register` and `dispatch` functions to establish communication between two code blocks using custom events. Here's how it works:

1. `Code Block 1:`

- Registers a callback function for the `"ping"` event.

- Sends a message `(input)` whenever an input event occurs, triggering the dispatch of a `"pong"` event.

```javascript
send.register("ping", function(e){
  console.warn("ping", e)
})

send.handle("input", input => {
  send.dispatch("pong", input)
})

"LIA: terminal" // Execute the code
```

2. `Code Block 2:`

- Registers a callback function for the `"pong"` event.

- Sends a message `(input) `whenever an input event occurs, triggering the dispatch of a `"ping"`event.

```javascript
send.register("pong", function(e){
  console.warn("pong", e)
})

send.handle("input", input => {
  send.dispatch("ping", input)
})

"LIA: terminal" // Execute the code
```



### Error Handling


1. **Using `send.lia:`** Passes messages to the terminal output, along with line-specific warnings or errors for enhanced interactivity.

```javascript
send.lia("Ups, something went wrong",
  [
    [
      { row: 1, column: 1, text: "Insert your error info here", type: "error" },
      { row: 2, column: 1, text: "Some general warnings about this line", type: "warning" }
    ]
  ],
  false); // Output appears in "error" mode

"LIA: stop";
```

2. **Using `LiaError:`** Simplifies error handling by creating a new error object and adding details about error messages, line numbers, and warning types.

```javascript
// Create a new error with an error message
var error = new LiaError("Ups, something went wrong", 1);

// Add details specifying line numbers and error messages
error.add_detail(0, "Insert your error info here", "error", 1, 1);
error.add_detail(0, "Some general warnings about this line", "warning", 2, 1);

// Throw the error
throw(error);
```


## Example: CPP in JavaScript

This code block demonstrates how to execute C++ code within JavaScript using JSCPP. Here's what happens:

- The C++ code is provided within the code block.

- The JSCPP library is used to execute the C++ code in a JavaScript environment.

- The `JSCPP.run `function is called with the C++ code provided as input.

- The output of the C++ program is captured and displayed below the code block.


```cpp
#include <iostream>
using namespace std;

int main() {
    int a = 120;
    int rslt = 0;
    for(int i=1; i<a; ++i) {
        rslt += i;
        cout << "rslt: " << rslt << endl;
    }
    cout << "final result = " << rslt << endl;
    return 0;
}
```

## Styling

`Line Numbering:` By default, code blocks without execution capabilities won't show line numbers. However, executable blocks will display line numbers. You can explicitly control this behavior using the `data-showGutter` attribute.

`Theme:` You can specify the theme for the code block using the data-theme attribute. This allows you to change the appearance of the code block based on your preference.

`Read-only Mode:` Set the `data-readOnly` attribute to make a code block read-only. You can either set it to `true` or `false` to control the read-only mode.

`Highlighting:` Use the `data-marker` attribute to highlight specific aspects of your code. You can define the row and column range, color, and type of highlight.

`Customization:` Other attributes such as `data-firstLineNumber`, `data-fontSize, data-tabSize`, and `data-theme` allow you to further customize the appearance and behavior of code blocks.

Let's see an example below to demonstrate how these attributes work:


````` markdown
<!-- data-showGutter="false" -->
```cpp
// some C++ code without line numbers
...
```
<!-- data-readOnly="true" -->
```hpp
// some header-file with lineNumbers,
// that cannot be edited
```
<script>
...// your execution code
</script>
`````

```` markdown
<!-- data-marker="
0 0 0 100 error screenline;
2 0 4 200 log;
6 12 6 33 rgba(55,255,100,0.5) text"
data-showGutter="true"
data-theme="chaos"
data-readOnly="false" -->
```
this will be red

this is blue ...
until the next
line

and this is rgba(55,255,100,0.5)
```
````

<!-- data-marker="
0 0 0 100 error screenline;
2 0 4 200 log;
6 12 6 33 rgba(55,255,100,0.5) text"
data-showGutter="true"
data-theme="chaos"
data-readOnly="false" -->
```
this will be red

this is blue ...
until the next
line

and this is rgba(55,255,100,0.5)
```

**`Attributes:`**

`data-showGutter:` Controls the visibility of line numbers.

`data-theme:` Specifies the theme of the code block.

`data-readOnly:` Sets the read-only mode of the code block.

`data-marker:` Highlights specific aspects of the code.

`data-firstLineNumber:` Defines the initial line number.

`data-fontSize:` Specifies the font size.

`data-tabSize:` Sets the tab size.


## More Examples

The collection of LiaScript templates on GitHub offers a wide range of examples showcasing different functionalities implemented using editable code snippets and macros. These templates serve as excellent resources for learning and exploring LiaScript's capabilities. Here's a brief overview of some of the templates available in the collection:

**1. `Presentation Templates:`** Templates designed for creating interactive presentations using LiaScript. These templates often include features such as slide navigation, interactive code snippets, quizzes, and more.

**2. `Educational Templates:`** Templates focused on educational content creation, including tutorials, lessons, and interactive exercises. These templates demonstrate how LiaScript can be used to enhance the learning experience with interactive elements.

**3. `Documentation Templates:`** Templates for creating documentation with LiaScript. These templates provide structures for organizing and presenting technical documentation, tutorials, API references, and more.

**4. `Project Templates:`** Templates tailored for project documentation, including README files, project overviews, feature documentation, and more. These templates demonstrate how LiaScript can be integrated into project workflows for better documentation practices.

**5. `Course Templates:`** Templates designed for creating online courses using LiaScript. These templates offer structures for organizing course content, including lectures, assignments, quizzes, and assessments.


[Reference link](https://github.com/topics/liascript-template)