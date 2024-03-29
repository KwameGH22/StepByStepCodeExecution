
**PROJECT MOCK DESIGN**
--
![desktop-active-states](https://github.com/KwameGH22/StepByStepCodeExecution/assets/111309120/47271f23-e5a5-485c-b94d-f80dec4a97a0)

**CLONING A GITHUB VITE-REACT APP TO LOCAL MACHINE**
--

Step 00**
  --Follow the link to the project assignment GitHub repository provided in teams

	
**Step 00**
--The link will lead you to the project repository interface on GitHub.

**Step 00**
--At the Project repository interface, look for the <code>fork tab</code> to create a forked branched of the repository.

**Step 00**
--Inside your repository and in the forked C4-project directory, click the code tab to display the project URL.

**Step 00**
--Using the copy icon at the extreme right of the URL copy the URL link to the clipboard.

**Step 00**
--Open VS Code and on the menu button select the file menu option followed by the open folder option from the drop down.

**Step 00**
--Using the windows file explorer dialogue pop-up box select your referred repository and click open in VS code.

**Step 00**
--Inside VS Code, and on the menu bar look for the three dots (...) and click to reveal the dropdown options: terminal and help. Hover on the terminal option to reveal new terminal option.

**Step 00**
--Select the new terminal option. Clicking on the new terminal option creates at the bottom the VS Code interface a new terminal with a menu bar. At the extreme right of the menu bar is located a group of menu icons. Adjacent to the + icon is the drop-down icon which upon clicking opens up a menu list containing the GIT BASH option.

**Step 00**
--Selecting the Git Bash option opens the git bash terminal inside the local assignment project repository.

**Step 00**
--At the git bash terminal prompt type the command : 
```bash
	git clone https://github.com/KwameGH22/c4_project.git
```
	and hit the return key and wait for the remote directory files to download to your preferred folder. 
 
**Step 00**
--At the terminal use the command:
```bash
	cd c4_project
```
	to change into the react-vite project. 
 
**Step 00**
--To identify whether you are in the right project directory, check for the label (main) at the end of the terminal address.

**Step 00**
--After satisfying that you are in the right directory, run the command:
```bash
	npm install
```
	to install the necessary packages into the react-vite project. 
 
 **INSTALLING REQUIRED EXTERNAL LIBRARIES AND PLUGINS**
 --
 **REACT ROUTER DOM**
 
 **Step 00**
 --React makes use of an external library to handle routing; however, before we can implement routing with that library, we must first install it in our project, which is accomplished by running the following command in my terminal (within your project directory):
 ```bash
	npm install react-router-dom 
```
 and wait for the react-router-dom external library to download and install.

 **SETTING UP REACT-ROUTER IN MY PROJECT**
 
 --**Step 00**
 --After successfully installing the package, I can now set up and configure react-router within my project to enable client side routing for my web app. To configure React router, navigate to the <code>main.jsx</code> file, which is the root file, and create and render a <code>BrowserRouter</code>. To create a BrowserRouter first import the <code>createBrowserRouter</code>, <code>RouterProvider</code> and <code>CreateRoutesFromElements</code> components from the react-router-dom package that we installed, as follows:
 ```bash
	// main.jsx
import React from 'react';
import ReactDOM from 'react-dom/client';
import { createBrowserRouter, CreateRoutesFromElements, RouterProvider, } from 'react-router-dom';//Step 00
import App from './App';


```
--**Step 00**

--To render the <code>BrowserRouter</code> create an instance object of the createBrowserRouter function naming it <code>router</code> and call the CreateRoutesFromElements function in which you would call the <Route></Route> component element. 

```bash
	const router = createBrowserRouter(  //Step 00
	   CreateRoutesFromElements(	//Step 00
	     <Route>     //Step 00

             </Route>

	)
);
```


**Step 00**
--Inside the opening <Route> component tag, you are required to call two <code>props</code> namely: <code>path:</code> and <code>element:</code>. as illustrated below:

```bash
	<Route path=''	   //Step 00
	       element={ }  //Step 00
	>
		
	</Route>
```

**Step 00**
-- We can then set the values of the props: <code>path</code> and <code>element</code> to a forward slash <code>(/)</code> representing the root route and then a root layout component like this:

```bash
	<Route path='/'	   //Step 00
	       element={<RootLayout/> }  //Step 00
	>
		
	</Route>
```
Note that,  configuring the opening Route JSX component tag, that is <Route> with the forward slash (/) and the RootLayer component only sets the stage for actual routing to our web pages. The RootLayer component serves to provide a fixed Layout that gets inherited by all other pages.

--**Step 00**

--Within React.StrictMode JSX tag of the render method of the ReactDOM component, the <code>RouterProvider</code> component which was imported together with the createBrowserRouter component is called and nested within the <code>React.StrictMode</code> component and given the component props <code>router</code> and value of <code>{router}</code> as follows:

```bash
	ReactDOM.createRoot(document.getElementById("root")).render(
	  <React.StrictMode>Step 00
	    <RouterProvider router={router} />Step 00
	  </React.StrictMode>
);
```

 **CONFIGURING ROUTES IN MY PROJECT**
 
 --**Step 00**
 
 --At this point, i have now successfully installed and imported React-router into my project; the next step is to implement routing. The first step is to configure all of my routes (that is, all the pages/components to which we want to navigate).

 **CONFIGURING THE ROOT ROUTE OF MY REACT WEB APP**

 **Step 00**
 
 --After implementing the non-navigable root route as a wrapper for our other routes, we call the  first Route self-closing component within the "Route wrapper" whose's path and element props are set to index and <Home/> using the statement below to create our FIRST ROUTE to our Home Page:
 ```bash
	const router = createBrowserRouter(  //Step 00
	   CreateRoutesFromElements(	//Step 00
	     <Route path='/' element={RootLayer}>     //Step 00
		<Route index
		       element={<Home/>}
		       errorElement={<ErrorPage />}
		/>
             </Route>

	)
);
```



 **Step 00**
 
 --Following the creation of the root route, the Rootlayout component is the next to be created. So within the components folder setup a <code>.jsx</code> file with the identity <code>RootLayout.jsx</code>. For my application, the RootLayout component would be set to contain the Header component, as illustrated below:
 
  ```bash
	//RootLayer.js file
	import React from 'react';
	import Header from './Header';
	



	const RootLayout = () => {
	  return (
	    <div>
	        <Header/>
	       
	    </div>
	  )
	}

export default RootLayout;
```

 **CONFIGURING THE ERROR ROUTE OF MY REACT WEB APP**

 **Step 00**
 
 --The ErrorPage or route is configured by introducing a second element property of the first router object called <code>errorElement</code>using the statement below:
 ```bash
	const router = createBrowserRouter(  //Step 00
	   CreateRoutesFromElements(	//Step 00
	     <Route path='/' element={RootLayer}>     //Step 00
		<Route index
		       element={<Home/>}
		       errorElement={<ErrorPage />}    //Step 00
		/>
             </Route>

	)
);
```

**Step 00**
 
 --Following the creation of the Error route, the ErrorPage component is the next to be created. 
 
 **Step 00**
 --So within the components folder set up a <code>.jsx</code> file with the identity <code>ErrorPage.jsx</code> and implement the code below which was copied from the react-router tutorial website to handle page not found errors. 
 
 To set this ErrorPage setup, however, would not be possible if the <code>useRouteError</code> Hook from the react-router-dom is first not imported. The useRouteError hook function is used to create an error object instance whose methods such as the <code>error.statusText</code> and <code>error.message</code> are assessed in the return statement of the ErrorPage component.

```bash
import { useRouteError } from "react-router-dom";  //Step 00

export default function ErrorPage() {
  const error = useRouteError();
  console.error(error);

  return (
    <div id="error-page">
      <h1>Oops!</h1>
      <p>Sorry, an unexpected error has occurred.</p>
      <p>
        <i>{error.statusText || error.message}</i>
      </p>
    </div>
  );
}
```

**Step 00**
--

**IMPORTING SVG FILES AS REACT COMPONENTS IN MY VITE REACT APP**
--

**Steo 00**
--Install the <code>vite-plugin-svgr</code> in your project directory using the following command:
:
```bash
	npm install vite-plugin-svgr
```

and wait for it to download and install the plugin.

**Step 00**
--Add the plugin to your vite-config.js file by importing the svgr component and adding it to the object parameter of the <code>defineConfig function</code> like this:


```bash
	import { defineConfig } from 'vite'
	import react from '@vitejs/plugin-react'
	import svgr from 'vite-plugin-svgr'   //Step 00
	
	// https://vitejs.dev/config/
	export default defineConfig({
	  plugins: [react()],
	  plugins: [svgr()],   //Step 00
	})
```
**Step 00**
--To use the svg file in any component first import it into that component using the statement: 

<code>import { ReactComponent as WhateverIcon } from "./icons/WhateverIcon.svg";</code>

**IMPORTING REACT-ICONS AS REACT COMPONENTS IN MY VITE REACT APP**
--

**Steo 00**
--Install the <code>vite-plugin-react-icons</code> in your project directory using the following command:
:
```bash
	npm i -D vite-plugin-react-icons @iconify/json
```

and wait for it to download and install the plugin.

**Step 00**
--Add the plugin to your vite-config.js file by importing the <code>reactIcons</code> component and adding it to the object parameter of the <code>defineConfig function</code> like this:


```bash
	import { defineConfig } from 'vite'
	import react from '@vitejs/plugin-react'
	import svgr from 'vite-plugin-svgr'
	import reactIcons from 'vite-plugin-react-icons';  //Step 00

	
	// https://vitejs.dev/config/
	export default defineConfig({
	  plugins: [react()],
	  plugins: [svgr()],
	  plugins: [reactIcons()],   //Step 00
	})
```
***INSTALLING TAILWINDCSS AND IT'S DEPENDANCIES IN MY VITE-REACT PROJECT***
**Step 00**
--Navigate to your project directory and run the command :
```bash
	npm install -D tailwindcss postcss autoprefixer
```
--and wait for the dowmload and installation to complete.

**Step 00**
--To generate the tailwindcss configuration files run the command:
```bash
	npx tailwindcss init -p
```

**Step**
--To configure source paths add all of your template files in your <code>tailwind.config.cjs</code> file. Template files include <code>HTML templates</code>, <code>JavaScript components</code>, and <code>other source files that contain Tailwind class names</code>. This is to make sure that vanilla CSS is generated for the corresponding elements. Find the content of <code>tailwind.config.cjs</code> file below: 

```bash
	/** @type {import('tailwindcss').Config} */
export default {
  content: [],
  theme: {
    extend: {},
  },
  plugins: [],
}

```

**Step**
--Add the template files <code>"./index.html",</code> and <code>"./src/**/*.{js,ts,jsx,tsx}",</code>to the content property of the export default object like this:
```bash
	/** @type {import('tailwindcss').Config} */
export default {
  content: [
    "./index.html",
    "./src/**/*.{js,ts,jsx,tsx}",
  ],
  theme: {
    extend: {},
  },
  plugins: [],
}
```

**Step 00**
--Add the statements below to your ./src/index.css file:
```bash
	@tailwind base;
	@tailwind components;
	@tailwind utilities;
```


**DESIGN IMPLEMENTATION**
--

 
**Step 00**

--Inside the <code>src</code> folder create two (2) subfolders named components, and pages respectively.


**Step 00**

--Inside the components folder create 7 jsx files with the following identities: <code>shortlyLanding.jsx</code>, <code>Navbar.jsx</code, <code>Forms.jsx</code>, <code>FormDisplay.jsx</code>, <code>Main.jsx</code>, <code>Action.jsx</code>, and <code>Footer.jsx</code> and an additional 7 this time around being the CSS versions, i.e <code>shortlyLanding.css</code>, <code>Navbar.css</code, <code>Forms.css</code>, <code>FormDisplay.css</code>, <code>Main.css</code>, <code>Action.css</code>, and <code>Footer.css</code>

**NAVBAR COMPONENT SETUP**
--

**Step 00**
--Inside the Navbar.jsx file, run the react snippet "rafce" which stands for react arrow function component export" and hit the return key to generate a boilerplate code of a named (Navbar) functional component block with an export statement: 
```bash
	import React from 'react';



	const Navbar = () => {
	  return (
	    <div>Navbar</div>
	  )
	}

export default Navbar
```

**Step 00**
--Give the parent div after the return keyword of the navbar component a className attribute with a value of Navbar-container:
```bash
	import React from 'react';



	const Navbar = () => {
	  return (
	    <div className='Navbar-container'>//step 19
            </div>
	  )
	}

export default Navbar
```
**Step 00**
--within the parent div of ClassName 'Navbar-container' append a child div tag with className set to 'menu-items':
```bash
	import React from 'react';



	const Navbar = () => {
	  return (
	    <div className='Navbar-container'>//step 19
		<div className='menu-items'>//step 20
                </div>
            </div>
	  )
	}

export default Navbar
```
***Step 00**
--Inside the menu-items div append an unordered list tag with a className of 'nav-items':
```bash
	import React from 'react';



	const Navbar = () => {
	  return (
	    <div className='Navbar-container'>//step 19
		<div className='menu-items'>//step 20
		   <ul className='nav-items'>// step 21
		   </ul>
                </div>
            </div>
	  )
	}

export default Navbar
```
***Step 00**
--Inside the nav-items unordered list tag append four (4) list item tags with the following classNames: logo, features, pricing and resources:
```bash
import React from 'react';


const Navbar = () => {
  return (
    <div className="navbar-container">
        <div className='menu-items'>//step 20
            <ul className='nav-items'>//step 21
                <li className="logo"></li>step 22
                <li className="features">Features</li>//step 22
                <li className="pricing">Pricing</li>//step 22
                <li className="resources">Resources</li>//step 22
            </ul>
           
        </div>

    </div>
  )
}

export default Navbar
```
***Step 00**
--Inside logo list-item tag append four an imag child tag with the following attributes src and alt:
```bash
import React from 'react';


const Navbar = () => {
  return (
    <div className="navbar-container">
        <div className='menu-items'>//step 20
            <ul className='nav-items'>//step 21
                <li className="logo">//step 22
                    <img src = "" alt=""/>//step 23
                </li>
                <li className="features">Features</li>//step 22
                <li className="pricing">Pricing</li>//step 22
                <li className="resources">Resources</li>//step 22
            </ul>
           
        </div>

    </div>
  )
}

export default Navbar
```
**Step 00**
--To import the logo image into our Navbar component, first establish the correct file path to the image as this is required to import the image into our Navbar module (component); the Navbar.jsx file is located in the components folder: components/Navbar.jsx. Meanwhile the logo.svg file is located in the images folder which is also located in the assets folder: assets/images/logo.svg. So to import the image file into the component we need to step out of the file and then the components folder by ../. The final import path then becomes ../assets/images/logo.svg.: 
```bash
import React from 'react';
import logo from '../assets/images/logo.svg'; //step 24


const Navbar = () => {
  return (
    <div className="navbar-container">
        <div className='menu-items'>//step 20
            <ul className='nav-items'>//step 21
                <li className="logo">//step 22
                    <img src = "logo" alt="logo-image"/>//step 23
                </li>
                <li className="features">Features</li>//step 22
                <li className="pricing">Pricing</li>//step 22
                <li className="resources">Resources</li>//step 22
            </ul>
           
        </div>

    </div>
  )
}

export default Navbar
```
this enables us to import the image as a javascript object into our component hence setting the src attribute of our img tag to the object: {logo} and our alt attribute to 'logo-image'.

**Step 00**
--Within the menu-items div append a sibling div with className button-group and within this div append two button tags with classNames login and sign-up respectively:
```bash
import React from 'react';
import logo from './assets/images/logo.svg';


const Navbar = () => {
  return (
    <div className="navbar-container">
        <div className='menu-items'>
            <ul className='nav-items'>
                <li className="logo">
                    <img src = {logo} alt="logo-image"/>
                </li>
                <li className="features">Features</li>
                <li className="pricing">Pricing</li>
                <li className="resources">Resources</li>
            </ul>
            <div className='button-group'>//step 25
                <button className='login'>Login</button>//step 25
                <button className='signup'>Sign Up</button>//step 25
            </div>
        </div>

    </div>
  )
}

export default Navbar
```
**Step 00**
--Navigate the project file structure to the component folder then into the <code>Shortlylanding.jsx</code> file and run the rafce code snippet to generate the functional component boilerplate. After the return keyword and with the parent div append <code>Navbar JSX component tag</code>. NOTE that the addition of the <code>JSX component tag</code> automatically imports the component at the top of the ShortlyLanding file:
```bash
import React from 'react'
import Navbar from './Navbar'//note 1

const ShortlyLanding = () => {
  return (
    <div>
        <Navbar/>
    </div>
  )
}

export default ShortlyLanding
```
**STYLING THE NAVBAR COMPONENT**
--
**Step 00**
--Inside the styles folder create a CSS Module Stylesheet with the identity navbar.module.css.

**Step 00**
--Inside the Navbar.jsx file import the CSS Module Stylesheet with the following import statement: 
```bash
	import styles from '../styles/navbar.module.css'
```
**Step 00**
--To apply the styles in the module, all classNames should be referenced as javascript <code>STYLES</code> objects where the classNames are recognized as Object properties: 
```bash
	 <div className={styles.navbar-container}>
```



