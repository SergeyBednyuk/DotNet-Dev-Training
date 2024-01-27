# Exam questions
<details>
<summary>1. Please explain the difference between one-way and two-way data binding</summary>

>**Answer:**
>* **One-Way data binding:**
> the View or the UI part does not update automatically whenever the data model changes.
> You need to manually write custom code in order to update it every time the view changes.
> In one-way data binding, the template expression `{{}}` and square braces `[]` are used
> to bind a property to the DOM.
>  * Interpolation: `{{ value }}` (From the Component to the DOM)
>  * Property binding: `[property]=”value”` (From the Component to the DOM)
>  * Event binding: `(event)=”function”` (From the DOM to the Component)
>* **Two-way data binding:**
> the View or the UI part is updated as soon as the data model changes.
> It is a synchronization process, unlike One-way data binding.
>  * `[(ngModel)]=”value”`
</details>


<details>
<summary>2. What is a parameterized pipe?</summary>

>**Answer:**
> The pipe which accepts parameters.
> The parameterized pipe can be created by declaring the pipe name with a colon `:` and then the parameter value.
> The example of using: 
>```
> {{ someDate | date: "mediumDate" }}
>```
</details>


<details>
<summary>3. What is view encapsulation for CSS in Angular?</summary>

>**Answer:**
> Component CSS styles are encapsulated into the component's view and don't affect the rest of the application.
</details>


<details>
<summary>4. What is Routes in Angular?</summary>

>**Answer:**
> The Angular Router NgModule provides a service that lets you define a navigation path among
> the different application states and view hierarchies in your app.
</details>
<details>


<summary>5. Could you name the existing Router Events?</summary>

>**Answer:**
>* NavigationStart,
>* RouteConfigLoadStart,
>* RouteConfigLoadEnd,
>* RoutesRecognized,
>* GuardsCheckStart,
>* ChildActivationStart,
>* ActivationStart,
>* GuardsCheckEnd,
>* ResolveStart,
>* ResolveEnd,
>* ActivationEnd
>* ChildActivationEnd
>* NavigationEnd,
>* NavigationCancel,
>* NavigationError
>* Scroll

</details>


<details>
<summary>6. Describe the way how to provide communication between parent and child components.</summary>

>**Answer:**
>* Parent to Child: sharing via @Input()
>* Child to Parent: sharing via @Output() and EventEmitter
>* Child to Parent: Sharing Data via ViewChild
>* Unrelated components too: Communication through service (or storage, like Redux, etc…)

</details>
<details>


<summary>7. What type of compilation exists in Angular?</summary>

>**Answer:**
>* **Just-in-time (JIT)** compilation - standard development approach which compiles a project in
> the browser at runtime when the application loads.
>* **Ahead-of-time (AOT)** compilation - the compiles tuns at the build time and browser will 
> have only precompiled version of an app. APP size less than for JIT.
>
> The AOT compiler works in three phases:
> * *Code Analysis:* The compiler records a representation of the source
> * *Code generation:* It handles the interpretation as well as places restrictions on what it interprets. 
> * *Validation:* In this phase, the Angular template compiler uses the TypeScript compiler to validate the binding expressions in templates.
> 
> ( see https://angular.io/guide/aot-compiler for details)

</details>


<details>
<summary>8. Explain the lifecycle sequence in Angular?</summary>

>**Answer:**
>* *ngOnChanges* - Called before ngOnInit() and whenever one or more data-bound input properties change. 
>* *ngOnInit* - Called once, after the first ngOnChanges().
>* *ngDoCheck* - Called during every change detection run, immediately after ngOnChanges() and ngOnInit().
>* *ngAfterContentInit* - Called once after the first ngDoCheck().
>* *ngAfterContentChecked* - Called after the ngAfterContentInit() and every subsequent ngDoCheck().
>* *ngAfterViewInit* - Called once after the first ngAfterContentChecked().
>* *ngAfterViewChecked* - Called after the ngAfterViewInit() and every subsequent ngAfterContentChecked().
>* *ngOnDestroy* - Called just before Angular destroys the directive/component.

</details>


<details>
<summary>9. Please explain the change detection strategy in Angular</summary>

>**Answer:**
> Change Detection means updating the DOM whenever data is changed. 
> By default, Angular uses `ChangeDetectionStrategy.Default` and change detection is run only on immutable objects.
>
> `ChangeDetectionStrategy.OnPush`
> This tells Angular that the component only depends on its `@Inputs()` ( aka pure ) and needs to be checked 
> only in the following cases:
>* The Input reference changes. The advantage of working with immutability in the context of change detection is
> that Angular could perform a simple reference check in order to know if the view should be checked. 
> Such checks are way cheaper than a deep comparison check.
>* An event originated from the component or one of its children.
   A component could have an internal state that’s updated when an event is triggered from the component or one of his children
>* We run change detection explicitly.
</details>

<details>
<summary>10. What is the Resolver? How to get some data for the route, before you will be navigated to this route?</summary>

>**Answer:**
> You should pass service, which implements `Resolve` interface, into `resolve` property of route. 
</details>
<details>


<summary>11. What is Service Workers?</summary>

>**Answer:**
> At its simplest, a service worker is a script that runs in the web browser and manages caching for an application. 
> Service workers function as a network proxy. They intercept all outgoing HTTP requests made by the application 
> and can choose how to respond to them.
</details>


<details>
<summary>12. Explain please existing module loading concepts.</summary>

>**Answer:**
>* *Eager* - loading modules before application starts
>* *Lazy loading* - loading modules on demand (to load module using `loadChildren` property in route configuration)
>* *Preloading* - loading modules in the background when application starts 
> (to load modules using `loadChildren` property and configure `preloadingStrategy` property with `RouterModule.forRoot`. 
> Must be assigned `PreloadAllModules` strategy to `preloadingStrategy` property, 
> then all feature modules configured with `loadChildren`, are preloaded.)
</details>
<details>


<summary>13. How to create reusable animation?</summary>

>**Answer:**
> To create a reusable animation, use the `animation()` method to define animation in a separate .ts file 
> and declare this animation definition as a const export variable. 
> You can then import and reuse this animation in any of your app components using the `useAnimation()` API.
> For the addition of parameters to the animation, you should pass parameters in `{{}}` in animation, 
> then you can set it in `parameter` property of options parameter of `useAnimation()`.
</details>


<details>
<summary>14. What are operators in RxJS?</summary>

>**Answer:**
> Operators are functions that build on the observables foundation to enable sophisticated manipulation of collections. 
</details>

<details>
<summary>15. Please name RxJs operators that are often used?</summary>

>**Answer:**
> From, of, concat, merge, filter, take, concatMap, map, combineAll, tap, share etc.
</details>

<details>
<summary>16. How we can handle error in RxJs?</summary>

>**Answer:**
> In addition to the `error()` handler that you provide on a subscription, RxJS provides the `catchError` 
> operator that lets you handle known errors in the observable recipe.
</details>


<details>
<summary>17. What is Subject in RxJS?</summary>

>**Answer:**
> An RxJS Subject is a special type of Observable that allows values to be multicasted to many Observers. 
> While plain Observables are unicast (each subscribed Observer owns an independent execution of the Observable), 
> Subjects are multicast.
</details>

<details>
<summary>18. Which Subjects in RxJS do you know?</summary>

>**Answer:**
>* *Subject*
>* *BehaviorSubject* - It stores the latest value emitted to its consumers, 
> and whenever a new Observer subscribes,
> it will immediately receive the "current value" from the BehaviorSubject.
>* *ReplaySubject* - A ReplaySubject is similar to a BehaviorSubject because 
> it can send old values to new subscribers, but it can also record a part of the Observable execution.
>* *AsyncSubject* - option for which only the last value of the Observable execution is sent to its observers, 
> and only when the execution completes.

</details>


<details>
<summary>19. What is the difference between template driven forms and reactive forms?</summary>

>**Answer:**
> Reactive forms are also known as model-driven forms. 
> This means that the HTML content changes depending on the code in the component.
>
> Template-driven forms are driven by derivatives in the template.
> This means that you will see derivatives such as `ngModel` in the template as opposed to the code. 
> Template-driven forms use the `FormsModule`, while reactive forms use the `ReactiveFormsModule`. 
>
> Template-driven forms are asynchronous, while reactive forms are synchronous. 
> In template-driven forms, most of the interaction occurs in the template, 
> while in reactive-driven forms, most of the interaction occurs in the component.
</details>


<details>
<summary>20. How to work with a single FormControl?</summary>

>**Answer:**
> It is possible to create an instance of control in the component’s constructor and then work 
> with its value and behavior linking from a template.
</details>


<details>
<summary>21. How to add custom validator for forms?</summary>

>**Answer:**
> **For reactive forms**:
>* Create function-validator, which returns implementation of ValidatorFn interface.
>* Add this function in form validators.
>
> **For template driven forms:**
>* Create directive class which implements Validator interface.
>* Add this directive to providers in the field of Decorator of this directive.
>* Add this directive to input in the template.
</details>


<details>
<summary>22. How to handle http requests within Angular application, how to create basic wrapper for handling 
Http requests? What is the Http Interceptor and its purpose?</summary>

>**Answer:**
> It has be to used with `HttpClient` module by creating simple service that will 
> handle different kinds of requests. `HttpInterceptor` is the interface that provides ways of catching request that 
> will be sent to and adding some additional headers, for example.
</details>


<details>
<summary>23. What difference between ContentChild and ViewChild?</summary>

>**Answer:**
> `ContentChild` works with content, which was passed into `ng-content` of component.
> And `ViewChild` works with content of child component or component template elements.
</details>

**[⬆ back to top](#exam-questions)**
