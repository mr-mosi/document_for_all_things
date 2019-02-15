## How to think in react!


### Step 1: Break The UI Into A Component Hierarchy
Single responsibility principle tell us a component should ideally only do one thing.if it ends up growing, it should be decomposed into smaller subcomponents.


### Step 2: Build A Static Version in React
Now that we have our component hierarchy, it’s time to implement our app. The easiest way is to build a version that takes our data model and renders the UI but has no interactivity. It’s best to decouple these processes because building a static version requires **a lot of typing and no thinking, and adding interactivity requires a lot of thinking and not a lot of typing.**

In this step we pass data to components via props and we do not use state because state is reserved only for interactivity.

build top-down or bottom-up is two choice. That is, you can either start with building the components higher up in the hierarchy or with the ones lower in it. In simpler examples, it’s usually easier to go top-down, and on larger projects, it’s easier to go bottom-up and write tests as you build.

At the end of this step, you’ll have a library of reusable components that render our data model. The components will only have render() methods since this is a static version of our app.


### Step 3: Identify The Minimal (but complete) Representation Of UI State
To build our app correctly, you first need to think of the minimal set of mutable state that our app needs. The key here is DRY: Don’t Repeat Yourself. Figure out the absolute minimal representation of the state our application needs and compute everything else you need on-demand. For example, if you’re building a TODO list, just keep an array of the TODO items around; don’t keep a separate state variable for the count. Instead, when you want to render the TODO count, simply take the length of the TODO items array.


For determining what peace of data is state or not we must simply ask this three question:


1 - Is it passed in from a parent via props? If so, it probably isn’t state.
2 - Does it remain unchanged over time? If so, it probably isn’t state.
3 - Can you compute it based on any other state or props in our component? If so, it isn’t state.


### Step 4: Identify Where Our State Should Live
In this step we need to identify which component mutates, or owns, this state.


Remember: React is all about one-way data flow down the component hierarchy. It may not be immediately clear which component should own what state. so follow these steps to figure it out:

For each piece of state in your application:

* Identify every component that renders something based on that state.
* Find a common owner component (a single component above all the components that need the state in the hierarchy).
* Either the common owner or another component higher up in the hierarchy should own the state.
* If you can’t find a component where it makes sense to own the state, create a new component simply for holding the state and add it somewhere in the hierarchy above the common owner component.


### Step 5: Add Inverse Data Flow
This step discuss about how inner components can change the state of outer components.
