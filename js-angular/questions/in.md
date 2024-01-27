# Interview Questions

<details>
<summary>1. What is a module in Angular?</summary>

>**Answer:**
>NgModules are containers for a cohesive block of code dedicated to an application domain, a workflow, 
>or a closely related set of capabilities. They can contain components, service providers, and other code 
>files whose scope is defined by the containing NgModule. They can import functionality that is exported from 
>other NgModules, and export selected functionality for use by other NgModules.

</details>

<details>
<summary>2. What is the Decorator? List types of decorators, what is the role of decorator in Angular?</summary>

>**Answer:**
>In common words, decorator is a pattern that applies some functionality over existing one without 
>modifying. There are several types of Decorators such as Class, Function, Property, Argument. 
>Angular decorator works as a holder of metadata which could be applied to incorporate with Angular core functionality 
>and make it easier for developing applications.

</details>

<details>
<summary>3. What is Angular CLI and how to create pieces of Angular application using this tool?</summary>

>**Answer:**
>CLI stands for command line interface, its tools provide ways of creating an application and its parts 
>with the easy command to execute, such `ng generate component`, etc.

</details>

<details>
<summary>4. Describe please Angular application structure in general</summary>

>**Answer:**
>The simplest Angular application consists of configurations files (its availability depends 
>on the version of Angular ), for example, angular.json, eslint, and others. It also contains the entry file 
>from which the app will be built, a directory with root module “/app”, index.html, etc.

</details>

<details>
<summary>5. What kind of ngModule metadata fields do you know?</summary>

>**Answer:**
>* `declarations`: The components, directives, and pipes that belong to the current NgModule.
>* `exports`: The subset of declarations which should be visible and usable in component templates of other 
> NgModules.
>* `imports`: Other modules whose exported classes are needed by component templates declared in the current NgModule.
>* `providers`: Creators of services which this NgModule contributes to the global collection of services; they 
> become accessible in all parts of the app. (You can also specify providers at the component level, which is 
> often preferred.)
>* `bootstrap`: The main application view, called the root component, which hosts all other app views. Only the 
>root NgModule should set the bootstrap property.
>* `entryComponents`: it used to list components which could be dynamically created and loaded into the app

</details>

<details>
<summary>6. Which Angular frequently used modules do you know?</summary>

>**Answer:**
>* BrowserModule
>* CommonModule
>* FormsModule
>* RouterModule
>* HttpClientModule
>* BrowserAnimationsModule
>* ReactiveFormsModule

</details>


<details>
<summary>7. What is Service in Angular?</summary>

>**Answer:**
>Service is a broad category encompassing any value, function, or feature that an app needs. 
>A service is typically a class with a narrow, well-defined purpose. It should do something specific and 
>do it well.
</details>

<details>
<summary>8. What are Directives in Angular?</summary>

>**Answer:**
>A directive is a custom element which is used to extend the power of HTML. Examples:
>
>```
><li *ngFor="let element of list"></li>
>
><div *ngIf="condition"></div>
>```
> (Also, please see the question №16)

</details>

<details>
<summary>9. How we can get an instance of  Service in Components?</summary>

>**Answer:**
>1. Add Injectable decorator to service
>2. Add Service to declarations of module
>3. Add injection to the Component constructor 

</details>

<details>
<summary>10. What is DI(Dependency Injection) in Angular?</summary>

>**Answer:**
>Dependencies are services or objects which a class needs to perform this class function(s). DI is a coding pattern in 
>which a class asks for dependencies from external sources rather than creating them itself.
</details>

<details>
<summary>11. What is Component in Angular?</summary>

>**Answer:**
>Each Angular application has at least one component, the root component, that connects a component 
>hierarchy with the page document object model (DOM). Each component defines a class that contains application 
>data and logic, and is associated with an HTML template that defines a view to be displayed in a target 
>environment. 
</details>

<details>
<summary>12. What is an Angular Component template?</summary>

>**Answer:**
>A template looks like regular HTML except that it also contains Angular template syntax, which alters the HTML based 
>on an app's logic and the state of app and DOM data. 
</details>

<details>
<summary>13. What is data binding in Angular?</summary>

>**Answer:**
>Data-binding in Angular is the automatic synchronization of data between a component's model and view. There 
>are two types of data binding in Angular: one-way and two-way data binding.
>* One-way:
>  * Interpolation: `{{ value }}` (From the Component to the DOM)
>  * Property binding: `[property]=”value”` (From the Component to the DOM)
>  * Event binding: `(event)=”function”` (From the DOM to the Component)
>* Two-way data binding: `[(ngModel)]=”value”`:
> Using what’s called the banana in a box syntax, two-way data binding allows to have the data flow both ways
</details>

<details>
<summary>14. What is Pipe in Angular?</summary>

>**Answer:**
>Angular pipes let you declare display-value transformations in your template HTML. A class with the @Pipe decorator 
>defines a function that transforms input values to output values for display in a view.
</details>

<details>
<summary>15. What is the difference between Components and Directives in Angular?</summary>

>**Answer:**
>Directives don’t have view and have another decorator.
</details>

<details>
<summary>16. What types of Directives do you know in Angular? Type examples of it.?</summary>

>**Answer:**
>* Structural directives change the DOM layout by adding and removing DOM elements: `*ngFor, *ngIf`. 
>* Attribute directives change the appearance or behavior of an element: `ngSwitch, ngStyle, ngModel, ngClass`.
>* Component directives are basically directives with a template.

</details>

<details>
<summary>17. How we can add CSS Styles to Component?</summary>

>**Answer:**
>1. Just add styles to the `styles` property of Component decorator. 
>2. Add CSS file path to the `styleUrls` property of Component decorator.
>3. Add style element to the template of Component.
>4. Add link element to the template of Component.

</details>

<details>
<summary>18. What is Wildcard route?</summary>

>**Answer:**
>If the URL doesn't match any predefined routes then it causes the router to throw an error and crash the app. In 
>this case, it is better to use the wildcard route. A wildcard route has a path consisting of two asterisks to 
>match every URL. 
</details>

<details>
<summary>19.  Please explain the difference between Functions, Promises, and Observables?</summary>

>**Answer:**
>An Observable allows passing zero or more events where the callback is called for each event. If 
>the result of an HTTP request to a server or some other expensive async operation isn't needed anymore, the 
>Subscription of an Observable allows canceling the subscription, while a Promise will eventually call the 
>success or failed callback even when you don't need the notification or the result it provides anymore.

</details>

<details>
<summary>20.  What does a typical Angular animation consist of?</summary>

>**Answer:**
>* Triggers
>* States with Styles
>* Transitions between States with Animation
>Less often:
>* Groups
>* Keyframes
>* Queries
>* Sequences
>* Staggers
>* Animation useAnimation AnimateChild

</details>

<details>
<summary>21. What is Observable? What methods for notifications for subscribers Observable contains?</summary>

>**Answer:**
>Observables provide support for passing messages between publishers and subscribers in your application. 
>Observables offer significant benefits over other techniques for event handling, asynchronous programming, 
>and handling multiple values.
>* next
>* complete
>* error
</details>

<details>
<summary>22. What is route Guard in Angular? What types of guards do you know?</summary>

>**Answer:**
>Angular route guards are interfaces which can tell the router whether or not it should allow navigation 
>to a requested route. 
>Types:
>* CanActivate
>* CanActivateChild
>* CanDeactivate
>* Resolve
>* CanLoad

</details>

<details>
<summary>23. Which values can be returned by Guard?</summary>

>**Answer:**
>* True
>* False
>* Observable<boolean>
>* Promice<boolean>

</details>

**[⬆ back to top](#interview-questions)**
