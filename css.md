# CSS Structure & Methodologies

## B.E.M Methodology
* B ==> Block (Wrapper)
* E ==> Element (Inner Element)
* M ==> Modifier (Variant, Flag, State, ...)
> Structure ==> Block__Element--Modifier

## React and CSS
### 1. Classic CSS:
  
    `import './CSS/filename.css'`


### 2. PreProcessors like SASS, LESS or SCSS
  
    `import './SCSS/filename.scss'`


### 3. CSS in JS:
* Template Literal (Tagged Templates):
  
  <code>const heading = css`
    font-size: 2em;
    color: ${myTheme.color}
  `;</code>

* JS Object (Object Styles):
    
  `const heading = css({
    fontSize: "2em",
    color: myTheme.color,
  })`;`


### 4. CSS Modules:
* Import CSS:
  
  * Import: 

    `import styles from "./style.css" or import styles from './Button.module.css';`
  * Usage:
  
    `<button className={styles.error}>Error Button</button>`

  * > Close the CSS Scope


### 5. Styled Components:
  * call style.<HtmlElement>` ... CSS Properties here `
    - Nesting HMTL elements
    - States using '&' like Sass
  * Props:
    - Pass props from the Component
    - Inside Template Literal call `${(props) => props.<propName>}`
  * Theme:
    - Create a Provider and add a object with the values
    - Accessible on props.theme.<...> in any component wrapped by the provider
  * Global Styles --> CreateGlobalStyle in Globals.js exporting it to App.js as Component


### 6. Tailwind:
  * **Utility Classes** to create Styles
  * State: e.g.: `hover:color-gray-500`
  * Media Query: e.g.: `md:hidden`
  * TailWindCss.config.js file:
    - Extends new classes on extends or modify existent ones
    - Allow to use the VSCode autocomplete extension
  * TailWindCss.css file:
    * Import Fonts
    * Call all tailwind classes  (base / Components / utilities);
    * @Layer Add to a specific Layer
    * @Apply Will create a full class
  
      `.btn-primary { @apply py-2 px-4 bg-blue-500 text-white font-semibold rounded-lg }`
  * Recompile Tailwind after changing 'TailWindCss.css' file or 'TailWindCss.config.js' file


### 7. Other:

#### Display: *Block*, *inline*, *inline-block*
* Compared to display: inline, the major difference is that display: inline-block allows to set a width and height on the element.
* Also, with display: inline-block, the top and bottom margins/paddings are respected, but with display: inline they are not.
* Compared to display: block, the major difference is that display: inline-block does not add a line-break after the element, so the element can sit next to other elements.


#### Combinations 
* descendant selector (space) --> Contains
* child selector (`>`)  --> Parent Child
* adjacent sibling selector (`+`) -->  Place right each other
* general sibling selector (`~`) --> All elements

#### Not common pseudo Selectors
* `::first-line` --> First Line of a text
* `::selection` --> Highlighting Mouse selection
* `::marker` --> bullets or squares of lists 

#### Math Functions
* `Calc()` ==> Result will be the Value
* `Max(a, b, c, d)` Will get the 'maximum' value of all possible values
* `Min(a, b, c, d)` Will get the 'minimal'value of all possible values

#### CSS Units 
* *** My Preference is rem --> Relative to font-size of the root element (Don't overwrite the browser settings, default is 16px --> rems is base 16)
* *** Alternatively --> Usage of 62.5% will convert the rem to 1 rem = 10px (Can be trick if depends of others configuration);
* *** ch	--> Relative to the width of the "0" (zero)	- Printed World width of 'O' letter (Accessibility issues don't go more than 75 characters per line)
 
1. `em`	--> Relative to the current font-size of the element (2em means 2 times the size of the current font) --> Media Queries Maybe
2. `ex`	--> Relative to the x-height of the current font (rarely used)
3. `vw`	--> Relative to 1% of the width of the viewport*	
4. `vh`	--> Relative to 1% of the height of the viewport*	
5. `vmin` --> Relative to 1% of viewport's* smaller dimension	
6. `vmax` --> Relative to 1% of viewport's* larger dimension	
7. `%` --> Relative to the parent element

#### CSS Specificity
Hierarch of Styling: 
`Element ==> Class ==> ID ===> Style`

#### Modern CSS
1) :is()
   * *** Similar to:
   main, header, footer {
     p {
       color: green;
     }
   }
   * *** Usage: 
`:is(main, header, footer) p {
  color: green;
}`
1) :where()
2) :has()
   * styles applied to the <a> element
   `a:has(img, div) {
     border: 2px solid blue;
   }`

### References:
* CSS in JS - https://css-tricks.com/a-thorough-analysis-of-css-in-js/
* TailWindCss - https://tailwindcss.com/docs/installation
* Styled Components - https://styled-components.com/
* CSS Units - https://www.google.com/search?q=css+units&rlz=1C5CHFA_enCA805CA805&sxsrf=ALiCzsZ_hNhsa9VbUx62IYA81OJZSqtDxA:1671653684002&source=lnms&tbm=vid&sa=X&ved=2ahUKEwiWtZagw4v8AhUXnXIEHRxDACoQ_AUoAnoECAEQBA&biw=1440&bih=702&dpr=2#fpstate=ive&vld=cid:123a1b26,vid:N5wpD9Ov_To
