# Component Checklist
## Planning:
    1. Interface (Designer):
      * Check for Variant Structures (Leading, Trailing, icon-only, inline, block, columns quantity, slots)
      * Modes - Dark, Inverted, and Light
      * Uses other inner components?
      * Should be extending other existing component? (Enhancement or New Comp)
      * Behavior - Elevation, Block or Inline, Default, Inactive, Hover, Active, and Focus States?
      * Expected UX - Is common or a new comp?
      * What is the main intentions of this component for the project?
    2. Code (Dev):
      * Props Names/ types - There are any naming conventions?
      * Composed Component (First Option), HOC Component, Parent Child Component (Classic)
      * Child Components are required, optional or restricted (something)
      * Will use Context API or Prop Drilling?
      * Useful custom hooks that can be used?
      * Helper Functions or new Third party Libs?
      * Class Data Model with computed props (MVC)?
      * Interfaces, Enums or NameSpaces (Typescript)
      * Data Consumption:
        * Existent API
        * New API,
        * External API,
        * Browser Storage or Cookie
        * Property Array or Object
    3. Code (Dev UI/UX):
      * CSS Vars or SASS Tokens
      * New Mixing or Presets using SASS.
      * Iconography - Internal, External (Fetch), Libraries, SVG or imagery
      * States - Default, Inactive/Disabled, Hover, Active, Focus
      * Growth behavior - Static, Flow, Flex, Grid
      * Inline or Block behavior
      * Elevation after what?
      * Animation/ Micro animations - Suggestions
## Coding (Applying MVC layers):
    1. Model (Data)
        * Class Model with computer and default values?
        * Naming Conventions for Data;
        * Interfaces, Types, Enums, or Namespaces (Typescript)
        * Data Remodeling or API already transform data;
        * State Management - Comp, Prop, ContextAPI or Third Party Libraries (Global + Fetch)
        * State Management Third Party Libraries: MobX (Global), Redux Class (Global), RTK Function Components (Global + Normalization), Zustand (Global + Data Normalization) RTK Query (Fetched Data), React Query (Fetching Data)...
       
    2. Controller (Logic)
        * React Hooks:
          * UseEffect - LifeCycle + Cancel Handlers
          * UseReducer - Complex Logic
          * Others - https://beta.reactjs.org/learn/adding-interactivity
        * Custom Hooks (Super Cool - Share, Locate, and Extend Logic)
          * Note: State only where is called.
        * Single output for Helper Functions + Third Party Libs
          * Easy to maintain - index.js
        * Local comp logic - Specific behavior about something.
        * Comp behavior - UX / A11y
  
    3. View (Interface):
       1. HTML Semantic (A11y, SEO, Human Readability)
          * Compatibility: 
            * Can I 'use - https://caniuse.com/?search=HTML%20Semantic
          * Testing: 
            * Web Dev Tools - Chrome Light House
            * Other: https://validator.w3.org/
          * Resources: 
            * Classic Cheat Sheet - https://learntheweb.courses/topics/html-semantics-cheat-sheet/
            * Web AIM - https://webaim.org/resources/htmlcheatsheet/
       2. CSS:
          * CSS Vars or SASS Tokens
          * New Mixing or Presets using SASS.
          * Use REM based on the font-size.
          * Multiple Files (Ideally + File Name Convention + Location) or Monolithic?
          * B.E.M. Methodology
          * Module/Style Component/Scoped Component/CCSinJS
          * Iconography - Internal, External (Fetch), Libraries, SVG or imagery (Ideally externalize to props implementation)
          * States - Default, Inactive/Disabled, Hover, Active, Focus
          * Growth behavior - Static, Flow, Flex, Grid
          * Inline or Block behavior
          * Structure - Agnostic? Related to?
          * Animations + Micro animation
          * Elevation
          * Documentation about external modifications (Tokens / CSS Vars / Props)
          * Verify Color Contrast A11y
        3. A11y:
           * Code:
             * Roles
             * Aria-*
             * Behaviors - disabled / selected / active / expanded/ hide / visible
             * id relationships + title + alt
             * Semantic Structure - E.g.: Link or Button or Text
           * Keyboard Navigation + Menu + ShortCuts + Keyboard/focus traps + tabindex
           * Screen Reader - Arias, Labels, and tabindex
           * Color Contrast (Designer) - Impairment Vision
           * Element Size (Designer) - Motor Impairment 
           * Testing:
             * Color Contrast Test - Light house
             * Accessibility Tree - Chrome LightHouse
             * Axe Dev Tools / extension / Axe Test
             * Code Lint
           * Resources:
             * https://webaim.org/
             * https://www.digitala11y.com/
           * Course - https://www.udacity.com/course/web-accessibility--ud891
  

## Unit Testing Simplified:
    1. Component Rendering - Default + Catching Errors.
    2. Component Features 
    3. Component Behaviors
    4. Component A11y Features
    5. Component Snapshots - UI Variant
    6. Notes: 
       1. Only apply human behavior
       2. Use semantic test by role or label first (Human Vision)
       3. Only one assertion per test
       4. Code Coverage 80% minimum.

## Suggested Visual Studio Code Extensions:
1. Console Ninja
2. Auto Close Tag
3. Auto rename tag
4. Axe Accessibility Linter
5. Web Accessibility
6. Better Comments
7. Bracket Pair Colorization
8. Bundle Size
9. Colorize
10. Indent Rainbow
11. Css Peek
12. Dictionary Completion
13. GitLenses
14. IntelliCode
15. Mithril Emmet
16. SonarLint
17. StyleLint
18. Live Share