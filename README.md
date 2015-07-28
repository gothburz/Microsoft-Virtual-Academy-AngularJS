# Microsoft Virtual Academy - AngularJS 

These are my personal notes taken on the [Microsoft Virtual Academy](http://www.microsoftvirtualacademy.com/) course on AngularJS. These notes also include expanded definitions, core principles of computer science and programming to understand what is happening --*under the hood*  of Angular, leading to a much better understanding of the *how, why, & what*. I have also included specific links to the API in relevant situations.

If you don't want to watch don't fret these notes also serve as an ANgularJS cheatsheet!

Notes taken using [StackEdit](https://stackedit.io/) - Full-featured, open-source Markdown editor.

Check out the entire MVA course for yourself!

[Microsoft Training Course on AngularJS](http://www.microsoftvirtualacademy.com/training-courses/introduction-to-angularjs)  
[Github Demo and Course Files](https://github.com/MicrosoftLearning/MVAAngular)

Feel free to fork, modify, and share these along your own programming learning journey. Most importantly have fun with it!

Cheers,

Petrus Rex


##What is AngularJS?


- Front End JavaScript framework for creating dynamic web applications.
- Open source and maintained by Google.
	- Initial release 2009.
	- Stable release 1.4.3 / July 15, 2015.

- MVC pattern (Model-View-Controller)<br>
	- *Model–view–controller (MVC) is a software architectural pattern for implementing user interfaces. It divides a given software application into three interconnected parts, so as to separate internal representations of information from the ways that information is presented to or accepted from the user.*

Here is an in depth definition of [Model–view–controller(MVC)](http://www.tomdalling.com/blog/software-design/model-view-controller-explained/).

![MVC](http://i.stack.imgur.com/ocEWx.png)

- Handles common ( and often trying tasks ) such as DOM manipulation, updating UI based on data or input, registering callbacks. 
- Declarative programming 


##Why use AngularJS?

- Good for dynamic websites/ web apps (CRUD) based.
- Framework imposes structure that is good for organization. 
- Helps create responsive, fast, and efficient websites.
- Easy to Test --- creates software that is easy to maintain.
	- Was built to be highly testable.
	- Can be broken down into pieces easily (easy to manage).

What is CRUD? 

 - Create 
 - Read 
 - Update 
 - Delete

_In computer programming **CRUD** refers to the four basic types of **persistent** storage._
<br><br>
**Persistence**: _In computer science **persistence** refers to the characteristic of state that outlives the process that created it._ 

- See [persistence (computer science)](https://en.wikipedia.org/wiki/Persistence_(computer_science)) for more info.

**Crud**: Database - Applications

_The acronym **CRUD** refers to all of the major functions that are implemented in relational database applications. Each letter in the acronym can map to a standard SQL statement, HTTP method or DDS operation:_

| **Operation** | **SQL** | **HTTP** | **DDS** |
| --------------- | --------- | ---------- | --------- |
| Create         |Insert   | Put/Post |  Write  |
| Read (Retrive) |Select   | Get      |  Read/Take |
| Update (Modify) | Update  | Put/Patch |  Write      |
| Delete (Destroy) | Delete | Delete   |  Dispose    |


###Declarative Programming

_In computer science, **declarative programming** is a programming paradigm, a style of building the structure and elements of computer programs, that expresses the logic of a computation without describing its control flow. _

- See [declarative programming](https://en.wikipedia.org/wiki/Declarative_programming) for more info.

####Example

**AngularJS**

<pre class="prettyprint">
&lt;body ng-app="spicyApp2"&gt;
&nbsp;&nbsp;&nbsp;&lt;div ng-controller="SpicyController"&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;input ng-model="customSpice"&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;button ng-click="spicy('chili')"&gt;Chili&lt;/button&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;button ng-click="spicy(customSpice)"&gt;Custom Spice&lt;/button&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;p>The food is {{spice}} spicy!&lt;/p&gt;
&nbsp;&nbsp;&nbsp;&lt;/div&gt;
&lt;/body&gt;
</pre>

**jQuery**

<pre class="prettyprint">
&lt;body ng-app="spicyApp2"&gt;
&nbsp;&nbsp;&nbsp;&lt;div&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;input&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;button &gt;Chili&lt;/button&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;button&gt;Custom Spice&lt;/button&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;p>The food is spicy!&lt;/p&gt;
&nbsp;&nbsp;&nbsp;&lt;/div&gt;
&lt;/body&gt;
</pre>

*The intention of the application is expressed or __declared__ in the HTML for AngularJS.*

---

##Getting Started - How does AngularJS Work?

- AngularJS will initialize when the DOM content is loaded.
	- Document Object Model (DOM)  is a programming interface for HTML, XML and SVG documents. It provides a structured representation of the document (a tree) and it defines a way that the structure can be accessed from programs so that they can change the document structure, style and content.

	- See [DOM(Document Object Model)](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model) for more info.

- Looks for **ng-app** directive - if its found, that is the root or root scope of the app. 

- Directives can be declared  in a variety of ways typically with the **ng-** prefix, but you can use **data-ng**.
	- **ng-** simply stands for angular.
		- **data-*** was introduced in HTML5.
		-  **data-*** attributes is used to store custom data private to the page or application.
		- **data-*** attributes gives us the ability to embed custom data attributes on all HTML elements.
		- use **data-*** as a safety net for support on older browsers, most modern browsers support simply using the **ng-** prefix.
		- see more on [data-*](http://www.w3schools.com/tags/att_global_data.asp) for best practices and other information.

- It will load the module associated with the directive if specified.

###Getting Started - Bootstrapping

![Bootstrap](https://docs.angularjs.org/img/guide/concepts-startup.png)

See  [Bootstrapping AngularJS](https://docs.angularjs.org/guide/bootstrap) in the Angular API for more info on the initialization process.

####Dependency Injection

[Dependency Injection (DI)](https://docs.angularjs.org/guide/di) is a software design pattern that deals with how components get hold of their dependencies.


The Angular injector subsystem is in charge of creating components, resolving their dependencies, and providing them to other components as requested. 

![Dependancy Injection (DI)](https://docs.angularjs.org/img/guide/concepts-module-injector.png)

Check out [Understanding dependency injection](https://github.com/angular/angular.js/wiki/Understanding-Dependency-Injection) which has an excellent resource on understanding dependency injection in Angular. 


###Two-Way Data Binding

*Remember Model-View-Controller (MVC)?*

In AngularJS the **view** (what the user sees) and **model** (data) is intertwined (bound together), the model or *data* is accessed by the **controller**.  In terms of AngularJS think of the view as a reflection of the current model state. This is highly efficient and powerful!

![Two-Way Data Binding](https://docs.angularjs.org/img/Two_Way_Data_Binding.png)

Read more on [AngularJS Data Binding](https://docs.angularjs.org/guide/databinding) from the API.

##What are AngularJS Modules?

### Modules

- AngularJS [Module API](https://docs.angularjs.org/guide/module)
- Modules are:
	- Containers for various parts of your application (controllers, services, filters, directives, etc.)
	- Declarative - easy to understand
    - Maintainable, readable, testable
    - Define App dependencies
- Modules are usually organized around a specific feature and may contain several functions an example would be a contact form.

###Setting up Modules

- A module is comprised of configuration and run blocks.
	- In computer programming a block is a section of code which is grouped together. Blocks consist of one or more declarations and statements. A programming language that permits the creation of blocks, including blocks nested within other blocks, is called a **block-structured programming language**. 
	- [Block (programming)](https://en.wikipedia.org/wiki/Block_(programming))
- Configuration blocks *(configurations and settings are run)* - executed during and registration. Only providers and constants can be passed.
	- [Provider API](https://docs.angularjs.org/guide/providers)
- Run blocks *(main app fires off)* - happen after the injector is created. Only instances and constants can be passed.
- Some convenience methods for this.
- Run blocks is like a main method - it kickstarts the application.
- Modules can depend on other modules.
- They are only loaded once.

###Module Loading & Dependencies

####Example:
<pre class="prettyprint">angular.module('myModule', []).
config(function(injectables) { // provider-injector
  // This is an example of config block.
  // You can have as many of these as you want.
  // You can only inject Providers (not instances)
  // into config blocks.
}).
run(function(injectables) { // instance-injector
  // This is an example of a run block.
  // You can have as many of these as you want.
  // You can only inject instances (not Providers)
  // into run blocks
});</pre>
<br>
#### Example Breakdown 
- myModule is the name of the Angular module. - Naming convention for Angular modules is lowerCamelCase (myModule). - [] in the above example is the **dependencies** for the module. This example has none so it is an empty array. 
<br>
#### View entire [Module API](https://docs.angularjs.org/guide/module) 
<hr>
###Creating an AngularJS Module
<br>
- organize your module by functionality or component type.

<pre class="prettyprint">/*Angular Modules take a name, best practice is lowerCamelCase, and a list of dependancies*/

angular.module('mainApp', [])
.config([function () {
	/* Configuration is where you configure providers ( not instances) */
	console.log("Configuration hook")
}])
.run([function () {
	/* Run is when the app gets kicked off */
	console.log("Run hook");
}])</pre>
<br>

###Example Breakdown
<br>
- mainApp is the name of the Angular module.
- [] in the above example is the **dependencies** for the module. This example has none so it is an empty array.

###Module Architecture

- Modules for each feature
- Modules for each reusable component
- Application level module with module dependencies. 

---

##AngularJS Controllers

###What is a controller?

 - A controller is a set of JavaScript functions bound to a scope *(area it should execute in)*.
 - The **ng-controller** directive tells Angular to instantiate *(instance)*  the new controller object, and inject the new scope as a dependency. 
	- In [object-oriented programming (OOP)](http://searchsoa.techtarget.com/definition/object-oriented-programming), an *instance* is a specific realization of any object. Formally, "instance" is synonymous with "object" as they are each a particular value (realization), and these may be called an instance object; "instance" emphasizes the distinct identity of the object. The creation of an instance is called instantiation.
	- [Instance (computer science)](http://whatis.techtarget.com/definition/instance)


 - Contain business logic for the view
 - Best for adding logic
 - Avoid using to manipulate the DOM

##Creating a Controller

- Requires **ng-controller** directive
- Add controller code to module
- Controllers are named using upper CamelCase
- Name your controller based on functionality E.g. (NavCtrl)
- Keep controllers lean & organized
- you can have multiple controllers on a page
- you can nest controllers within controllers.

###Example Controller:

**HTML:**
<pre class="prettyprint">
&lt;body ng-app="mainApp"&gt;
    <!-- Navigation -->
    &lt;nav ng-controller="EventCtrl" class="navbar navbar-inverse navbar-fixed-top" role="navigation"&gt;
        &lt;div class="container"&gt;
            <!-- Brand and toggle get grouped for better mobile display -->
            &lt;div class="navbar-header"&gt;
                &lt;button type="button" class="navbar-toggle" data-toggle="collapse" data-target="#bs-example-navbar-collapse-1"&gt;
                    &lt;span class="sr-only">Toggle navigation&lt;/span>
                    &lt;span class="icon-bar">&lt;/span&gt;
                    &lt;span class="icon-bar">&lt;/span&gt;
                    &lt;span class="icon-bar">&lt;/span&gt;
                &lt;/button&gt;
                &lt;a class="navbar-brand" href="#"&gt;{{title}}&lt;/a&gt;
            &lt;/div&gt;
            <!-- Collect the nav links, forms, and other content for toggling -->
            &lt;div class="collapse navbar-collapse" id="bs-example-navbar-collapse-1"&gt;
                &lt;ul class="nav navbar-nav"&gt;
                    &lt;li class="active">
                        &lt;a href="{{menu[0].href}}"&gt;{{menu[0].name}}&lt;/a&gt;
                    &lt;/li>
                    &lt;li>
                        &lt;a href="{{menu[1].href}}"&gt;{{menu[1].name}}&lt;/a&gt;
                    &lt;/li&gt;
                &lt;/ul&gt;
            &lt;/div&gt; 
            <!-- /.navbar-collapse -->
        &lt;/div&gt;
        <!-- /.container -->
    &lt;/nav&gt;
    &lt;/body"&gt;
</pre>

**Module mainAPP:**

<pre class="prettyprint">
/*Angular Modules take a name, best practice is lowerCamelCase, and a list of dependancies*/
/*added the second module as a dependancy */

angular.module('mainApp', ['eventModule'])
.config([function () {
	/* Configuration is where you configure providers ( not instances)*/
	console.log("Configuration hook")
}])
.run([function () {
	/* Run is when the app gets kicked off*/
	console.log("Run hook");
}])
</pre>

 - Notice that we passed eventModule as a dependancy of mainApp!

<br>
**Module eventModule:**

<pre class="prettyprint">

(function(){

angular.module('eventModule', [])
.config([function () {
	console.log("Event Module:: config");
}])
.run([function () {
	console.log("Event Module::running");
}])
.controller('EventCtrl', ['$scope', function ($scope) {
	$scope.title = "Young Game Maker";
	$scope.menu=[
		{
			name:"Events",
			href:"index.html"
		},
		{
			name:"Contact",
			href:"contact.html"
		}
	]
}])

})();
</pre>

 - In the module **eventModule** we created the controller **EventCtrl**.
 - Go back up to the **HTML** document and see that **EventCtrl** is bound to the **&lt;nav&gt;** tag 
	 - Any element operating inside<br><pre>&lt;nav ng-controller="EventCtrl"&gt;&lt;/nav&gt;</pre> is functioning within the *scope* of **EventCtrl**.
	 - 
 - Think of **scope** as the *area of operation*.
 - Look at the **data-binding**: <pre>&lt;a class="navbar-brand" href="#">{{title}}&gt;</pre>
	 - {{title}} in the HTML document is bound to **EventCtrl**, we can see in the **eventModule** which contains our controller that **$scope.title** is Young Game Maker and will be rendered so to the *view*.

 - Same here <pre> &lt;a href="{{menu[0].href}}"&gt;{{menu[0].name}}&lt;/a&gt;<br>
   &nbsp;&lt;a href="{{menu[1].href}}"&gt;{{menu[1].name}}&lt;/a&gt;</pre>
	   - {{menu}} is bound to array **$scope.menu** also found within **EventCtrl**.
 
 _These bound items will display the information found in our **eventModule** to the browser view, in this example on the navbar specifically._

If for example you change **$scope-title** in your JS file you can truly can see the power of AngularJS in that when you change information in the **controller** the **view** will update as well. To do this maneuver with jQuery alone for example would take take tons of lines of code!<br><br>
In the big picture the **view** is what the user sees, you can take that a step further and break the webpage up into pieces. In the above example we were working with the navbar specifically that's a view and had its own controller, you can create a controller for any number of elements on the page the footer, an image, a single div etc.

![MVC](http://mnikoo.files.wordpress.com/2010/07/slide2_thumb2.png?w=980&h=740)<br>
####Still Lost? Take a moment to relook at [Model–view–controller(MVC)](http://www.tomdalling.com/blog/software-design/model-view-controller-explained/).

###Adding Behavior

Once again we *stored* data properties on the **scope** object within the **controller**. You can also add behavior by adding functions, properties, or WHATEVER. 

<pre>
&lt;body ng-app="mainApp"&gt;
    <!-- Navigation -->
    &lt;nav ng-controller="EventCtrl" class="navbar navbar-inverse navbar-fixed-top" role="navigation"&gt;
        &lt;div class="container"&gt;
            <!-- Brand and toggle get grouped for better mobile display -->
            &lt;div class="navbar-header"&gt;
                &lt;button type="button" class="navbar-toggle" data-toggle="collapse" data-target="#bs-example-navbar-collapse-1"&gt;
                    &lt;span class="sr-only">Toggle navigation&lt;/span>
                    &lt;span class="icon-bar">&lt;/span&gt;
                    &lt;span class="icon-bar">&lt;/span&gt;
                    &lt;span class="icon-bar">&lt;/span&gt;
                &lt;/button&gt;
                &lt;a class="navbar-brand" href="#"&gt;{{title}}&lt;/a&gt;
            &lt;/div&gt;
            <!-- Collect the nav links, forms, and other content for toggling -->
            &lt;div class="collapse navbar-collapse" id="bs-example-navbar-collapse-1"&gt;
                &lt;ul class="nav navbar-nav"&gt;
                    &lt;li ng-click="setIndex(0)" ng-class="(index===0) ? 'active' : ''">
                        &lt;a href="{{menu[0].href}}"&gt;{{menu[0].name}}&lt;/a&gt;
                    &lt;/li>
                    &lt;li  ng-click="setIndex(1)"  ng-class="(index===1) ? 'active' : ''">
                        &lt;a href="{{menu[1].href}}"&gt;{{menu[1].name}}&lt;/a&gt;
                    &lt;/li&gt;
                &lt;/ul&gt;
            &lt;/div&gt; 
            <!-- /.navbar-collapse -->
        &lt;/div&gt;
        <!-- /.container -->
    &lt;/nav&gt;
    &lt;/body"&gt;
</pre>
<pre>
(function(){

angular.module('eventModule', [])
.config([function () {
	console.log("Event Module:: config");
}])
.run([function () {
	console.log("Event Module::running");
}])
.controller('EventCtrl', ['$scope', function ($scope) {
	$scope.title = "Young Game Maker";

	$scope.menu=[
		{
			name:"Events",
			href:"index.html"
		},
		{
			name:"Contact",
			href:"contact.html"
		}
	]

	$scope.index = 0;

	$scope.setIndex=function(val)
	{
		$scope.index = val;
		
	}

	$scope.getIndex=function(){
		return($scope.index);
	}
}])

})();</pre>

-	Above we passed two dummy functions to demonstrate adding behavior to AngularJS.
-	We added the **ng-click** directive to *listen* for user clicks.
-	We then added the **ng-class** directive to *change* the class when the user *clicks* a menu item to active using [Bootstraps](http://getbootstrap.com/) active class.
-	We did the same thing that JavaScripts **addEventListener()**  or jQuerys **click()** method does but in a much simpler and efficient manner.
-	Remember **Declarative Programming**? The intention of the application is  **declared** in the HTML for AngularJS.
-	Love Angular yet?

####SideNote
if  you're wondering about the question mark: <pre>ng-class="(index===0) ? 'active' : ''"</pre> <br>
It's a simple shorthand **if/else** statement that in computer science is called a [ternary operator](https://en.wikipedia.org/wiki/%3F:). 
<br>

**if**<pre>(index===0){'active'
}</pre> change class to active. 
<br>

**else**<pre>''"</pre> do nothing. 
<hr>
##What is $scope?
- **$scope** is an object that refers back to the app model
- **$scope** provides the [execution context](http://davidshariff.com/blog/what-is-the-execution-context-in-javascript/) for expressions
	- think of execution context as the environment / scope the current code is being evaluated in
- **$scope** is the glue between the **controller** and **view**
- attach properties and functions to scope to make them available to the view
- any objects or primitives that is added to **$scope** are considered model properties.

View the AngularJS API on [scopes](https://docs.angularjs.org/guide/scope) for more info.
###Understanding Scope

- Child scopes prototypically inherit
- Isolate scopes do not
- JavaScript Prototypical Inheritance: If it doesn't exist in current, it will go up the chain (parent). Hiding and shadowing of properties.
- Best practice of always have a "**.**" in models.
- Wiki on [Understanding Scopes](https://github.com/angular/angular.js/wiki/Understanding-Scopes) in AngularJS.
- API on [Inheritance and the Prototype Chain](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Inheritance_and_the_prototype_chain) in JavaScript.
<br>
###Multiple Controllers 
<br>
<pre> &lt;nav ng-controller="EventCtrl" class="navbar navbar-inverse navbar-fixed-top" role="navigation"&gt;
        &lt;div class="container"&gt;
            <!-- Brand and toggle get grouped for better mobile display -->
            &lt;div class="navbar-header"&gt;
                &lt;button type="button" class="navbar-toggle" data-toggle="collapse" data-target="#bs-example-navbar-collapse-1"&gt;
                    &lt;span class="sr-only">Toggle navigation&lt;/span&gt;
                    &lt;span class="icon-bar">&lt;/span&gt;
                    &lt;span class="icon-bar">&lt;/span&gt;
                    &lt;span class="icon-bar">&lt;/span&gt;
                &lt;/button>
                &lt;a class="navbar-brand" href="#">{{title}}&lt;/a&gt;
            &lt;/div&gt;
            <!-- Collect the nav links, forms, and other content for toggling -->
            &lt;div class="collapse navbar-collapse" id="bs-example-navbar-collapse-1"&gt;
                &lt;ul class="nav navbar-nav"&gt;
                    &lt;li  ng-click="setIndex(0)" ng-class="(index==0) ? 'active' : ''"&gt;
                      &lt;a href="#">{{menu[0].name}}&lt;/a&gt;
                    &lt;/li&gt;
                    &lt;li ng-click="setIndex(1)"  ng-class="(index==1) ? 'active' : ''"&gt;
                        &lt;a href="#">{{menu[1].name}}&lt;/a&gt;
                    &lt;/li&gt;

                    &lt;li>&lt;a href="#"&gt; {{title}}&lt;/a>&lt;/li&gt;
                &lt;/ul&gt;
            &lt;/div&gt;
            &lt;!-- /.navbar-collapse --&gt;
        &lt;/div&gt;
        &lt;!-- /.container --&gt;
    &lt;/nav&gt;

    &lt;!-- Page Content --&gt;
    &lt;div class="container"&gt;

        &lt;!-- Portfolio Item Heading --&gt;
        &lt;div class="row"&gt;
            &lt;div class="col-lg-12"&gt;
                &lt;h1 class="page-header">New York 
                    &lt;small>January 24th, 2015&lt;/small&gt;
                &lt;/h1&gt;
            &lt;/div&gt;
        &lt;/div&gt;
        &lt;!-- /.row --&gt;

        &lt;!-- Portfolio Item Row --&gt;
        &lt;div class="row" ng-controller="EventItemCtrl"&gt;

            &lt;div class="col-md-8"&gt;
                &lt;img class="img-responsive" src="assets/img/newyork_big.jpg" alt=""&gt;
            &lt;/div&gt;

            &lt;div class="col-md-4"&gt;
                &lt;h3&gt;{{itemTitle}}&lt;/h3&gt;
                &lt;p&gt;{{description}}&lt;/p&gt;
                &lt;h3&gt;Details&lt;/h3&gt;
                &lt;ul class="nav nav-tabs"&gt;
                     &lt;li class="active">&lt;a href="#">Schedule&lt;/a&gt;
                     &lt;/li&gt;
                    &lt;li&gt;&lt;a href="#">Tickets&lt;/a>&lt;/li&gt;
                    &lt;li&gt;&lt;a href="#">Location&lt;/a&gt;&lt;/li&gt;
                    
                &lt;/ul&gt;
                &lt;div&gt;CONTENT FOR TABS GO HERE&lt;/div&gt;
            &lt;/div&gt;

        &lt;/div&gt;</pre>
        
<pre>(function(){

angular.module('eventModule', [])
.config([function () {
	console.log("Event Module:: config");
}])
.run([function () {
	console.log("Event Module::running");
}])
.controller('EventCtrl', ['$scope', function ($scope) {
	$scope.title = "Young Game Maker";
	$scope.menu=[
		{
			name:"Events",
			href:"index.html"
		},
		{
			name:"Contact",
			href:"contact.html"
		}
	]

	$scope.index = 0;

	$scope.setIndex=function(val)
	{
		$scope.index = val;
		console.log("called")
	}

	$scope.getIndex=function(){
		return($scope.index);
	}
	
}])
.controller('EventItemCtrl', ['$scope', function ($scope) {
	$scope.itemTitle="Young Game Makers in NYC";
	$scope.description="Young Game Makers is a one day event that teaches kids how to code";
	$scope.imgSrc ="assets/img/newyork_large.jpg";
	$scope.date ="January 24, 2015";

	
}])


})();</pre>

Notice we have two **controllers**, we have **EventCtrl**, and **EventItemCtrl**. Each controller uses scope to contain *properties*. These properties are then displayed in the browser because we have them bound to our **view**.

<pre>&lt;div class="spicy" &gt;
   &lt;div ng-controller="MainController"&gt;
     &lt;p&gt;Good {{timeOfDay}}, {{name}}! &lt;/p&gt;

     &lt;div ng-controller="ChildController"&gt;
       &lt;p&gt;Good {{timeOfDay}}, {{name}}! &lt;/p&gt;

       &lt;div ng-controller="GrandChildController"&gt;
         &lt;p&gt;Good {{timeOfDay}}, {{name}}! &lt;/p&gt;
       &lt;/div&gt;
     &lt;/div&gt;
   &lt;/div&gt;
 &lt;/div&gt;</pre>
 Taken straight from the AngularJS API this is an example of multiple **controllers**, nested **controllers**, **scope**, and **inheritance**.
<br>
- each controller has its own **scope** or *execution context*
- if for example **ChildController** does not have properties *timeOfDay* or *name* explicitly defined within its scope it will **INHERIT** them up the chain, in this case from **MainController**.
- Children will always inherit from the parent scope unless defined otherwise within their own controllers scope.
- you may explicitly call up in angular using ```$parent```
- More on [Controller API](https://docs.angularjs.org/guide/controller)
<br>


###Sharing Data

<pre>(function(){

angular.module('eventModule', [])
.factory('MainTitle', [function () {
	return {
		title:"Young Game Maker"
	};
}])
.config([function () {
	console.log("Event Module:: config");
}])
.run([function () {
	console.log("Event Module::running");
}])
.controller('EventCtrl', ['$scope', 'MainTitle',function ($scope,mainTitle) {
	$scope.title = mainTitle.title;
	$scope.menu=[
		{
			name:"Events",
			href:"index.html"
		},
		{
			name:"Contact",
			href:"contact.html"
		}
	]

	$scope.index = 0;

	$scope.setIndex=function(val)
	{
		$scope.index = val;
		console.log("called")
	}

	$scope.getIndex=function(){
		return($scope.index);
	}
	
}])
.controller('EventItemCtrl', ['$scope','MainTitle',  function ($scope,mainTitle) {
	$scope.itemTitle=mainTitle.title+" in NYC";
	$scope.description=mainTitle.title+" is a one day event that teaches kids how to code";
	$scope.imgSrc ="assets/img/newyork_large.jpg";
	$scope.date ="January 24, 2015";
}])
.controller('EventTabCtrl', ['$scope', function ($scope) {
	$scope.tab = 0;
	console.log("yes")
	$scope.setTab=function(val)
	{
		$scope.tab = val;
	}
	$scope.getTab=function(val)
	{
		return($scope.tab);
	}
	
}])


})();</pre>

- We used ```.factory``` within the module to store a title that we will use throughout. This makes it convenient in that if we need to change the title to something else we just have to change it here instead of every individual controller.
- We also see examples of **dependency injection** in our controllers, as we are injecting **MainTitle** as a dependency.
###"Controller as" syntax

- Defines a named scope
- Defines properties on the function Controller and not on the $scope 
- object ```$scope``` is still useful for things such as ```$watch```( watching to see if a property changes )

<pre>&lt;nav ng-controller="EventCtrl as event" class="navbar navbar-inverse navbar-fixed-top" role="navigation"&gt;
        &lt;div class="container"&gt;
            <!-- Brand and toggle get grouped for better mobile display -->
            &lt;div class="navbar-header"&gt;
                &lt;button type="button" class="navbar-toggle" data-toggle="collapse" data-target="#bs-example-navbar-collapse-1"&gt;
                    &lt;span class="sr-only">Toggle navigation&lt;/span&gt;
                    &lt;span class="icon-bar">&lt;/span&gt;
                    &lt;span class="icon-bar">&lt;/span&gt;
                    &lt;span class="icon-bar">&lt;/span&gt;
                &lt;/button>
                &lt;a class="navbar-brand" href="#">{{event.title}}&lt;/a&gt;
            &lt;/div&gt;
            <!-- Collect the nav links, forms, and other content for toggling -->
            &lt;div class="collapse navbar-collapse" id="bs-example-navbar-collapse-1"&gt;
                &lt;ul class="nav navbar-nav"&gt;
                    &lt;li  ng-click="setIndex(0)" ng-class="(index==0) ? 'active' : ''"&gt;
                      &lt;a href="#">{{event.menu[0].name}}&lt;/a&gt;
                    &lt;/li&gt;
                    &lt;li ng-click="setIndex(1)"  ng-class="(index==1) ? 'active' : ''"&gt;
                        &lt;a href="#">{{event.menu[1].name}}&lt;/a&gt;
                    &lt;/li&gt;

                    &lt;li>&lt;a href="#"&gt; {{event.title}}&lt;/a>&lt;/li&gt;
                &lt;/ul&gt;
            &lt;/div&gt;
            &lt;!-- /.navbar-collapse --&gt;
        &lt;/div&gt;
        &lt;!-- /.container --&gt;
    &lt;/nav&gt;

    &lt;!-- Page Content --&gt;
    &lt;div class="container"&gt;

        &lt;!-- Portfolio Item Heading --&gt;
        &lt;div class="row"&gt;
            &lt;div class="col-lg-12"&gt;
                &lt;h1 class="page-header">New York 
                    &lt;small>January 24th, 2015&lt;/small&gt;
                &lt;/h1&gt;
            &lt;/div&gt;
        &lt;/div&gt;
        &lt;!-- /.row --&gt;

        &lt;!-- Portfolio Item Row --&gt;
        &lt;div class="row" ng-controller="EventItemCtrl as eventitem"&gt;

            &lt;div class="col-md-8"&gt;
                &lt;img class="img-responsive" src="assets/img/newyork_big.jpg" alt=""&gt;
            &lt;/div&gt;

            &lt;div class="col-md-4"&gt;
                &lt;h3&gt;{{eventitem.itemTitle}}&lt;/h3&gt;
                &lt;p&gt;{{eventitem.description}}&lt;/p&gt;
                &lt;h3&gt;Details&lt;/h3&gt;
                &lt;ul class="nav nav-tabs"&gt;
                     &lt;li class="active">&lt;a href="#">Schedule&lt;/a&gt;
                     &lt;/li&gt;
                    &lt;li&gt;&lt;a href="#">Tickets&lt;/a>&lt;/li&gt;
                    &lt;li&gt;&lt;a href="#">Location&lt;/a&gt;&lt;/li&gt;
                    
                &lt;/ul&gt;
                &lt;div&gt;CONTENT FOR TABS GO HERE&lt;/div&gt;
            &lt;/div&gt;

        &lt;/div&gt;</pre>
<pre>(function(){

angular.module('eventModule', [])
.factory('MainTitle', [function () {
	

	return {
		title:"Young Game Maker"
	};
}])
.config([function () {
	console.log("Event Module:: config");
}])
.run([function () {
	console.log("Event Module::running");
}])
.controller('EventCtrl', ['$scope', 'MainTitle',function ($scope,mainTitle) {
	this.title = mainTitle.title;
	this.menu=[
		{
			name:"Events",
			href:"index.html"
		},
		{
			name:"Contact",
			href:"contact.html"
		}
	]

	this.index = 0;

	this.setIndex=function(val)
	{
		this.index = val;
		console.log("called")
	}

	this.getIndex=function(){
		return(this.index);
	}
	
}])
.controller('EventItemCtrl', ['$scope','MainTitle',  function ($scope,mainTitle) {
	this.itemTitle=mainTitle.title+" in NYC";
	this.description=mainTitle.title+" is a one day event that teaches kids how to code";
	this.imgSrc ="assets/img/newyork_large.jpg";
	this.date ="January 24, 2015";
}])
.controller('EventTabCtrl', ['$scope', function ($scope) {
	this.tab = 0;
	console.log("yes")
	this.setTab=function(val)
	{
		this.tab = val;
	}
	this.getTab=function(val)
	{
		return(this.tab);
	}
	
}])

})();</pre>
- we added "```as event```" to the **EventCtrl** in our HTML document
	- now if you wish to reference anything on the **EventCtrl** you need to use ```event``` for example we ```{{event.title}}```
- we used ```as event``` but you can use whatever as long as you use ```as```, for example ```as foo``` or ```as petrus```
- in the JavaScript file we replaced ```$scope``` with ```this```
	-  ```this``` simply attaches it to the **controller**
- instead of attaching these properties to the scope object we are attaching it to the controller itself.

##Expressions and Filters

- What are Expressions?
- What can we do with Expressions?
- Using Expressions
- What are Filters?
- Using Filters
- Creating a Custom Filter

###What is an Expression?

- JavaScript code snippets places in bindings **{{Hello World}}**
- Evaluated against a scope object
- Forgiving, doesn't throw an error
- Can use filters with expressions to format data
- Expressions do not have access to window, document, and location
- View [Expression API](https://docs.angularjs.org/guide/expression)

###What can you do with Expressions?

![AngularJS Expressions ](http://teropa.info/images/angular_expressions_cheatsheet.png)

###One time binding

**Why use One time Binding?**
It saves resources!
<br>
Straight from the AngularJS API: <br>*"The main purpose of one-time binding expression is to provide a way to create a binding that gets deregistered and frees up resources once the binding is stabilized. Reducing the number of expressions being watched makes the digest loop faster and allows more information to be displayed at the same time."*

[Angular Expressions](https://docs.angularjs.org/guide/expression)

**Example:**

```<a class="navbar-brand" href="#">{{::title}}</a>```

An expression that starts with ```::``` is considered a one-time expression.

###What are filters?

- Formats the value of an expression
- Filters can be applied in the view
```{{employees.array | filter: 's'}}```
- Filters applied in the view can be costly as they are re-evaluated
- Filters can be used elsewhere: controllers, services, etc.

###Built in Filters

- orderBy
- limitTo
- lower & uppercase
- filter
- currency
- number
- date

<br>
**Example:**
<br>
```p>{{item.date | date:'MMMM,dd yyyy'}}</p>```

<pre>&lt;div ng-repeat="item in event.events | orderBy: 'date'" class="col-sm-3 col-xs-6" &gt;
                &lt;a href="#" &gt;
                    &lt;img class="img-responsive portfolio-item" ng-src="assets/img/{{item.imgName}}_small.jpg" alt="" &gt;
                &lt;/a &gt;
                &lt;div &gt;
                    &lt;h4>{{item.title}}&lt;/h4 &gt;
                    &lt; &gt;{{item.date | date:'MMMM,dd yyyy'}}&lt;/p &gt;
                &lt;/div &gt;
            &lt;/div &gt;</pre>

<pre>.controller('EventCtrl', ['$scope', 'MainTitle',function ($scope,mainTitle) {
	this.title = mainTitle.title;
	console.log(this.title);
	this.menu=[
		{
			name:"Events",
			href:"index.html"
		},
		{
			name:"Contact",
			href:"contact.html"
		}
	]

	this.index = 0;
	this.eventIndex = 0;

	this.setIndex=function(val)
	{
		this.index = val;
		console.log("called")
	}

	this.getIndex=function(){
		return(this.index);
	}

	this.setEventIndex = function(val)
	{
		this.eventIndex = val;
	}
	this.getEventIndex = function(){
		return(this.eventIndex);
	}

	this.events=[
	{
		title : "New York",
		itemTitle:mainTitle.title,
		description:" is a one day event that teaches kids how to code",
		imgName:"newyork",
		date :Date.parse("January 24 2015")
	},
	{
		title: "Seattle",
		itemTitle:mainTitle.title,
		description:" is a one day event that teaches kids how to code",
		imgName:"seattle",
		date:Date.parse("February 24 2015")
	},
	{
		title: "San Francisco",
		itemTitle:mainTitle.title,
		description:" is a one day event that teaches kids how to code",
		imgName:"sanfran",
		date:Date.parse("April 24 2015")
	},
	{
		title : "Vancouver",
		itemTitle:mainTitle.title,
		description:" is a one day event that teaches kids how to code",
		imgName:"vancouver",
		date:Date.parse("March 24 2015")
	},
	{
		title : "Brighton",
		itemTitle:mainTitle.title,
		description:" is a one day event that teaches kids how to code",
		imgName:"brighton",
		date:Date.parse("September 24 2015")
	},

	{
		title: "London",
		itemTitle:mainTitle.title,
		description:" is a one day event that teaches kids how to code",
		imgName:"London",
		date:Date.parse("September 26 2015")
	},

	]
	
}])</pre>

- in the above example we are using the ```ng-repeat``` directive as a *template*
- basically ```ng-repeat``` is running a **for/each** loop.
- where ```event``` is our controller **EventCtrl** and ```events``` is our array located in our JS file.
- [ngRepeat API](https://docs.angularjs.org/api/ng/directive/ngRepeat)
- ```|``` means filter!

###Creating custom Filters

- Register a new filter factory function on the model
- Return a filter function that takes the input value as the first argument
- Filter function should be stateless typically

<pre>angular.module('eventModule', [])
.factory('MainTitle', [function () {
	

	return {
		title:"Young Game Maker"
	};
}])
.filter('searchCity', function() {
  return function(items,search) {
    var filtered = [];
    if(!search){return items;}
    angular.forEach(items, function(item) {

    	if(angular.lowercase(item.title).indexOf(angular.lowercase(search))!=-1)
    	{
    		filtered.push(item);
    	}
      
    });
   return filtered;
  };
})</pre>
<br>
**HTML:**
<br>
```<input type="text" ng-model="event.search" placeholder="Search by City">```

- In the JS file we created a custom filter that filters out information by city.
- we tied that filter to our view using an input field with ```ng-model``` attached.
	- The ```ng-model``` directive binds an input, select,  textarea (or custom form control) to a property on the scope using NgModelController, which is created and exposed by this directive.
	- more on [ng-model](https://docs.angularjs.org/api/ng/directive/ngModel)

##Directives

- What are Directives
- Built in Directives
- ng-include
- How Directives are instantiated
- Creating a Custom Directive
- Creating a Custom Directive Controller

###What are Directives, really?

- AngularJS directives are markers on the DOM that tell the Angular compiler to attach behaviour ot transform the DOM element
- Directives can be placed on the DOM as:
	- Element directives
	- Attribute directives
	- CSS class directives
	- Comment directives

###Types of Directives

- Element Directive
	- &lt;product-description>&lt;/product-description&gt;
- Attribute Directive
	- &lt;h3 product-description>&lt;/h3&gt;
- Comment Directive
	- &lt;product-description&gt;&lt;/product-description&gt;
- Class Directive
	- &lt;div class="product-description&gt;&lt;/div&gt;
<br>


###Built in Directives

- AngularJS provides a wealth of built in directives
- Some of these override built in HTML elements to provide additional functionality - like ```<form>```
- Other directives are visible through the ```ng-``` prefix

###Some built in Directives 

- ```ng-href```
- ```ng-src```
- ```ng-disabled```
- ```ng-checked```
- ```ng-class```
- ```ng-style```
- ```ng-selected```
- ```ng-app```
- ```ng-controller```
- ```ng-show```
- ```ng-hide```

###How Directives are Instantiated

- Angular's compiler scans the DOM looking for Directives
- Directives can be declared a few different ways
<br>
A valuable directive you will use frequently as your project grows is ```ng-include``` this allows us to break up our project in AngularJS into pieces.
<br>
A valuable directive you will use frequently as your project grows is ```ng-include``` this allows us to break up our project in AngularJS into pieces.

```<div ng-include src="'app/event/header.html'"></div>```

###Creating custom Directives

<pre>// directives
 .directive('eventItem', function () {
    return {
        restrict: 'E', //E = element, A = attribute, C = class, M = comment   
        templateUrl: 'app/event/eventItem.html',
        controller: function($scope){
            console.log("do stuff")

        }, //Embed a custom controller in the directive
        link: function ($scope, element, attrs) { } //DOM manipulation
    }
});</pre>
<br>
**HTML:**
<br>
```&lt;event-item&gt;&lt;/event-item&gt;```

- you need to restrict your directive
	- restricting means what is this element being used as?
	- see above example: E = element, A = attribute, C = class, M = comment
- ```templateUrl``` is simply a path to en external document
- <br>




