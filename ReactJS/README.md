Tooling
-------
Webpack and Babel transpile ES6 code files into a single bundle.js that can
be understood by browsers. This is necessary because most browsers don't yet
have complete support for ES6. See [tooling.png](tooling.png).


ES6
---
* `const` is used to declare variables that are not meant to change (constants).
* `function ()` is equivalent with `() =>`. If the function has a single
  argument, the parens can be dropped:
  `(event) => console.log(event)` is equivalent with `event => console.log(event)`.
* `{ foo: foo }` is equivalent to `{ foo }`


JSX
---
JSX is a dialect of JS that allows us to write HTML in JS. Webpack and Babel
handle translating it to vanilla JS that can be understood by the browser.


Components
----------
React components (views) are JS functions that produce HTML.


Component classes and instances
-------------------------------
This is a definition of a component (think of it as a class definition):
```
const App = function() {
  return <div>Hi</div>;
}
```

This instatiates the above component:
```
<App />
```

Modules, import/export
----------------------
Write a component in its own file/module, export it at the bottom of that
file, import it from the index.js file and render it by calling `<Component />`
inside the root <App /> tag.


Class-based components
----------------------
Components can also be written as classes - classed-based components.
Class-based components are usually used for more complex components
that need the ability to introspect themselves (keeping track of user
input, etc). Every class-based component has a `render()` method
which returns some JSX.


Handling events
---------------
Event handler is a function that is run every time the event occurs
(e.g. `onInputChange(event)`). The handler is passed to the element
that we want to monitor for change
(e.g. `<input onChange={this.onInputChange} />`).


State
-----
State is a plain JS object that is used to record and react to user
events. E.g. it can hold data that changes over time. Each
class-based component has its own state object. Functional
components do not have state. Whenever the component state is
changed, the component automatically re-renders (and forces all its
children to re-render as well). Before we use state inside a
component, we need to initialize the state object. This is done by
setting a property `state` to a plain JS object inside the component
class constructor:

```
constructor(props) {
  super(props);
  this.state = { name: ''};
}
```

We only directly assign to the state object in the constructor.
Everywhere else, when we need to update state, we use `this.setState()`.


Controlled components
---------------------
A controlled form element is a form element whose value is set by
the state.


Downwards data flow
-------------------
Downwards data flow means that the most parent component in an
application (`<App />`) should be responsible for fetching data.


Props
-----
To pass a prop from a parent component to a child component:
```
<Parent name={this.state.name} />
```

This then becomes available in the child component via the props:
```
const Child = (props) => {
  return {props.name};
}
```
In the case of functional component,`props` is the argument to the
function. In the case of the class-based component, it is available
in any method via `this.props`.

Rendering is the only way for a component to pass props to another
component.

A component should never update `this.props`.
A component should use `props` to store information that can be
changed, but can only be changed by a different component.
A component should use `state` to store information that the
component itself can change.


Lifecycle methods
-----------------
3 categories of lifecycle methods: mounting, updating an unmounting.

### Mounting

A component "mounts" when it renders for the first time. This is when mounting
lifecycle methods get called. There are three mounting lifecycle methods:

* `componentWillMount` - gets called right **before** render, but *only the
first time* the component renders
* `render`
* `componentDidMount` - gets called right **after** render, but *only the first
time* the component renders

When a component mounts, it automatically calls these three methods, in order.

If a React app uses AJAX to fetch initial data from an API, then
`componentDidMount` is the place to make that AJAX call. More generally,
`componentDidMount` is a good place to connect a React app to external
applications, such as web APIs or JavaScript frameworks.
`componentDidMount` is also the place to set timers using `setTimeout`
or `setInterval`.

### Updating

A component updates every time that it renders, starting with the second render.
There are five updating lifecycle methods:

* `componentWillReceiveProps` - gets called before the rendering begins when
a component instance updates; only gets called if the component will receive
`props`
* `shouldComponentUpdate` - gets called after `componentWillReceiveProps`,
but still before the rendering begins
* `componentWillUpdate` - gets called in between `shouldComponentUpdate` and
`render`
* `render`
* `componentDidUpdate` - gets called after any rendered HTML has finished
loading

When a component updates, it automatically calls these five methods, in order.

`shouldComponentUpdate` should return either `true` or `false`. If
`shouldComponentUpdate` returns `true`, then nothing noticeable happens.
But if `shouldComponentUpdate` returns `false`, then the component will not
update. None of the remaining lifecycle methods for that updating period will
be called, including `render`.

You cannot call `this.setState` from `componentWillUpdate` or
`componentDidUpdate`. The most common use case for these two methods is any
kind of non-React setup before/after a component renders, such as checking the
window size or interacting with an API.

### Unmounting

A component's unmounting period occurs when the component is removed from the
DOM. This could happen if the DOM is rerendered without the component, or if
the user navigates to a different website or closes their web browser. There
is only one unmounting lifecycle method:

* `componentWillUnmount` - gets called right before a component is removed from
the DOM.

If a component initiates any methods that require cleanup, then
`componentWillUnmount` is where you should put that cleanup.



TODO:

* reducers (generate state)
* containers (smart components, components with state)
* actions and action creators (for changing state)
* middleware
