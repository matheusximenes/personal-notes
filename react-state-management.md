# React State Management


## 1) Native State Management: (By Default)
  * useState (Build-in React Hook):
    - Returns a duple (Array of two items) ==>  'currentState' + 'setFunction' to modify the currentState
    - Will receive initial state or function to start the state
    - > *** Within the Component (Scoped on the component)

  * useReducer (Build-in React Hook):
    * Returns a duple (Array of two items) ==> 'currentState' + 'dispatch' will invoke the change by a action and a value/payload
    * useReducer(reducerFunc, initialState)
    * Will receive initial state as a function called reducer:
      > This reducer function will receive the state and an action as args:
         ```e.g.: function reducerFunc(state, action) { 
          switch(action.type) {
            case actionTypeName: 
            ...logic to modify the state based on the payload
              return { ...newState };
            default:
              Throw new Error("")
          }
        }
    * `reducerFunction = ((state, action) => ({...state, ...action}))`
    * `dispatch({ type: <ActionType>, ...<other values to be used to modify the state>})`

  * useCallback: (Calculation - Not the same as React.memo - Not memoize)
    * Memoize Functions
    * Avoid Expensive computations on Re-rendering (Functions)
    * Dependencies - Will rerun if dependencies changes

  * useMemo: (Calculation - Not the same as React.memo - Not memoize)
    * Memoize Objects or Arrays:
    * Avoid Expensive computations on Re-rendering
    * Dependencies - Will rerun if dependencies changes

  * useRef: (Will not re-render the component if updated)
    * Uncontrolled Input
    * Update a value to not render the complex
    * > *** use 'current'




## 2 - Redux (store, state tree, action, dispatch, reducer):

- Store: 
  * is a reference to a only State tree Object 
  * API is {subscribe, dispatch, getState}
  ```
  function reducerName(state = {...}, action) {
    switch(action.type){
      case 'whatever':
        return { ... } // Altered state; 
        ...
      default:
        return state;
    }
  }
  let store = createStore(reducerName);
  store.subscribe(() => store.getState);
  store.dispatch({type: whatever}) type is the action type;
  ```

- State tree = State:
  * is the object on the Store that will be updated
  * contains only pain JS objects, arrays and primitives;

- Reducer: 
  * is a function to updated the State Tree
  * Think as event listener with handle actions type.
  ```function reducerName(State, action) => { return new State };```
  

- Action: 
  * is a object to manage the reduce changes returning a new State Tree Changed;
  * usually text with domain and eventName, like `domain/eventName`
  ```
  const addTodo = text => {
    return {
      type: 'todos/todoAdded',
      payload: text
    }
  }


## 3 - Redux - React Tool Kit ==> Global State management
  * Modern and standard way of using redux (hooks)
  * Main Hooks:
    - useSelector(state) ==> call the state of the slice
    - useDispatch() ==> use the actions exported on the slice
  * Recommended: Single Store, Multiple Slices (Features) exporting reducers and actions
  * >  Note 1: State Call on useSelector should be exported by the slice (Avoid rewriting extra code)
  * > Note 2: Immer.Js will manage the state on the slice, can do state.something.push()
  * > Note 3: NanoID will generate a random ID --> Native to the Toolkit
  * > Note 4: CreateSelector can be user to memoize selector, voids rerender all state based on the dependencies

  * Steps:
    * 1 - Create a Store and wrap it to the app
    * 2 - Create a Slice and import on the store
    * 3 - Use useSelector API for get the Slice State on the Store
    * 4 - Use the exported action on slice with useDispatch() with or without the to change state on the slice``


## Learn more
- Zustand: (Uni-directional State Management like Redux)
 * Docs: https://www.npmjs.com/package/zustand
- Valtio (Bi-direction State Management like MobX)
- Jotai (Atomic State Management or Nano)
======================
