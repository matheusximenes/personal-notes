# React JS

## 1) What is React?
* JS Library - Open Source (Created and Maintained by Facebook)
SSR - Server Side Render  - Classic By request (Dynamic Content)
CSR - Client Side Render (SPA) - Page Lever (#app) and Component Level (#someId)
SSG - Static Site Generation - Classic By Request with all together JS, CSS, HTML, ... (Performance and BLOG)
ISR - Incremental Static Generation - SSG + Incremental

## 2) Main Features:
* JSX - Javascript Syntax Extension Language (React Elements that Extends HTML Elements)
* Virtual D.O.M (Document Object Model)
* State ==> If updated will rerender the component
* Props ==> Parent to Child, if Changes will rerender component
* One Way Data Bind - Uni-direction (Parent to Child)
* Key Usage (Performance Virtual DOM Manipulation) in a Iteration = Render()
* Component Based:
  - MVC:
    * Model (data)
    * View (Render())
    * Controller (Control ==> Logic between Data and Render())

## 3) Virtual D.O.M (Document Object Model):
* Copy of Real DOM.
* 2 Virtual DOMs (Prev State and Current State).
* Reconciliation Event (Diffing Algorithm).
* Minimal Changes on the Real DOM (Tree or Element Attributes).
* Super Fast.

## 4) Class Components:
* Js Class extends React.Component
* Construction
  - Receive Props as arg
  - Super (Props) // Super() ==> Call Constructor in Parent Class + Props (React)
  - Initial State Object
* Basic LifeCycle Methods:
  - `constructor()`
  - `componentDidUpdate (PrevProps, PrevState, Snapshots)`
  - `render()`
  - `componentDidMount()` => Ref's + Fetch Data + Early State Updates
  - `componentWillUnmount()` (Clear Listeners + subscriptions)
  - ** `shouldComponentUpdate()` => Avoid unnecessary rendering - Performance Optimization
  - *** `componentDidCatch()` ==> Error Boundaries Class Component UI

## 5) Functional Components (Better Readability, Less code, Better State Management, reusable code (Custom hooks))
* Presentation Comp or Stateless
* Stateful Comp (React Hooks)
* Arrow (Instantiation) or Function (Declarative) Functions
* return JSX
* props as args + children hidden
* Don't need this declaration all the time.

## 6) React Hooks (Functional Components):
* Basic Rules ==> Top Level, not in iterations, not in conditions
* Builded In function from React Library

## 6.1) useState:
* State management.
* Arguments are the initial state.
* Returns a tuple => State + function to Change update this state.
* SetState function: returns the current State, can be called as CB func passing the PrevState.

## 6.2) useEffect: 
* Component LifeCycles
* Pass a CB Function as argument and dependencies (Run if updates Dependencies)
* Dependencies: 
  - No Dependencies - Run Every time (Similar to componentDidUpdate)
  - Empty Dependencies [] - Run on Mount (Similar to componentDidMount)
  - Receives State, Props, Variables and Functions as dependencies 
* Returning Function:
  - Clear Up Functions (Listeners, On Going Fetch, and cancel subscriptions)
  - Similar to componentWillUnmount
* *** Avoiding Infinite Loop:
  - *useCallback to memoize Functions (new functions in each rendering)*
  - *useMemo to memoize objects (New referenced objects)*
  - *useRef.current to memoize arrays (new referenced array)*

## 6.3) useContext (*Avoid Drilling Properties to deep nested components*)
* Context API usage:
  1 - Create the Context ==> const AuthContext = React.createContext( InitialValue );
  2 - Wrap Component with a `<AuthContext.Provider value={ /* Value(s) = State, SetState */}/>`
  3 - On nested component call const [state, setState] = useContext(AuthContext);

## 6.4) UseRef:
* Memoize arrays/objects;
* DOM Reference to future manipulation (No State manipulation)
* Update values without trigger re-rendering
> *** Don't have dependencies.
> *** Don't forget *.current

## 6.5) useCallback:
* Memoize Functions
* Avoid Expensive computations on Re-rendering (Functions)
* Dependencies - Will rerun if dependencies changes

## 6.6) useMemo:
* Memoize Objects/Arrays (**Primitives**):
* Avoid Expensive computations on Re-rendering
* Dependencies - Will rerun if dependencies changes

## 6.7) useReducer:
* Used for complex Logic on State Management - 3 Variations at least
* Call ==> `const [state, dispatch] = useReduce(reducerFunc, InitialState);`
* ReducerFunc ==> `function reducerName(state, action) { switch (action.type) { case actionName: return doSomething to state, ... }}`
* Dispatching Changes ==> `onClick={() => dispatch({type: actionName})}`
  *** With the Payload will send a value to the actions

## 6.8) useID = Created uniqueId;

## 6.7) Custom Hooks:
* `'use'` prefix for initialization 
* must return something (Data, State management, Multiple Things, Reusable Code, Abstractions);
* E.g.:
  - useFetch() --> Fetch Things
  - usePortal() --> Manipulate Portals 
  - useCookies() --> Manipulate Cookies
  - useLocalStorage() --> Manipulate Local Storage
  - Very Usefull Abstractions

## 7) Suspense - Lazy Loading
* Wrap into `<React.Suspense fallback={<Component/>}/>`
* Import Component ==> const OtherComp = `React.lazy(() => import("someplace"))`

## References:
https://www.tatvasoft.com/blog/reactjs-best-practices/




# React Performance:

## Virtual DOM:
  * Avoid unnecessary updates and re-renders.
  * Double-Check the React Dev Tools under Settings at checkbox "Highlight updated when components render"
  * Splitting Components
  * * Avoid spread props
## HOC - Higher Order Components
  * Definition ==> Reuse component logic
  * Raw Definition ==> Receives a Component as arguments and modify it and return it.
  * Use Cases:
    * Create a Middleware
    * Extend without Modify
    * Hydrating with Data
    * Intercepting DOM Events
    * Creating Variants of same Component
  * Example : 
  * `// accept a Component as an argument
const withSomeLogic = (Component) => {
  // do something

  // return a component that renders the component from the argument
  return (props) => <Component {...props} />;
};
const Button = ({ onClick }) => <button onClick={func}>Button</button>;
const ButtonWithSomeLogic = withSomeLogic(Button);
` 

## Rendering Techniques:
  * SSR
  * Static Rendering

## Leveraging Local Storage (Avoid round trips to the server)

## State Managing (Redux, React Query)

## Code Splitting:
  * Dynamic Imports
## Lazy Load Components
  * Render Components on Demand
  * Initialize Critical UI and quietly render noncritical UI 
  * Usage ==> Client Side only:
    * React.lazy() ==> const Comp = React.Lazy(() import('./component'))
    * React.Suspense:
      * Placeholder for the laziness of the component.
      * Wrap the Lazy Component with Suspense using fallback attribute, can be a spinner or a loader.
  * On SSR - Server Side Render use react-loadable library - https://github.com/jamiebuilds/react-loadable

## Measure Performance:
* React Profiler (Experimental)
* Lighthouse

References:
HOC - https://www.developerway.com/posts/higher-order-components-in-react-hooks-era
Lazy Loading - https://blog.logrocket.com/lazy-loading-components-in-react-16-6-6cea535c0b52/
React:
https://reactjs.org/docs/optimizing-performance.html
https://reactjs.org/docs/perf.html