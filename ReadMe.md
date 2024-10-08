# **ANGULAR**
<img src="the-seo-guide-to-angular.png" alt="" style="width:100%;"/>


## Table of Content
- Introduction to AngularJS 
- Getting Started
- AngularJS Expressions
- AngularJS Modules
- Directives in AngularJS
- AngularJS Filter
- AngularJS - Tables
- Pipes
- AngularJS Events
- References



## Introduction to AngularJS

### What is Angular?
Angular is a framework for building websites and web apps, especially single-page apps, using HTML and TypeScript. It's developed by Google and helps developers create dynamic, interactive, and fast web applications easily. With Angular, you can manage how a webpage updates without needing to reload the whole page, making user experiences smoother.


**Installing AngularJS**

AngularJS can be installed via a CDN.

CDN Installation: Include AngularJS directly in your HTML.

<script src="https://ajax.googleapis.com/ajax/libs/angularjs/1.8.0/angular.min.js"></script>


**Your First AngularJS Application**

Create a basic "Hello World" AngularJS app.
```jsx
    <!DOCTYPE html>
    <html lang="en" ng-app="myApp">
    <head>
      
      <title>Hello AngularJS</title>
      <script src="https://ajax.googleapis.com/ajax/libs/angularjs/1.8.0/angular.min.js"></script>
    </head>
    <body>
      <div ng-controller="myCtrl">
        <h1>{{ greeting }}</h1>
      </div>
      <script>
        angular.module('myApp', [])
          .controller('myCtrl', function($scope) {
            $scope.greeting = 'Hello, AngularJS!';
          });
      </script>
    </body>
    </html>
```
**Output**
```jsx
Hello, AngularJS!
```

## AngularJS Expressions
Double braces can be used to enclose AngularJS expressions.

Expressions in Angular are much like JavaScript expressions: They can contain literals, operators, and variables. Here is an example:

```jsx
<!DOCTYPE html>
<html>
<script src="https://ajax.googleapis.com/ajax/libs/angularjs/1.6.9/angular.min.js"></script>
<body>
<div ng-app="">
  <p>This is an expression: {{ 1.5 * 5 }}</p>
</div>
</body>
</html> 
```
This gives the following output:
```jsx
This is an expression: 7.5
```

## AngularJS Modules
AngularJS modules are used to organize related parts of your app, like components, services, or filters, so they can work together. This helps keep the app well-structured and easy to manage.

You can create an AngularJS module using the angular.module function. After creating the module (your app), you can add things like controllers (which manage data), directives (which add special features to HTML), and filters (which format data) to build your application.For example, we can add a controller with the ng-controller directive:

```jsx
<!DOCTYPE html>
<html>
<head>
  <script src="https://ajax.googleapis.com/ajax/libs/angularjs/1.8.2/angular.min.js"></script>
</head>
<body>

<div ng-app="exampleApp" ng-controller="myCtrl">
  {{ firstName + " " + lastName }}
</div>

<script>
var app = angular.module("exampleApp", []);
app.controller("myCtrl", function($scope) {
  $scope.firstName = "John";
  $scope.lastName = "Doe";
});
</script>

</body>
</html>

```
**Output**
```jsx
John Doe
```


##  Directives

Directives in AngularJS are like special commands that make HTML more powerful. They help you add new features or behavior to your webpage. For example, ng-repeat shows a list of items.

You can use directives inside HTML tags or attributes, and AngularJS comes with many built-in ones that are easy to use.

**Some directives include:**
 - ng-app directive initializes an AngularJS application
 - ng-init directive initializes the data in the application
 - The ng-model directive is used to bind some value of an HTML control to application data.
   
 Let us see these directives in action:
```jsx
<!DOCTYPE html>
<html>
<head>
  <script src="https://ajax.googleapis.com/ajax/libs/angularjs/1.8.2/angular.min.js"></script>
</head>
<body>

<div ng-app="" ng-init="firstName='John'">
  <p>Name: <input type="text" ng-model="firstName"></p>
  <p>You wrote: {{ firstName }}</p>
</div>

</body>
</html>

```
**Output**
```jsx
Name: John

You wrote: John
```

## AngularJS Filter

AngularJS filters allow users to format data in the user interface without altering the original format. 


 - currency: Used to format a number to a currency format
 - date: Used to format a date to some format
 - limitTo: Used to limit an array/string, into a specific number of elements/characters
 - lowercase: Used to format a string to lower case
 - number: Can format a numerical value to a string
 - orderBy: Sorts an array by an expression
 - uppercase: Used to format a string to upper case.

   
 Filters in AngularJS can be added to expressions used in the pipeline | character followed by a filter.
 
 Let's look at an example:
 
```jsx
<!DOCTYPE html>
<html>
<head>
  <script src="https://ajax.googleapis.com/ajax/libs/angularjs/1.8.0/angular.min.js"></script>
</head>
<body ng-app="exampleApp" ng-controller="exampleController">

  <!-- Currency Filter -->
  <h2>Currency Filter</h2>
  <p>Amount: {{ amount | currency }}</p>

  <!-- Date Filter -->
  <h2>Date Filter</h2>
  <p>Today's Date: {{ today | date:'fullDate' }}</p>

  <!-- LimitTo Filter -->
  <h2>LimitTo Filter</h2>
  <p>Limited Names: {{ names | limitTo:2 }}</p>

  <!-- Lowercase Filter -->
  <h2>Lowercase Filter</h2>
  <p>Lowercase Name: {{ name | lowercase }}</p>

  <!-- Number Filter -->
  <h2>Number Filter</h2>
  <p>Formatted Number: {{ number | number}}</p>

  <!-- OrderBy Filter -->
  <h2>OrderBy Filter</h2>
  <p>Sorted Names: <span ng-repeat="name in names | orderBy">{{ name }} </span></p>

  <!-- Uppercase Filter -->
  <h2>Uppercase Filter</h2>
  <p>Uppercase Name: {{ name | uppercase }}</p>

  <script>
    var app = angular.module("exampleApp", []);
    app.controller("exampleController", function($scope) {
      $scope.amount = 1234.56; // Example amount
      $scope.today = new Date(); // Current date
      $scope.names = ["John", "Jane", "Doe"]; // List of names
      $scope.name = "AngularJS"; // Example name
      $scope.number = 1234567.89; // Example number
    });
  </script>

</body>
</html>


```

**Output**
```jsx
Currency Filter
Amount: $1,234.56

Date Filter
Today's Date: Wednesday, September 11, 2024

LimitTo Filter
Limited Names: ["John","Jane"]

Lowercase Filter
Lowercase Name: angularjs

Number Filter
Formatted Number: 1,234,567.89

OrderBy Filter
Sorted Names: Doe Jane John
Uppercase Filter
Uppercase Name: ANGULARJS
```

## AngularJS - Tables

Table data is generally repeatable. The ng-repeat directive can be used to draw table easily. 
The following example shows the use of ng-repeat directive to draw a table −

```jsx
<!DOCTYPE html>
<html>
<head>
  <script src="https://ajax.googleapis.com/ajax/libs/angularjs/1.8.2/angular.min.js"></script>
</head>
<body>

<div ng-app="exampleApp" ng-controller="exampleController">
  <table border="1">
     <tr>
        <th>Name</th>
        <th>Marks</th>
     </tr>
     
     <tr ng-repeat="subject in student.subjects">
        <td>{{ subject.name }}</td>
        <td>{{ subject.marks }}</td>
     </tr>
  </table>
</div>

<script>
var app = angular.module("exampleApp", []);
app.controller("exampleController", function($scope) {
  $scope.student = {
    subjects: [
      { name: "Mathematics", marks: 90 },
      { name: "Physics", marks: 85 },
      { name: "Chemistry", marks: 78 },
      { name: "Biology", marks: 88 }
    ]
  };
});
</script>

</body>
</html>
```
**Output**
```jsx
Name	        Marks
Mathematics	  90
Physics	      85
Chemistry	    78
Biology	      88
```

## Pipes

Pipes transform data in the template. Angular provides built-in pipes for common data transformations like date formatting, currency conversion, and more.

**Example**

```jsx
<!DOCTYPE html>
<html>
<head>
  <script src="https://ajax.googleapis.com/ajax/libs/angularjs/1.8.2/angular.min.js"></script>
</head>
<body>

<div ng-app="exampleApp" ng-controller="exampleController">
  <h2>Uppercase Filter Example</h2>
  <p>Original Text: {{ message }}</p>
  <p>Uppercase Text: {{ message | uppercase }}</p>
</div>

<script>
var app = angular.module("exampleApp", []);
app.controller("exampleController", function($scope) {
  $scope.message = "Hello, AngularJS!";
});
</script>

</body>
</html>

```
**Output**
```jsx
Uppercase Filter Example
Original Text: Hello, AngularJS!

Uppercase Text: HELLO, ANGULARJS!
```

## AngularJS Events

An Events in AngularJS can be used to perform particular tasks, based on the action taken. Both Angular Event & the HTML Event will be executed & will not overwrite with an HTML Event. It can be added using the Directives mentioned below:

- ng-mousemove: The movement of the mouse leads to the execution of the event.
- ng-mouseenter: Click of the mouse button leads to the execution of the event.
- ng-mouseover: Hovering the mouse leads to the execution of the event.
- ng-keypress: Press of key leads to the execution of the event.
- ng-click: Single click leads to the execution of the event.
- ng-dblclick: Double click leads to the execution of the event.
- ng-mouseleave: It is used to apply custom behavior when a mouse-leave event occurs on a specific HTML element.

Example:

 ```jsx
<!DOCTYPE html> 
<html> 
  
<head> 
    <script src= 
"https://ajax.googleapis.com/ajax/libs/angularjs/1.6.9/angular.min.js"> 
    </script> 
</head> 
  
<body> 
    <p> 
        Click on button to  
          increase the Total Count.  
    </p> 
    <div ng-app="App1" 
         ng-controller="Ctrl1"> 
        <button ng-click="count = count + 1"> 
             button  
        </button> 
        <h2>Total Count:</h2> 
        <h2>{{ count }}</h2>  
    </div> 
    <script> 
        var app = angular.module('App1', []); 
        app.controller('Ctrl1', function($scope) { 
            $scope.count = 0; 
        }); 
    </script> 
</body> 
</html>
```
**Output**
```jsx
Click on button to increase the Total Count.

button

Total Count:
3
```
## References

https://www.w3schools.com/angular/

https://www.microverse.org/blog/angularjs-the-complete-guide-for-beginners

https://www.geeksforgeeks.org/angularjs/
