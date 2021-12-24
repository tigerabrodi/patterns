# Patterns

## Singleton Pattern

- Singletons are classes which can only be instantiated once, and can be accessed globally.

- Can not be modified.

- Considered an anti-pattern and should be avoided in JavaScript.

- Makes code more complex, less useful, and a real pain to re-use or test, since all tests rely on the modification to the global instance of the previous test.

- We may use other tools for global state such as Redux, the downsides of global state don't disappear, but we can at least make sure that the global state is mutated the way we intent it, since components cannot update the state directly.


## Proxy Pattern

- Proxy is basically the middle-man between you and your target. You will interact with the proxy, instead of directly interacting with your target.

- You create a proxy via `new Proxy()`.

- Common methods you would add to a Proxy are get and set.

- Can be useful to add validation.

- It is best to not use proxies for performance-critical code.


## Provider Pattern

- Make data available available without relying on prop drilling, which makes refactoring easier and avoids a mess.


## Prototype Pattern

- Share properties among many objects of the same type.

- See the prototype via `prototype` directly on a constructor, or via `__proto__` property on any instance.

- Prototypes themselves also have a __proto__object!

- When we try to access a property that's not directly available on the object, JavaScript recursively walks down all the objects that __proto__ points to, until it finds the property!

- The Object.create method lets us create a new object, to which we can
explicitly pass the value its prototype.


## Container/Presentational Pattern

- Enforce separation of concerns by separating the view from the application logic.

- Presentational components receive their fdata from container components, where the logic happens.

- You can also use a custom hook to retrieve the data within the presentational component. Still we separate the application logic from the view.


## Observer Pattern

- Use observables to notify subscribers when an event occurs.

- An observable object usually contains 3 methods, subscribe, unsubscribe and notify.

- Great way to enforce separation of concerns and the single-responsibility principle.


## Module Pattern

- Split up your code into smaller, resuable pieces.

- You can only have one default export per module.

- We can import everything from a module via asterisk, the default export will have the name `default`.

- By dynamically importing modules, we can reduce the page load time. We only have to load, parse, and compile the code that the user really needs, when the user needs it.


## Mixin Pattern

- Add functionality to objects or classes without inheritance.

- All a mixin does is to add functionality.

- The mixin can be added to the the object's or classes' prototype with the `Object.assign` method.

- Mixins themselves can use inheritance.

- Modifying an object's prototype is seen as bad practice, as it can lead to prototype pollution and a level of uncertainty regarding the origin of our functions.


## Mediator/Middleware Pattern

- Use a central mediator object to handle communication between components.

- Components communicate with each other via a central point.

- When multiple components need to communicate with multiple components, this is great in order to avoid conflicts or miscommunication (things going south and becoming messy.)


## Render Props Pattern

- Pass JSX elements to components through props.

- When lifting state up to the parent, if the parent has multiple children, each state change could cause a re-render of all the children, which could make the app less performant, because children who don't need to be re-rendered would still be re-rendered.

- You could give it an explicit prop such as `render`, or we could use `props.children`.


## Hooks Pattern

- Use functions to reuse stateful logic among multiple components throughout the app.


## HOC Pattern

- Pass reusable logic down as props to components throughout your application.

- Used in order to reuse the same logic in multiple components.

- Hooks do not replace this pattern.

- Best when uncustomized behaviors need to be used by many components throughout the application. Hooks are more suitable if you want to also be able to customize the logic from within the components.


## Flyweight Pattern

- Reuse existing instances when working with identical objects.

- A good way to spare memory when creating a lot of similar objects.

- Takes advantage of a Set to check if a certain unique value already exist, i.e. isbn for books.

- Less import nowadays due to the amount of RAM hardware have.


## Factory Pattern

- Use a factory function in order to create objects.


## Compound Pattern

- Create multiple components that work together to perform a single task.

- Managing internal state, and only importing one component, great for component libraries, i.e. Semantic UI does this.


## Command Pattern

- Decouple methods that execute tasks by sending commands to commander.


# List Virtualization

- When you have a huge list of items you need to render, instead of rendering of all of them, you only render ones that is within the user's window (what the user sees), and dynamically render them as the user scrolls.
