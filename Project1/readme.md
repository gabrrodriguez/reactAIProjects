# Project 1

## Procedure

### Initial Bootstrap Process
1. Init project 
```s
npm create vite@latest ai-chat-bot -- --template react
```

2. Run project dependencies
```s
cd ai-chat-bot
npm install
npm run dev
```

3. Clean up boiler plate code

```s
rm -rf ./public/vite.svg
rm -rf ./src/assets/react.svg
rm -rf ./src/App.css
```

4. In the `index.html` file make the following changes: 
```s
# remove line -> "<link rel="icon" type="image/svg+xml" href="/vite.svg" />" from the index.html file
# Change the "<title></title>" to "<title>AI Chatbot Application</title>"
```

5. Clear the content of the `index.css` file

6. Remove the content of the `App.jsx` file and replace with this content
```js
import React from 'react'

const App = () => {
  return (
    <div>App</div>
  )
}

export default App
```

7. Under the `src` folder create a folder called `Components`. 
```s
mkdir ./src/Components
```

8. Add a new file to the `Components` file called `ChatBotStart.jsx` 
```s
touch ./src/Components/ChatBotStart.jsx
```

9. In the `ChatBotStart.jsx` file input the following code:
```js
import React from 'react'

const ChatBotStart = () => {
  return (
    <div>ChatBotStart</div>
  )
}

export default ChatBotStart
```

10. Import the `ChatBotStart` component into the `App.jsx` file: 
```js
import React from 'react'
import ChatBotStart from './Components/ChatBotStart'

const App = () => {
  return (
    <div>
      <ChatBotStart/>
    </div>
  )
}

export default App
```

### Create Start page

1. Import `BoxIcons`. Go to this [site](https://boxicons.com/usage#import-css). Grab the code to import the `.css`. Paste the `css` link to the `index.html` file. 

```html
<link href='https://unpkg.com/boxicons@2.1.4/css/boxicons.min.css' rel='stylesheet'>
```

2. Import `FontAwesome`. Go to this [site](https://cdnjs.com/libraries/font-awesome) to grab the _cdnjs_ link. Paste the link to the `index.html` file.

```html
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.6.0/css/all.min.css" integrity="sha512-Kc323vGBEqzTmouAECnVceyQqyqdsSiqLQISBL29aUW4U/M7pSPA/gEUZQqv1cwx4OnYxTxve5UMg5GT6L4JJg==" crossorigin="anonymous" referrerpolicy="no-referrer" />
```

3. Go to the `ChatBotStart.jsx` file and input the following code: 

```js
import React from 'react'

const ChatBotStart = () => {
  return (
    <div className="start-page">
      <button className="start-page-btn">Chat AI</button>
    </div>
  )
}

export default ChatBotStart
```

4. Add a `container` class to our App.jsx file

```js
import React from 'react'
import ChatBotStart from './Components/ChatBotStart'

const App = () => {
  return (
    <div className="container">
      <ChatBotStart/>
    </div>
  )
}

export default App
```

5. Use the `index.css` file for our global stylings. 
5a. Import our stylings into  and import the file to the `ChatBotStart.jsx` file via an import statement
```s
import './ChatBotStart.css'
```

6. Import Google Font Families into the `index.css` file. Go to this [site](https://fonts.google.com/?preview.layout=grid). 
6a. Select `Exo 2`, and ``Outfit` fonts. 
6b. Select `Get Embed Code`. 
6c. Select `import` to create the _@import_ statement you'll need to include in your .css file. 
6d. Paste the following at the top of the `ChatBotStart.css` file deleting the `<style></style>` tags.

```html
<!-- ChatBotStart.css File -->
@import url('https://fonts.googleapis.com/css2?family=Exo+2:ital,wght@0,100..900;1,100..900&family=Outfit:wght@100..900&display=swap');

...
```

7. Now update the `index.css` file as follows: 


```css
@import url('https://fonts.googleapis.com/css2?family=Exo+2:ital,wght@0,100..900;1,100..900&family=Outfit:wght@100..900&display=swap');

* {
    margin: 0;
    padding: 0; 
    box-sizing: border-box;
    outline: none;
    font-family: 'Outfil', sans-serif;
}

html {
    font-size: 62.5%;
}

.container {
    width: 100%; 
    height: 100vh;
    display: grid;
    place-items: center;
    background-color: #131927;
}
```

8. Create a Component level css file called `ChatBotStart.css` and place in the components directory. In this file input the following code: 

```css
.start-page {
    width: 100%; 
    height: 100%; 
    display: grid;
    place-items: center;
}

.start-page-btn {
    width: 35rem;
    height: 15rem;
    background: linear-gradient(135deg, #f42ff4, #8e25bf);
    border: none;
    border-radius: 1rem;
    font-family: "Exo 2", sans-serif;
    font-size: 7rem;
    font-weight: bold;
    color: #eee;
    text-transform: uppercase;
    letter-spacing: 1rem;
    text-shadow: 0 1rem 2rem rgba(0,0,0,2);
    box-shadow: 0rem 2rem 5rem rgba(0,0,0,2) ;
    cursor: pointer;
    transition: transform .1s ease;
}

.start-page-btn:active {
    transform: scale(0.98);
}
```

9. Create a partent component called `ChatBotApp` to manage our Chatbot Components. In the Componets folder create a file called `ChatBotApp.jsx` file. 

```s
touch ./src/Components/ChatBotApp.jsx
```

10, Open the `ChatBotApp.jsx` file and input the following code: 
```js
import React from 'react'

const ChatBotApp = () => {
  return (
    <div>ChatBotApp</div>
  )
}

export default ChatBotApp
```

11. Update the `App.jsx` file to import and reference the `ChatBotApp` Component now instead of the `ChatBotStarter` component. 
```jsx
import React from 'react'
// import ChatBotStart from './Components/ChatBotStart'
import ChatBotApp from './Components/ChatBotApp'

const App = () => {
  return (
    <div className="container">
      {/* <ChatBotStart/> */}
      <ChatBotApp/>
    </div>
  )
}

export default App
```

12. Update the `ChatBotApp.jsx` file with the following: 

```js
import React from 'react'

const ChatBotApp = () => {
  return (
    <div className="chat-app">
        <div className='chat-list'>
            <div className="chat-list-header">
                <h2>Chat List</h2>
                <i className="bx bx-edit-alt new-chat"></i>
            </div>
            <div className="chat-list-item">
                <h4>20/07/2024 12:59:42pm </h4>
                <i className="bx bx-x circle"></i>
            </div>
            <div className="chat-list-item">
                <h4>20/07/2024 12:59:42pm </h4>
                <i className="bx bx-x circle"></i>
            </div>
            <div className="chat-list-item">
                <h4>20/07/2024 12:59:42pm </h4>
                <i className="bx bx-x circle"></i>
            </div>
        </div>
        <div className="chat-window">
            <div className="chat-title">
                <h3>Chat with AI</h3>
                <i className="bx bx-bx-arrow-back arrow"></i>
            </div>
            <div className="chat">
                <div className="prompt">
                    Hi How are you?
                    <span>12:59:51 PM</span>
                </div>
                <div className="response">
                    Hello I'm just a computer program so I don't have feelings, but I'm here and ready to assist you. How can I help you today?
                    <span>12:59:52 PM</span>
                </div>
                <div className="typing">Typing ...</div>
            </div>
            <form className="msg-form">
                <i className="fa-solid fa-face smile emoji"></i>
                <input type="text" className="msg-input" placeholder="Type a message..." />
                <i className="fa-solid fa-paper-plane"></i>
            </form>
        </div>
    </div>
  )
}

export default ChatBotApp
```

13. Create a file called `ChatBotApp.css`. 
```s
touch ./src/Components/ChatBotApp.css
```

13a. Import this file into the `ChatBotApp.jsx` file
```js
import './Components/ChatBotApp'
```

13b. And input the following code styles to format the ChatBotApp component.

```css

```