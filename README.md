React Topic

---Outline---

1. What is React?
  React is a JavaScript Library for building User Interfaces.
  React was created by Jordan Walke, a software engineer at Facebook.

2. Why use React?
  React only affects the View in Model View Control, giving you a simpler programming model.
  It implements one-way reactive data flow which is easier to reason than traditional data binding.

3. What are the pros and cons to React?
  Pros:
  - Extremely easy to write UI tests cases. This is due to the virtual DOM system implemented entirely in JS.
  - Components can be reuse easily throughout your app. They can also be combined, and wireup together to create even more complex UIs.
  - You can use reactJS as an alternative, or along with popular JS libraries such as angular, backbone and jQuery.
  - React will automatically manage all UI updates when your underlying data changes.
  - Ease of debugging. there's a reactJS chrome extension that allows you to inspect the DOM to figure out which component is rendering a particular piece of UI.
  - Works nicely with commonJS / AMD patterns.

  Cons:
  - There's a learning curve for beginners whom are new to web development.
  - Integrating reactJS into a traditional MVC framework such as rails would require some configuration. (ie: substituting erb with reactJS).
  - It's kind of verbose. Writing components isn't as straight forward as pure HTML & JS.
  - It's not a full framework. There's no router nor model management libraries built into reactJS -- unlike angular or ember. Hence one needs to have some degree of experience in picking libraries to fulfill these needs.

  References:
  - https://facebook.github.io/react/index.html
  - https://www.quora.com/What-are-the-pros-and-cons-of-React-js-and-Flux-Are-they-the-future-of-front-end-development)


4. How to use React.

  - Step 1: Install React
    Terminal: $ npm install -g react

  - Step 2: In your main directory, create a file 'main.js' and place the following code there:
    // main.js
    var React = require('react');
    var ReactDOM = require('react-dom');

    ReactDOM.render(
      <h1>Hello, world!</h1>,
      document.getElementById('example')
    );

  - Step 3: Install browserify module system:
    Terminal: $ install -g browserify

  - Step 4: Install ReactDom and your bundle with browserify
    Terminal: $ npm install --save react react-dom babelify babel-preset-react
              $ browserify -t [ babelify --presets [ react ] ] main.js -o bundle.js

  - Step 5: Download the starter-kit:
    https://facebook.github.io/react/downloads/react-0.14.6.zip

  - Step 6: In your main directory, create a file 'helloworld.html' with the following contents:
    <!DOCTYPE html>
    <html>
      <head>
        <meta charset="UTF-8" />
        <title>Hello React!</title>
        <script src="build/react.js"></script>
        <script src="build/react-dom.js"></script>
        <script src="https://cdnjs.cloudflare.com/ajax/libs/babel-core/5.8.23/browser.min.js"></script>
      </head>
      <body>
        <div id="example"></div>
        <script type="text/babel">
          ReactDOM.render(
            <h1>Hello, world!</h1>,
            document.getElementById('example')
          );
        </script>
      </body>
    </html>

  - Step 7: Create a separate JSX file in a 'src' directory like this: 'src/helloworld.js' with the following content:
    ReactDOM.render(
      <h1>Hello, world!</h1>,
      document.getElementById('example')
    );

  - Step 8: Reference 'src/helloworld.js' in your 'helloworld.html'
    <script type="text/babel" src="src/helloworld.js"></script>

  - Step 9: Install the Babel command-line tools
    Terminal: $ npm install --global babel-cli
              $ npm install babel-preset-react

  - Step 10: Then, translate your 'src/helloworld.js' file to plain JavaScript:
    Terminal: $ babel --presets react src --watch --out-dir build
    (The file build/helloworld.js is autogenerated whenever you make a change.)

  - Step 11: Update your HTML file as below:
    <!DOCTYPE html>
    <html>
      <head>
        <meta charset="UTF-8" />
        <title>Hello React!</title>
        <script src="build/react.js"></script>
        <script src="build/react-dom.js"></script>
        <!-- No need for Babel! -->
      </head>
      <body>
        <div id="example"></div>
        <script src="build/helloworld.js"></script>
      </body>
    </html>
