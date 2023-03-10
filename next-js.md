
# Next Js

## NextJS benefits:
* Created on top of React
* SSR - Server Side Rendering
* SEO Friendly
* Performance with Static Generation

## Main Features:
* Routing out of the box
* API Routes (Optional)
* Typescript & Sass out of the box (Just Change the *.tsx or *.scss)
* Static Site Generation
* Easy to Deploy

## Default Folders:
* Public ==> Static Files
* Pages will run the pages or application
* Styles is style (Recommended )


## Main Concepts:
1) Pages folder containing the Pages (Starting Lowercase)
    * 'index.tsx' will contain the main component like App()
    * 'Home' Component will render like App()
    * 'About' Component will create a route for '/about' and render the about
    *** import Head from 'next/head' will make update to header tag
    *** '_document.tsx' will generate the document page
2) Components folder: (Starting Uppercase)
    * Other components not Pages 
    * Create 'Layout.tsx' ==> Wrap the components and render in all pages


## Fetching Data ==> Async Fetch Data Methods
  * `getStaticProps()` --> Allow to fetch data in the build time
  * `getServiceSideProps()` --> Fetch data in every request (Little slower)
  * `getStaticPaths()` --> Dynamically Fetch Data by the route
      - Get all ids for all feature paths to be mapped by the getStaticSideProps 
      - `Return { paths: { params: {id: '1', id:'2', ...} }}`
  * *** Will return a object with props with data like `{ posts: fetched data }
      e.g.: return {
          props: {
              posts: data
          }
      }`
  * *** I will be pass as props to the component on top
      e.g.: `export default function Posts({posts}) { ...}`