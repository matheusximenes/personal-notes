# Testing:


## Importance:
* Catch Bugs (Can Be in Multiple places at once)
* Increase Confidence in Applications (All features are working properly)
* Speed QA Time (More sure about )
* Can Serve as Documentation for what it does

## Types of Test: (Most Relevant to Client Side)
* Unit Tests (Isolation):
  - Component, Class, Function or Hook 
  - Fast + Cheap
* Integration Tests:
  - How things are working together
  - Proper Relationship between things (Classes, Components, Hooks)
* End to End (E2E) Testing - Cypress or Puppeteer
  - Human Behaviour in the Application as a whole
  - Slow + Expensive

## TDD (Test Driven Development)
  * Red - Make it Fail
  * Green - Make it Pass
  * Refactoring Code
  * Redo again

## BDD (behavior-driven development)
  * Given - Scenario or Situation (Visiting a Site)
  * When - Action (Clicking on sign up button)
  * Then - Reaction (Go to sign up page)


## Best Practices - Unit Test:
* Unit of the Code
* Check only the behaviour
* Make the setup simple / Factory
* Write Data generators - Utility Class
* Mocks Data generations - Utility Mock Class
* Single Assertion per Test
  - Test names more specific
  - Find quickly the bug
  *** Multiple if fail can be some of the middle assertions
* Keep it isolated

## Structure:
* Describe ==> Component  
  - Describe ==> Rendering
  - Describe ==> Features
  - Describe ==> A11y
  - Describe ==> Snapshots



# React Testing Library (Testing Playground Addon Browser)
1. Files (*.spec|test.*)
2. Getting to work:
  - 'render' will render the component
  - 'screen' will access the Virtual DOM created on the render function 
  - Assertion ==> expect will be JEST
3. Querying things on the Virtual DOM:
  - Driver Methods:
    * get 
      - 90% of the time
      - If not match throw a error
    * find (Async & Await)
      - If not match throw a error
    * query 
      - If not match return 'null'
  - Sub driver Method:
    * By (returns Single Element) 
      - if find more the one element return a 'Error'
    * AllBy (returns Array of Elements)
  - Sub query by Priority:
    * Role (Top Priority) - A11y
    * LabelText - A11y
    * PlaceholderText - A11y
    * Text(/<text>/i) - A11y
    * AltTExt - Semantic
    * ByTitle - Semantic
    * TestId (Lower Priority) - Test ID

  - Mixes:
    * Get Role and Inner Text: e.g.:  `screen.getByRole("heading", { name: <innerText>})`
4. Fire Events (fireEvent.* Method):
  - Typing - `fireEvent.change(Element, { target: { value: "Text"}})`
  - Clicking - `fireEvent.click`
5. Hooks (react-hooks):
  - 'renderHook':
    * e.g.: `const { result } = renderHook(<CustomHookName>)`
  - 'act'
    * e.g.: `act(() => { result.current.<ExportedHookMethodName>})`
  - Assertion:
    * `expect(result.current.<ExportedHookState>).toBe(*)`
