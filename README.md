# Intro to React.js

![react-logo](./images/react-white-logo.png)

## Learning Objectives

<!-- * Explain what a frontend framework is and why they can be helpful in writing more complex applications.
* Explain what ReactJS is and where it fits in our applications' stack.
* Explain the component model of web development.
* Create and return React components in the browser. -->

## Framing

<!-- ### What is a Frontend Framework? 

- A framework is software providing generic functionality and structure that serves as foundation to build and deploy applications.
- Express is a framework that runs on the server, receiving incoming request from the client, preforming some work that you have defined, and returning some response to the client.  Front-end frameworks run in the client's browser, receive input from interactions with the page, perform some work that you have defined, and make any updates necessary.
- Frameworks can help standardize code, give you additional functionality and performance, and can help get your code off the ground faster.  
- There are [many front end frameworks](https://2020.stateofjs.com/en-US/technologies/front-end-frameworks/)  and each go about solving problems of how state is managed, updated, and represented by a view but there are many commonalities.
- There is a lot of debate over whether frontend frameworks count as frameworks at all -- some people say that they are just libraries and should be referred to as such. -->

### What is React and Why do popele like it?
[React](https://reactjs.org/) is a JavaScript library for building interactive user interfaces.

With jQuery we had the ability to dynamically interact with the DOM, updating content, creating and removing elements on the page, without having to trigger a full page refresh. In this way React will take the place of jQuery.

As the the front end of your application becomes larger and more complex, trying to manage that complexity with vanilla JavaScript or even jQuery becomes difficult. The jQuery library alone doesn't provide us with tools to organize our code.

React provides powerful tools for managing that complexity, giving us tools to organize our code. With React, the user interface is broken out into reusable building blocks called **components**. Each component can house its own logic, manage its own state, and pass information to other **components**.

React also performs very efficiently in the browser. If we think back to using server-side templates in the previous units, whenever we wanted to update the data on the page, we needed to refresh the entire page to see our changes. We could improve this with jQuery by only rerendering part of the page.

React takes this efficiency even further, using something called the **Virtual DOM**, we can rerender only the exact parts of the page that need to be rerendered and nothing more. What is even more beautiful is React handles all of this behind the scenes without us having to manage it.

<!-- > **Selling Point:** By modeling small compatible components that focus on just rendering a view, we can move business logic out of the DOM, and therefore improve our app's performance, maintainability, modularity and readability. -->

<!-- TODO: CONSIDER BRINGING THE FACEBOOK HISTORY BACK ON SOME LEVEL -->

<!-- #### Some History

The first thing most people hear about React is "Facebook uses it."
* First used by Facebook in 2011.
* Then Instagram in 2012.
* Went open source in May 2013.

**BEHOLD! The OLD FACEBOOK!**  -->

<!-- *2008*

<img src='https://lh3.googleusercontent.com/d4ypmybEZT8SAOj1efmy9CCkKwNG3Dd-Mv0__FoIsWgK0iWuYWBS4NPHOf71ANpKcx2ElOndGeiDInxm8p-sOMqNXBkPy3y-HsH45lGscqJepxFOYkU1_6BbAw' alt='2008 facebook' width='600px'>

*2020*

<img src="https://cdn.vox-cdn.com/uploads/chorus_asset/file/19819048/News_Feed.jpg" alt="2020 facebook" width="600px"> 

React was born out of Facebook's frustration with the traditional MVC model and how...
  * Re-rendering something meant re-rendering everything (or just a lot).
  * That had negative implications on processing power and ultimately user experience, which at times became glitchy and laggy. -->


### React from horse's mouth

If you want to get a taste of what React is all about, [here's an introduction from React.js Conf 2015](https://www.youtube.com/watch?v=KVZ-P-ZI6W4&feature=youtu.be&t=510). Recommend starting around the 8:35 mark and watching until 16:30.

### React in MVC

React can be thought of as the "Views" layer in MVC, the part that the user will view and interact with.

React will work with any back-end language, but for our in-class examples we will be using Mongoose and Express for the models and controllers.

## A Break from Convention

In a traditional front end separation of concerns, we would have our markup (HTML) in one file and our logic (JavaScript) in another file. React strays from this concept mixing markup and logic in the same file, and instead separates concerns by **components**.

### What is a Component?

A component in React is a reusable chunk of user interface (UI).

Using the homepage of Wikipedia as an example, we could think of each language section as an instance of a language component. Each language section has the same structure but different content.

![wikipedia homepage](./images/wikipedia-homepage.png)

If we were to draw a box around each component on the homepage it might look something like this.

![wikipedia homepage components](./images/wikipedia-homepage-components.png)

We might have many instances of a language component (red), a component for the search bar (green), and a component for the dropdown button (blue). All of these components might live inside of a parent component for the page (orange). In this way, all of these components would be children of the page component.

In this way, we are able to break our user interface (UI) into smaller more manageble chunks. Each component holds the markup and the functionality for that particular chunk of UI.

### Another Example

Using Facebook as an example, you could think of each status post as a **component**. Each status post has the same structure but it might have different content, a different image, different text, and it might be associated with a different user.


You could then think of the news feed as a component that contains many of the smaller status post components within it. You could take this further and think of the entire page as a component. The news feed component would be a child of the page component. The sidebar and the header components would be children of the page component as well.

![facebook news feed](./images/facebook-newsfeed.png)

<!-- 
[Templates vs Components](https://wanderoak.co/fixed-templates-vs-components/)

![Templates Page](images/templates-page.png)
![Components Page](images/components-page.png)
> [WanderOak - Fixed Templates vs. Components](https://wanderoak.co/fixed-templates-vs-components/) -->


<!-- Let's see if we can identify the components in the Tube Tracker app below.

![Wireframe](images/wireframe.png)
![Wireframe with components](images/wireframe_deconstructed.png)
> [MakeTea - Building Robust Apps with React](http://maketea.co.uk/2014/03/05/building-robust-web-apps-with-react-part-1.html)

Notice the structure of how the various components are nested. 
```
- TubeTracker
    - Network
        - Line
    - Predictions
        - DepartureBoard
            - Trains
```

We can say that the entire Tube Tracker app is a component containing both the Network component and the Predictions component. We say that the Network and Predictions components are child components of the TubeTracker component and the TubeTracker component is a parent of the Network and the Predictions components. This parent/child relationship creates a tree-like structure which will become important to us later on. -->

## Exercise: Identifying Components

* Break into groups of three and take a look at a website of your choice (Facebook, Craigslist, Ebay, etc...). Identify the visual "components" the website is comprised of.

As you're drawing this out, think about the following questions...
* Where do you see "nested components"? Where do you not?
* Are there any components that share the same structure?
* Of these similar components, what is different about them?

----------------------------

## Code Along: Initial Setup

In order to create a new project and get our development environment setup, we are going to use a tool called `create-react-app`.

`create-react-app` is an NPM package that will handle the details of setting up a React project for us. It will install the necessary dependancies, and set up a server to serve our front end files to the browser. It will also watch our files for any changes and automatically update the browser when we save a file, also called "hot reloading".

It is possible to set up a React environment yourself, and many companies will set up their own custom React environments. However for our use cases, `create-react-app` will allow us to focus on learning how to use React and not worry about configuration.

In your terminal, navigate to the directory where you would like to create your React app. And then run the following commands.
```bash
$ npx create-react-app my-app
$ cd my-app
$ npm start
```

The command may take a few minutes to complete depending on your internet connection. `create-react-app` will create a new directory for our React project. For our example it will create a directory called 'my-app'. Inside the directory it will set up our React environment, complete with a server that will serve our React app to the browser.

We're using `npx` instead of `npm` here. `npx` allows us to run `create-react-app` without downloading the `create-react-app` package to our machines. `npx` allows us to run a hosted version of the package instead.

Navigate into the directory for your new React project.
```bash
cd my-app
```

And then start up the server.
```bash
npm start
```

We'll want to keep this server running while we are working on our app. You can now view your React app at `http://localhost:3000`! Take a look.

Open your new React app up in your code editor and take a look inside.

Along with installing the necessary dependencies, `create-react-app` creates an initial app skeleton that looks like this...

```bash
?????????README.md
?????????  favicon.ico
?????????  index.html
?????????  node_modules
?????????  package.json
?????????  public
???     ?????????index.html
?????????  src
      ?????????  App.css
      ?????????  App.js
      ?????????  index.css
      ?????????  index.js
      ?????????  logo.svg
```

Take some time and look at what's been generated. Specifically look at `index.html`, `index.js`, and `App.js` inside the `public` directory and the `src` directory.

### index.html

To render our React app on the page, our journey starts at the `/public/index.html` file.

When the browser first loads our app, the first thing to be loaded is this HTML file. We'll see a lot of comments in here explaining various parts of the file. For now, let's focus on the div in the body tag with the id of "root".

```html
<body>
  <div id="root"></div>
</body>
```

When our HTML file first loads on the page, some JavaScript will run behind the scenes to append our entire React application to this div with an id of "root".

### index.js

Let's take a looks inside `/src/index.js`. Notice the call to `ReactDOM.render()`.

```javascript
ReactDOM.render(
  <React.StrictMode>
    <App />
  </React.StrictMode>,
  document.getElementById('root')
);
```

<details>
  <summary>What is strict mode?</summary>

  The [StrictMode](https://reactjs.org/docs/strict-mode.html) component wrapping our app will perform additional checks and warnings, highlighting potential bugs or misuses or the React library.
</details>

This function call takes two arguments, the component we want to render, and the element on the page that we want to render our component to. This code will take our `<App />` component and render it on the page to the element with the id of "root".

Notice that before we render our `<App />` component to the page, we import it from another file, `App.js`.

```javascript
import App from './App';
```

### App.js

Let's take a look inside `./src/App.js`.

```javascript
function App() {
  return (
    <div className="App">
      <h1>Some markup</h1>
    </div>
  );
}
```

Here we define a function, `App` that simply returns some markup (HTML). Pull up your React app in the browser side by side with this file and you'll notice that the markup up here is what is being rendered to the page. Try changing the markup in the return statement. Change the content. Add an HTML element. Save the file, and watch the rendered outpage change as well.

### Components

This App function is a **React component**. Here in our `App.js` file we are defining our React component just as we would define a function. Just like any other function in JavaScript we can pass parameters in the parentheses `()` and our function has a return statement.


### JSX

You'll notice something funny about this function. We are not returning regular JavaScript. Instead we are returning markup, something that looks an aweful lot like HTML. This HTML-like syntax is called [**JSX**](https://reactjs.org/docs/introducing-jsx.html).

Behind the scenes our `create-react-app` setup will convert this **JSX** code into regular old JavaScript before sending it to the browser. By using **JSX** we can write code that strongly resembles HTML, a language we are already familiar with, and is easy to read and write.

### Rendering a Component

Now that our **React component** (function) has been defined we can render it to the page with this syntax, `<App/>`, just like we do in our `index.js` file. When we write `<App/>` we are calling the `App` function defined in `App.js` which just returns some markup.

Notice that we are also exporting our `App` component. In order to import `App` in our `index.js` file we must first export it from `./src/App.js`.

<details>
  <summary>Hungry for More: How does JSX get converted to JavaScript</summary>

  Behind the scenes our `create-react-app` setup is using a tool called "Webpack", which is using another tool called "Babel" to "transpile" this **JSX** into vanilla JavaScript and regular React code before bundling it up and sending it off to the browser.

  [Try it out yourself!](https://babeljs.io/repl)

  Using Babel's REPL you can define a component with React that returns JSX, and see what Babel will "transpile" your component into. It converts it into vanilla JavaScript and into JavaScript code written with the React library. Notice the function call to `React.createElement()`. Notice how this function is taking as arguments, the name of the element to be created, any HTML attributes attached to the element, and possibly another call to `React.createElement()` to render out the child elements of the parent.

  It is possible to write your React components this way by calling `React.createElement()`. However most developers agree using JSX is more intuitive and we'll be using JSX in this course.

  ### More about Babel
  Babel is a tool that can convert newer versions of JavaScript into a version of JavaScript widely supported by browsers. For example, ES12 => ES5.

  Babel can also be used to convert **JSX** into vanilla JavaScript and React code.

  ### What is Webpack?
  Webpack is a module bundler that can be configured to do all sorts of things in order to prepare our front end code into code that is ready to be sent to and read by a browser. For our uses, Webpack will take all of our React and JavaScript code, convert it into vanilla JavaScript, bundle it into a single JavaScript file, and then append it in a script tag to our `index.html` file. We can actually find this script tag by opening up the elements panel with our React app open.
</details>

At this point, take another look at the three files we've seen so far, `/public/index.html`, `/src/index.js`, and `/src/App.js`. See if you can trace the path that eventually leads to our `App` component rendering to the page.

## Code Along: Let's Code

<!-- Throughout class we have separated HTML, CSS and Javascript.
* With components, the lines between those three become a bit blurry.
* Instead, we organize our web apps according to small, reusable components that define their own content, presentation and behavior. -->

<!-- What does a component look like? Let's start with a simple "Hello World" example... -->

In our `/src/App.js` file, let's remove the boilerplate content that `create-react-app` sets up for us. We'll leave the App function intact and replace the return value with any markup you wish and watch it render to the page.

```javascript
function App() {
  return (
    <div>
      <h1>My React App</h1>
      <h2>Todo List:</h2>
      <ul>
        <li>Learn about components</li>
        <li>Learn about props</li>
        <li>Learn about state</li>
        <li>Give the dog a bath</li>
      </ul>
    </div>
  );
}

export default App;
```

As a rule the returned JSX can only have a single parent element.

This code would break.
```javascript
function App() {
  return (
    <h1>My React App</h1>
    <p>This is a paragraph tag</p>
  );
}
```

This would not.
```javascript
function App() {
  return (
    <div>
      <h1>My React App</h1>
      <p>This is a paragraph tag</p>
    </div>
  );
}
```

You can also wrap your markup in something called a [React fragment](https://reactjs.org/docs/fragments.html) which will not render as actual HTML in the browser for the empty tags (`<>` and `</>`).

```javascript
function App() {
  return (
    <>
      <h1>My React App</h1>
      <p>This is a paragraph tag</p>
    </>
  );
}
```

At the top of the file we can get rid of the import statements for the logo but keep the one for the CSS.

---

## Child Components

Remember how we said a component can have many child components within it? To understand this concept let's create a `Person` component and make it a child of the `App` component.

Create a new directory called `components` inside of your `src` directory.

In the terminal run
```bash
mkdir ./src/components
```

Create a file called `Person.js` in the `components` directory.
```bash
touch ./src/components/Person.js
```

Inside of the `Person.js` file, define our `Person` component and export it from the file.

```JS
function Person() {
  return (
    <div>
      <h2>Name: Flynn</h2>
      <p>Favorite Color: Blue</p>
    </div>
  );
}

export default Person;
```

We simply define a function called Person that returns some JSX.

- Notice how Person is capitalized. React components are always capitalized. We'll explain why in a bit.

- Notice how we wrap the JSX code in a set of parentheses. This allows us to put the JSX on a new line after the return and makes it easier to read.

- Notice the export statement which will allow us to import the component into another file.

Let's navigate back to the `App.js` file. First let's import our new `Person` component into `App.js`. Then let's render our `Person` component inside the `App` component replacing the existing content we had in there.

```javascript
import Person from './components/Person';
import './App.css';

function App() {
  return (
    <div className="App">
      <h1>My React App</h1>
      <Person />
    </div>
  );
}

export default App;
```

To render (or call) the `Person` component we simply include it in our JSX inside a set of opening and closing angle brackets. In this way the `Person` component is a child of the `App` component. The `App` component is a parent to the `Person` component. Any time we render the `App` component we will also render the `Person` component.

---

### Creating Many Instances

We can now easily create many instances of the `Person` component. We can render it as many times as we want.

```javascript
import Person from './components/Person';
import './App.css';

function App() {
  return (
    <div className="App">
      <h1>My React App</h1>
      <Person />
      <Person />
      <Person />
    </div>
  );
}

export default App;
```

---

### Multiple Child Components

Let's define a `Dog` component the same way we defined our `Person` component and then render it in our `App` component.

Create a file called `Dog.js` in your `components` directory.

```bash
touch ./src/components/Dog.js
```

Define the component returning some markup and export it at the bottom of the file.
```javascript
function Dog() {
  return (
    <div>
      <h2>Name: Sparky</h2>
      <p>Favorite Activity: Chasing the ball</p>
    </div>
  );
}

export default Dog;
```

Import it into the `App.js` file and then render the `Dog` component within the `App` component with `<Dog />`. We can create as many instances of the `Dog` component as we want. Here we render it twice.

```javascript
import Person from './components/Person';
import Dog from './components/Dog';
import './App.css';

function App() {
  return (
    <div className="App">
      <h1>My React App</h1>
      <Person />
      <Person />
      <Person />
      <Dog />
      <Dog />
    </div>
  );
}

export default App;
```

---

## Recipes App

The previous exercise was just a warm up. For this code-along activity we are going to be building an app to help users keep track of their recipes. The user will be able to browse recipes by categories, such as breakfast, lunch, and dinner, and create recipes of their own.

We'll keep the `Person` component and the `Dog` component for later activities when we introduce props in the next lesson.

When we are finished today, it will look something like this.

![Completed app](./images/completed-app.png)


### Some CSS

We are going to have a minimal amount of CSS for this activity to make it easier for us to work on. Delete the existing CSS inside of `./src/App.css` and paste in the following code.

<details>
  <summary>CSS for our Recipes App</summary>

  ```css
  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }

  ul {
    list-style: none;
  }

  a {
    text-decoration: none;
    color: #000;
  }

  a:visited {
    color: inherit;
  }

  button {
    padding: 6px 8px;
    margin: 0 20px 20px 0;
    cursor: pointer;
  }

  /* SITEWIDE *********************************************** */
  .container {
    max-width: 1000px;
    margin: 0 auto;
  }

  /* HEADER ************************************************* */
  .header {
    border: 2px solid #aaa;
    padding: 0 30px;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  .navList {
    display: flex;
  }

  .navLink {
    display: block;
    padding: 20px;
  }

  .navLink:hover {
    color: orange;
  }

  .main-page {
    display: flex;
  }

  /* SIDEBAR ************************************************* */
  .sidebar {
    width: 240px;
    min-width: 300px;
    border: 2px solid #aaa;
  }

  .sidebar-card {
    display: flex;
    padding: 20px;
    border-bottom: 2px solid #aaa;
    cursor: pointer;
  }

  .sidebar-card:hover {
    background: #efefef;
  }

  /* category INFO *********************************************** */
  .category-info {
    border: 2px solid #aaa;
    flex-grow: 1;
  }

  .category-detail {
    border: 2px solid #aaa;
    display: flex;
    justify-content: space-between;
    padding: 20px;
  }

  .category-content {
    padding-right: 15px;
  }

  .category-img {
    width: 525px;
    max-width: 50%;

  }

  /* RECIPES SECTION ******************************************* */
  .recipes-section {
    border: 2px solid #aaa;
    cursor: pointer;
  }

  .add-recipe-button {
    margin: 15px;
    padding: 7px 10px;
  }

  .recipe {
    border-top: 2px solid #aaa;
    padding: 18px;
  }

  .recipe:hover {
    background: #efefef;
  }

  /* RECIPE ADD PAGE ******************************************** */
  .form {
    margin: 0 auto;
    max-width: 1000px;
    padding: 20px;
  }

  .form-header {
    margin-bottom: 20px;
  }

  .form-group {
    display: flex;
    margin-bottom: 10px;
  }

  .form-label {
    width: 100px;
  }

  .form-input {
    width: 100%;
    border-radius: 3px;
    border: 2px solid #aaa;
    padding: 5px;
  }

  .form-input-body {
    height: 200px;
  }
  /* SHOW RECIPE PAGE **************************************** */
  .show-recipe-page {
    margin: 0 auto;
    max-width: 1000px;
    padding: 20px;
  }

  .recipe-category-name,
  .recipe-title,
  .recipe-body {
    margin-bottom: 10px;
  }
  ```
</details>

---

### Adding the Header Component

First let's create a `Header` component for our app. Create a `Header.js` file inside of the components directory.

```bash
touch ./src/components/Header.js
```

Inside of `Header.js` let's set up our `Header` component that returns the **JSX** for our header. It will include the app name and some navigation links.

```javascript
function Header() {
  return (
    <header className="header">
      <h1 className="header-title">Kitchenpedia</h1>

      <nav>
        <ul className="navList">
          <li><a className="navLink" href="/">Home</a></li>
          <li><a className="navLink" href="/">Explore</a></li>
        </ul>
      </nav>
    </header>
  );
}

export default Header;
```

We can now import our `Header` component into the `App.js` file and then render it inside of our `App` component. Let's get rid of the `Person` and `Dog` components as well.

```javascript
import Header from './components/Header';
import './App.css';

function App() {
  return (
    <div className="App">
      <Header />
    </div>
  );
}

export default App;
```

---

### Set Up the Home Page

Our app is going to be organized into different "pages" that the user can view. Let's create a `pages` directory where we will store all of our page components.

```bash
mkdir ./src/pages
```

Within the `pages` directory create a file called `HomePage.js` for our `HomePage` component.

```bash
touch ./src/pages/HomePage.js
```

Inside of `HomePage.js` set up a simple **React component** that returns some **JSX**.

```javascript
function HomePage() {
  return (
    <div className="container">
      <h1>Welcome to Kitchenpedia</h1>
    </div>
  );
}

export default HomePage;
```

We can now import the `HomePage` component into our `App.js` file and render it inside of our `App` component right under the `Header` component.

```js
import Header from './components/Header';
import HomePage from './pages/HomePage';
import './App.css';

function App() {
  return (
    <div className="App">
      <Header />
      <HomePage />
    </div>
  );
}

export default App;
```

---

### Set Up the Main Page

Let's create a `MainPage` component where we will be able select a category and view recipes for that category.

```bash
touch ./src/pages/MainPage.js
```
Inside of `MainPage.js` let's set up our component
```js
function MainPage() {
  return (
    <div className="main-page">
      
      <aside className="sidebar">
        Category Sidebar
      </aside>

      <main className="category-info">
        
        <section className="category-detail">
          Category Details
        </section>

        <section className="recipes-section">
          Recipes Section
        </section>
      </main>
    </div>
  );
}

export default MainPage;
```

Now import the `MainPage` component into the `App.js` file and render the `MainPage` component in the `App` component.

```js
import Header from './components/Header';
import HomePage from './pages/HomePage';
import MainPage from './pages/MainPage';
import './App.css';

function App() {
  return (
    <div className="App">
      <Header />
      {/* <HomePage /> */}
      <MainPage />
    </div>
  );
}

export default App;
```

Let's see what we have in the browser now. Alright, now we can see our header and the basic layout of our main page. Eventually we will be able to select a category from the sidebar and view information about that category and the recipes for that category.

We eventually want to be able to switch between the `HomePage` component and the `MainPage`component by clicking on the navigation links. For now though, to switch between them we can comment one out and uncomment the one we want to see. Let's comment out the `HomePage` component and uncomment the `MainPage` component.

---

### Add a Sidebar Component

Let's flesh out our `MainPage` component some more by creating some child components to render within it.

Because we will be creating a lot of components it will help us to create some additional structure. Let's create a directory called `mainPageComponents` inside of our `components` directory.

```bash
mkdir ./src/components/mainPageComponents
```

Within our `mainPageComponents` directory let's create a `Sidebar.js` file for our `Sidebar` component.

```bash
touch ./src/components/mainPageComponents/Sidebar.js
```

Inside of `Sidebar.js` define the `Sidebar` component.

```js
function Sidebar() {
  return (
    <aside className="sidebar">
      <ul>
        <li className="sidebar-card">Breakfast</li>
        <li className="sidebar-card">Soups</li>
        <li className="sidebar-card">Pasta Dishes</li>
      </ul>
    </aside>
  );
}

export default Sidebar;
```

And then let's render the `Sidebar` component within the `MainPage` component.

```js
import Sidebar from '../components/mainPageComponents/Sidebar';

function MainPage() {
  return (
    <div className="main-page">
      
      <Sidebar />

      <main className="category-info">
        
        <section className="category-detail">
          Category Details
        </section>

        <section className="recipes-section">
          Recipes Section
        </section>
      </main>
    </div>
  );
}

export default MainPage;
```

---

### Category Detail and Recipes Section

Let's set up the `CategoryDetail` component and the `RecipesList` component.

```bash
touch ./src/components/mainPageComponents/CategoryDetail.js
touch ./src/components/mainPageComponents/RecipesList.js
```

The `CategoryDetail` component will display some information about the featured category.

In `CategoryDetail.js`
```js
function CategoryDetail() {
  return (
    <div className="category-detail">
      <div className="category-content">
        <h2>Breakfast</h2>
        <p>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Velit quas architecto a aliquam voluptas omnis debitis ut sint, incidunt officia maxime? Assumenda voluptate, sint id cupiditate optio aliquid deleniti beatae?</p>
      </div>

      <img src="https://images.unsplash.com/photo-1533089860892-a7c6f0a88666" alt="" className="category-img"/>
    </div>
  );
}

export default CategoryDetail;
```

The `RecipesList` component will display a list of recipes for that particular category. For now we'll hard code some made up recipes for the breakfast category.

In `RecipesList.js`
```js
function RecipesList() {
  return (
    <section className="recipes-section">
      <button className="add-recipe-button">
        Add Recipe
      </button>

      <article className="recipe">
        <h4>Breakfast Potatoes</h4>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Blanditiis quidem corporis facilis, placeat pariatur unde mollitia magnam ratione deserunt ullam autem, quisquam commodi earum excepturi dolores voluptatem sequi repudiandae beatae!</p>
      </article>
      <article className="recipe">
        <h4>Rolled Oats</h4>
        <p>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Non cum nulla quisquam voluptatem animi fugiat optio dolor harum veritatis eaque perferendis, sunt quasi hic voluptates, error quod obcaecati maxime quo!</p>
      </article>
      <article className="recipe">
        <h4>French Toast</h4>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Totam sit accusantium quod sed dolorum perferendis deserunt voluptatem. Commodi sed natus adipisci veniam reiciendis eligendi corporis consequatur, ullam enim praesentium fugit.</p>
      </article>
    </section>
  );
}

export default RecipesList;
```
---

Now in our `MainPage` component we can import the `CategoryDetail` component and the `RecipesList` component. And then we can render them inside the `MainPage` component. In this way the `CategoryDetail` and `RecipesList` components are child components to the `MainPage` component. And the `MainPage` component is a child of the `App` component.

```js
import Sidebar from '../components/mainPageComponents/Sidebar';
import CategoryDetail from '../components/mainPageComponents/CategoryDetail';
import RecipesList from '../components/mainPageComponents/RecipesList';

function MainPage() {
  return (
    <div className="main-page">
      <Sidebar />
      <main className="category-info">
        <CategoryDetail />
        <RecipesList />
      </main>
    </div>
  );
}

export default MainPage;
```

---

### Creating a Recipe Component

Take a look back at the recipes component in `RecipesList.js`. You'll notice that each recipe follows the same exact structure and we're repeating a lot of code here unnecessarily. Let's create a `Recipe` component that we can render iside the `RecipesList` component for each recipe.

```bash
touch ./src/components/mainPageComponents/Recipe.js
```

For now we can copy the **JSX** of one of our recipes and paste it in the `Recipe` component.

```js
function Recipe() {
  return (
    <article className="recipe">
      <h4>Breakfast Potatoes</h4>
      <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Blanditiis quidem corporis facilis, placeat pariatur unde mollitia magnam ratione deserunt ullam autem, quisquam commodi earum excepturi dolores voluptatem sequi repudiandae beatae!</p>
    </article>
  );
}

export default Recipe;
```

Back in `RecipeList.js` we can import the `Recipe component and render it for each one of our recipes.

```js
import Recipe from './Recipe';

function RecipesList() {
  return (
    <section className="recipes-section">
      <button className="add-recipe-button">
        Add Recipe
      </button>

      <Recipe />
      <Recipe />
      <Recipe />
    </section>
  );
}

export default RecipesList;
```

This makes our `RecipesList` component much easier to read. If we take a look at the app in the browser, you'll notice that we are repeating the same recipe three times. Right now we are hard coding the "Breakfast Potatoes" content in the `Recipe` component. In the next section we are going to learn how we can pass information to a component so that it renders with different content each time using something called **React props**.

---

Alright, taking a look at our app in the browser, we can see our Recipes App start to come to life. None of the buttons work but the general features of the page are all there. Take some time to look over the code that we have written so far and trace how it all fits together. Start with the `index.js` file and work your way down the component tree. The `App` component is the parent of the `MainPage` component. The `MainPage` component is a parent to the `RecipesList` component and so forth. Trace the flow of components multiple times until you are sure you understand it. We are going to be building on all of this information in the next unit.

That concludes the code along for this lesson. We are starting to get a sense for how a React application can be constructed with these building blocks called **components**.

## The Virtual DOM

When our `index.html` file initially renders in the browser, React, using the DOM API under the hood, will take all of the **JSX** in our **components** and append it to the page as HTML.

Before it appends all that HTML to the page, it will create a giant JavaScript object representing all of the markup in the app and hold that JavaScript object in the browser's memory. This giant JavaScript object is a virtual representation of the DOM, the **Virtual DOM**.

In our Recipes App, let's say we were to click on a different category. We would want to see the details for that category and see the recipes for that category.

When the state of our application changes, React will compare the old version of our **Virtual DOM** with the new version of our **Virtual DOM**, note the differences, and only render the exact parts of the page that need need to change. We will revisit the concept when we work with **state** in React, but for now, know that the **Virtual DOM** allows React to be highly efficient in how it renders and changes content on the page.

[The React Docs on the Virtual DOM](https://reactjs.org/docs/faq-internals.html#what-is-the-virtual-dom)

## Review

* What is a component in React?
* What benefits do components provide?
* What is the parent/child relationship of the Recipes App we've created?
* How is our React app rendered to the page in the browser?
* What is JSX?
* What is the Virtual DOM?
* What features does `create-react-app` give us?

## Additional Resources

The [React documentation](https://reactjs.org/) is incredibly well put together and a great place to learn more about React.

The [Introductory Tutorial](https://reactjs.org/tutorial/tutorial.html) featured on the React documentation will give you a great introduction to using **props** and **state** in React and will be a good primer on some of the topics we will be covering in the next few lessons.

<!-- When we take a look at our `index.html` file in the public directory we see that there is no markup in the body tag except for one div with an id of "root". But when we put our app up in the browser, we see our app. In the browser, if we go to our developer tools and open the elements tab, we can see all of the HTML for our app. So what gives? -->


<!-- > Hey you got your html in my javascript!
>
> You got your javascript in my html!
>
> (https://youtu.be/O7oD_oX-Gio?t=5s) -->

<!-- Let's talk about the value that the render method returns. It looks an awful lot like an HTML heading, but it's not. We often write out React components in JSX.

JSX is [a language that compiles to Javascipt](https://reactjs.org/docs/introducing-jsx.html) that allows us to write code that strongly resembles HTML. It is eventually compiled to lightweight JavaScript objects.

Your Hello function: -->

<!-- * Currently returns JSX, not HTML.
The JSX creates a heading with 'Hello World!'.
* Your component reads this and renders a "Hello World!" heading.

> React can be written without JSX. If you want to learn more, [check out this blog post](http://jamesknelson.com/learn-raw-react-no-jsx-flux-es6-webpack/).  

Here is an example of React code without JSX-

![Templates Page](images/react-without-jsx.png) -->


<!-- ## Virtual DOM  -->

<!-- You may have noticed that our `src/index.js` code mentions ReactDOM. ReactDOM doesn't refer to the same DOM we know. Instead, it refers to a Virtual DOM. The Virtual DOM is a key piece of how React works.

The Virtual DOM is a Javascript representation of the actual DOM. The virtual DOM is a staging area for changes that will eventually be implemented.

* Because of that, React can keep track of changes in the actual DOM by comparing different instances of the Virtual DOM.
* React then isolates the changes between old and new instances of the Virtual DOM and then only updates the actual DOM with the necessary changes.
* By only making the "necessary changes," as opposed to re-rendering an entire view altogether, we save up on processing power.
* This is not unlike Git, with which you compare the difference -- or `diff` -- between two commits.

![Virtual DOM Diagram](https://docs.google.com/drawings/d/11ugBTwDkqn6p2n5Fkps1p3Elp8ZToIRzXzvM4LJMYaU/pub?w=543&h=229)

> If you're interested in learning more about the Virtual DOM, [check this video out](https://www.youtube.com/watch?v=-DX3vJiqxm4).

So we've created the template for our component. Now, let's use `/src/index.js` to load in our new component and render it on the DOM... -->

<!-- ```js
import React from 'react'
import ReactDOM from 'react-dom'
import Hello from './App.js'

ReactDOM.render(
  <Hello />,
  document.getElementById('root')
)
```
> In place of `ReactDOM.render` some tutorials will use React.renderComponent, which has been phased out. The change is outlined [here](http://bit.ly/1E81Whs).

`ReactDOM.render` takes the Virtual DOM node created by `extends Component` and adds it to the actual DOM. It takes two arguments...

  1. The component.
  2. The DOM element we want to append it to.

> **NOTE:** Whenever you use a self-closing tag in JSX, you **MUST** end it with a `/` like `<Hello />` in the above example. -->

<!-- --- -->

<!-- ### Review Questions
- How does JSX make your life as a developer easier?
- What are some of the advantages of having a virtual DOM? -->



<!-- ## Hello World: A Little Dynamic

Our `Hello` component isn't too helpful. Let's make it more interesting.
* Rather than simply display "Hello world", let's display a greeting to the user.
* So the question is, how do we feed a name to our `Hello` component without hardcoding it into our render method?

First, we pass in data wherever we are rendering our component, in this case in `src/index.js`...

```js
import React from 'react'
import ReactDOM from 'react-dom'
import Hello from './App.js'

ReactDOM.render(
  <Hello name={"Nick"} />,
  document.getElementById('root')
)
```

Then in our component definition, we have a reference to that data via as a property on the `props` object...

```js
function Hello(props) {
  return (
      <h1>Hello {props.name}</h1>
  );
}
```

In the above example, we replaced "world" with `{props.name}`.

### What are `.props`? -->

<!-- Properties! Every component has `.props`
* Properties are immutable. That is, they cannot be changed while your program is running.
* We define properties in development and pass them in as attributes to the JSX element in our `.render` method.

First we can pass multiple properties to our component when its rendered in `src/index.js`..

```js
import React from 'react';
import ReactDOM from 'react-dom'
import Hello from './App.js'

ReactDOM.render(
  <Hello name={"Nick"} age={24} />,
  document.getElementById('root')
)
```

Then in our component definition we have access to both values...

```js
function Hello(props) {
  return (
    <div>
      <h1>Hello {props.name}</h1>
      <p>You are {props.age} years old</p>
    </div>
  );
}
```

> **NOTE:** The return statement in `render` can only return one DOM element. You can, however, place multiple elements within a parent DOM element, like we do in the above example with `<div>`.

---

## You Do: A Blog Post 

Let's have some practice creating a React component from scratch. How about a blog post?
* Create a `post` object literal in `src/index.js` above `ReactDOM.render()` that has the below properties.
  1. `title`
  2. `author`
  3. `body`
  4. `comments` (array of strings)
* Render these properties using a Post component.
* The composition of your Post is up to you.

If you finish early, try experimenting with CSS (Make Sure you use `className` instead of `class` in `JSX`!)


<details><summary>Solution</summary>

*Post.js*

```
import React from 'react';

function Post(props) {
	return(
        <div>
            <h1>{props.title}</h1>
            <p>By {props.author}</p>
            <div>
                <p>{props.body}</p>
            </div>
            <h3>Comments:</h3>    
            <p>{props.comments[0]}</p>
        </div>
    )
}

export default Post;
```

*index.js*

```
import Post from './Post';

const post = {
    title: "Avengers",
    author: "Nick Fury",
    body: "I secretly recruited a group of superheroes to save our world.",
    comments: [
      "I love Avengers.",
      "Forget Avengers, we want the Witcher.",
		"At least let aliens destroy D&D for what they did to GOT!"
    ]
}

ReactDOM.render(
    <Post 
        title={post.title} 
        author={post.author}
        body={post.body} 
        comments={post.comments}/>, 
    document.getElementById('root')
);
```

</details>


---


#### Q: What problems did you encounter when trying to add multiple comments to your Post?

It would be a pain to have to explicitly define every comment inside of `<Post />`, especially if each comment itself had multiple properties.
* This problem is a tell tale sign that our separation of concerns is being stretched, and it's time to break things into a new component.

We can nest a Comment component within a Post component.
* We create these comments the same way we did with posts
* Then we can reference a comment using `<Comment />` inside of Post's return method.

Let's create a new file for our Comment component, `src/Comment.js`...

```js
import React from 'react';

const Comment = (props) => {
    return(
        <div>
            <p>{props.message}</p>
        </div>
    )
}

export default Comment;
```

Then in `Post.js`, we need to load in our `Comment` component and render it inside of our `Post` component...

```js
import React from 'react';
// Load in Comment component
import Comment from './Comment.js'


function Post(props) {
	return (
	  <div>
	    <h1>{props.title}</h1>
	    <p>By {props.author}</p>
	    <div>
	      <p>{props.body}</p>
	    </div>
	    <h3>Comments:</h3>
	    // Render Comment component, passing in data
	    <Comment message={props.comments[0]} />
	  </div>
	);
}

export default Post;
```

> **Note**: We could put all of our code in one file, but it's considered a good practice to break components out into different files to help practice separation of concerns. The only downside is we have to be extra conscious of remembering to **export / import** each component to where it's rendered.

The above code works, but we'd have to hard-code all of our `Comments`.  This is not very dry and our code will not dynamically change.  The best way to handle this is to set a variable equal to all of the `<Comments />` for this post.  We can do this using `.map` in `Post` function.

We can use `.map` in `Post` function to avoid having to hard-code all of our `Comments`

```js
import React from 'react';
import Comment from './Comment';

function Post(props) {
    let comments = props.comments.map((comment, index) => (
        <Comment message={comment} key={index}/>
    ))

    return(
        <div>
            <h1>{props.title}</h1>
            <p>By {props.author}</p>
            <div>
                <p>{props.body}</p>
            </div>
            <h3>Comments:</h3>    
            {comments}
        </div>
    )
}

export default Post;
```

---

## Closing

-->
