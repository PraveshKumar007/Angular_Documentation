# **ANGULAR**
<img src="Why-AngularJS-A1.jpg" alt="" style="width:100%;"/>


## Table of Content
- Introduction to AngularJS 
- Getting Started
- AngularJS Expressions
- AngularJS Modules
- Data Binding
- Directives in AngularJS
- AngularJS Filter
- AngularJS - Tables
- Pipes
- AngularJS Events
- References



## Introduction to AngularJS

### What is Angular?
Angular is a platform and framework for building single-page client applications using HTML and TypeScript. It is maintained by Google and offers a robust structure for developing dynamic web applications.


### Version History
**AngularJS (1.x):** This version was the first release of Angular, starting in 2010.

**Angular (2+):** Starting from Angular 2 in 2016. 

**Key Differences:**

- **AngularJS:** Older, with a focus on controllers and bidirectional data binding.
 
- **Angular:** Newer, with components, TypeScript support, and a unidirectional data flow.



## Getting Started

**Installing AngularJS**

AngularJS can be installed via a CDN or npm.
CDN Installation: Include AngularJS directly in your HTML.
<script src="https://ajax.googleapis.com/ajax/libs/angularjs/1.8.0/angular.min.js"></script>

**npm Installation**: Install AngularJS as a dependency.

**bash**
  ```jsx
    npm install angular@1.8.0
  ```

**Your First AngularJS Application**

Create a basic "Hello World" AngularJS app.
```jsx
    HTML (index.html):
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
A way to organize related components, directives, pipes, and services, allowing them to be combined with other modules to form applications.


An AngularJS module can be created using the angular.module function. Once you have created an app you can add controllers, directives and pipelines to your application. For example, we can add a controller with the ng-controller directive:

```jsx
<div ng-app="exampleApp" ng-controller="myCtrl">
{{ FirstName + " " + FastName }}
</div>
<script>
var app = angular.module("exampleApp", []);
app.controller("myCtrl", function($scope) {
  $scope.firstName = "John";
  $scope.lastName = "Doe";
});
</script> 
```

## Data Binding

In AngularJS, data binding refers to the synchronization of the model and the View. Applications using AngularJS typically have a data model. The data model is a set of information that the application can use. Data binding binds AngularJS expressions with AngularJS data.

We have already seen Data Binding in action. In the previous example, the {{ FirstName }} expression is an AngularJS data binding expression as it is bound with:

```jsx
ng-model="FirstName."
```

More specifically, you can usually use the ng-bind directive, which will bind the innerHTML of the element to the specified model property:

```jsx 
<p ng-bind="Firstname"></p>
```

Like the previous example, you can also display the content from the model using double braces {{ }}:

 ```jsx 
 <p>First name: {{Firstname}}</p>
```

##  Directives

Directives in AngularJS let you extend HTML by giving it new syntax. Each directive has a name; either one that is predefined by Angular, such as ng-repeat, or a custom name that can be anything. In addition, each directive specifies where it can be used, whether in an element, attribute, class, or comment.

AngularJS has many built-in directives which offer different functionalities and are defined using the ng- prefix. 
**Some directives include:**
 - ng-app directive initializes an AngularJS application
 - ng-init directive initializes the data in the application
 - The ng-model directive is used to bind some value of an HTML control to application data.
   
 Let us see these directives in action:
```jsx
<div ng-app="" ng-init="firstName='John'">
<p>Name: <input type="text" ng-model="firstName"></p>
<p>You wrote: {{ firstName }}</p>
</div>
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
div ng-app="exampleApp" ng-controller="exampleController">
<p>The name is {{ LastName | uppercase }}</p>
</div> 
```

## AngularJS - Tables

Table data is generally repeatable. The ng-repeat directive can be used to draw table easily. 
The following example shows the use of ng-repeat directive to draw a table −

```jsx
<table>
   <tr>
      <th>Name</th>
      <th>Marks</th>
   </tr>
   
   <tr ng-repeat = "subject in student.subjects">
      <td>{{ subject.name }}</td>
      <td>{{ subject.marks }}</td>
   </tr>
</table>
```
Table can be styled using CSS Styling.

```jsx
<style>
   table, th , td {
      border: 1px solid grey;
      border-collapse: collapse;
      padding: 5px;
   }
   table tr:nth-child(odd) {
      background-color: #f2f2f2;
   }
   table tr:nth-child(even) {
      background-color: #ffffff;
   }
</style>
```


The following example shows the use of all the above-mentioned directives.
```jsx
testAngularJS.htm
Live Demo
<html>
   <head>
      <title>Angular JS Table</title>
      <script src = "https://ajax.googleapis.com/ajax/libs/angularjs/1.3.14/angular.min.js"></script>
      
      <style>
         table, th , td {
            border: 1px solid grey;
            border-collapse: collapse;
            padding: 5px;
         }
         table tr:nth-child(odd) {
            background-color: #f2f2f2;
         }
         table tr:nth-child(even) {
            background-color: #ffffff;
         }
      </style>
   </head>
   
   <body>
      <h2>AngularJS Sample Application</h2>
      <div ng-app = "mainApp" ng-controller = "studentController">
         
         <table border = "0">
            <tr>
               <td>Enter first name:</td>
               <td><input type = "text" ng-model = "student.firstName"></td>
            </tr>
            <tr>
               <td>Enter last name: </td>
               <td>
                  <input type = "text" ng-model = "student.lastName">
               </td>
            </tr>
            <tr>
               <td>Name: </td>
               <td>{{student.fullName()}}</td>
            </tr>
            <tr>
               <td>Subject:</td>
               
               <td>
                  <table>
                     <tr>
                        <th>Name</th>.
                        <th>Marks</th>
                     </tr>
                     <tr ng-repeat = "subject in student.subjects">
                        <td>{{ subject.name }}</td>
                        <td>{{ subject.marks }}</td>
                     </tr>
                  </table>
               </td>
            </tr>
         </table>
      </div>
      
      <script>
         var mainApp = angular.module("mainApp", []);
         
         mainApp.controller('studentController', function($scope) {
            $scope.student = {
               firstName: "Mahesh",
               lastName: "Parashar",
               fees:500,
               
               subjects:[
                  {name:'Physics',marks:70},
                  {name:'Chemistry',marks:80},
                  {name:'Math',marks:65},
                  {name:'English',marks:75},
                  {name:'Hindi',marks:67}
               ],
               fullName: function() {
                  var studentObject;
                  studentObject = $scope.student;
                  return studentObject.firstName + " " + studentObject.lastName;
               }
            };
         });
      </script>
      
   </body>
</html>

```
## Pipes

Pipes transform data in the template. Angular provides built-in pipes for common data transformations like date formatting, currency conversion, and more.

**Using Built-in Pipes**

```jsx
<p>{{ birthday | date }}</p>

```
- **birthday** is a Date object in the component.
- **date** pipe formats the date.

**Output**

```jsx
Displays the formatted date of 'birthday'.

```

## AngularJS Events

An Events in AngularJS can be used to perform particular tasks, based on the action taken. Both Angular Event & the HTML Event will be executed & will not overwrite with an HTML Event. It can be added using the Directives mentioned below:

- ng-mousemove: The movement of the mouse leads to the execution of the event.
- ng-mouseup: Movement of the mouse upwards leads to the execution of the event.
- ng-mousedown: Movement of the mouse downwards leads to the execution of the event.
- ng-mouseenter: Click of the mouse button leads to the execution of the event.
- ng-mouseover: Hovering the mouse leads to the execution of the event.
- ng-keypress: Press of key leads to the execution of the event.
- ng-keyup: Press of upward arrow key leads to the execution of the event.
- ng-keydown: Press of downward arrow key leads to the execution of the event.
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

## References

https://www.w3schools.com/angular/

https://www.microverse.org/blog/angularjs-the-complete-guide-for-beginners

https://www.geeksforgeeks.org/angularjs/
