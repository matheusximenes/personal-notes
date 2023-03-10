# Clear Code
## 1) SOLID Principles: (In JS & React)
> Can Be applied to: Class, Function, Method, Component, or Module
* S ==> Single Responsibility - SRP:
    - Breakdown to Single Responsibility (Do exactly one thing).
    - Applied to Components, Hooks, Functions, or Classes.
    * *** Note: Agnostic (Doesn't know other relations).
    * *** Note 2: Separated is easy to fix bugs.
* 0 ==> Open-closed - OCP (Open to Extension, but closed for modification):
    - Don't modify extend it (Add features without modifying existing code).
    - Applied to Components, Hooks, Functions, or Classes.
    > E.g.: Creating new Components based on existent ones, Or Outer Implementations like 'icon' (Node) props.
    * *** Note: Don't modify the original 'component' just create a new one and use the original with some new features.
    * *** Note 2: Avoid Refactoring code, avoid bugs and is easy to maintain.
* L ==> Liskov Substitution - LSP (Subtype Objects should be Substitutable for supertype objects):
    - The Subtype/child Element should extends from the Supertype Element. 
    - If B extends A, anywhere you use A you should be able to use B.
    E.g.: 'SearchInput' should extends 'HTMLInputElement' and pass down as 'HTMLInputElement' props to based input inside 'SearchInput'.
    * *** Note: Extends the features of Supertype Element and avoid future refactoring and discussions.
    * *** Note: Promotes Consistency from parent and child entities.
* I ==> Interface Segregation - ISP:
    - Clients should not depend upon interfaces that they don't use
    - React: Components shouldn't depend of props that they don't use
    - Don't make a component rely on props it doesn't care about.
    >E.g.: Don't pass down 'products' props if you just gonna use product.image
    * *** Note: Only uses what suppose to, avoid extra bugs or extra dependencies.
* D ==> Dependency Inversion - DIP:
    - Should abstract unique action if is used in multiple places.
    - High-level code shouldn't depend on implementation details - always use an abstraction.
    > E.g: Form that can be use in different places, abstract the onSubmit function to a Parent Component.
    * *** Note: Avoid bugs and increase maintainability of the code.


> Good Code - Functional, Maintainable, and Robust

## Resources:
* https://www.youtube.com/watch?v=MSq_DCRxOxw
* https://medium.com/backticks-tildes/the-s-o-l-i-d-principles-in-pictures-b34ce2f1e898
* https://www.everydayreact.com/articles/solid-principles-in-react
* https://medium.com/docler-engineering/applying-solid-to-react-ca6d1ff926a4
* https://dev.to/shadid12/can-you-apply-solid-principles-to-your-react-applications-46il
