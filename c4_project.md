
PROJECT MOCK DESIGN
![desktop-active-states](https://github.com/KwameGH22/StepByStepCodeExecution/assets/111309120/47271f23-e5a5-485c-b94d-f80dec4a97a0)
**
**
CLONING A GITHUB VITE-REACT APP TO LOCAL MACHINE**
--

Step 1**
  --Follow the link to the project assignment GitHub repository provided in teams

	
**Step 2**
--The link will lead you to the project repository interface on GitHub.

**Step 3**
--At the Project repository interface, look for the <code>fork tab</code> to create a forked branched of the repository.

**Step 4**
--Inside your repository and in the forked C4-project directory, click the code tab to display the project URL.

**Step 5**
--Using the copy icon at the extreme right of the URL copy the URL link to the clipboard.

**Step 6**
--Open VS Code and on the menu button select the file menu option followed by the open folder option from the drop down.

**Step 7**
--Using the windows file explorer dialogue pop-up box select your referred repository and click open in VS code.

**Step 8**
--Inside VS Code, and on the menu bar look for the three dots (...) and click to reveal the dropdown options: terminal and help. Hover on the terminal option to reveal new terminal option.

**Step 9**
--Select the new terminal option. Clicking on the new terminal option creates at the bottom the VS Code interface a new terminal with a menu bar. At the extreme right of the menu bar is located a group of menu icons. Adjacent to the + icon is the drop down icon which upon clicking opens up a menu list containing the GIT BASH option.

**Step 10**
--Selecting the Git Bash option opens the git bash terminal inside the local assignment project repository.

**Step 11**
--At the git bash terminal prompt type the command : 
```bash
	git clone https://github.com/KwameGH22/c4_project.git
```
	and hit the return key and wait for the remote directory files to download to your preferred folder. 
 
**Step 12**
--At the terminal use the command:
```bash
	cd c4_project
```
	to change into the react-vite project. 
 
**Step 13**
--To identify whether you are in the right project directory, check for the label (main) at the end of the terminal address.

**Step 14**
--After satisfying that you are in the right directory, run the command:
```bash
	npm install
```
	to install the necessary packages into the react-vite project. 
 
**DESIGN IMPLEMENTATION**
--

 
**Step 15**
--Inside the src folder create a subfolder and name it components.

**Step 16**
--Inside the src folder create additional subfolders and name them: pages and styles respectively.

**Step 17**
--Inside the components folder create 7 jsx file with the following identities: shortlyLanding.jsx, Navbar.jsx, Forms.jsx, FormDisplay.jsx, Main.jsx, Action.jsx, and Footer.jsx.

**Step 18**
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

**Step 19**
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
**Step 20**
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
***Step 21**
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
***Step 22**
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
***Step 23**
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
**Step 24**
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

**Step 25**
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
**Step 26**
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
**Step 27**
--Inside the styles folder create a CSS Module Stylesheet with the identity navbar.module.css.

**Step 28**
--Inside the Navbar.jsx file import the CSS Module Stylesheet with the following import statement: 
```bash
	import styles from '../styles/navbar.module.css'
```



