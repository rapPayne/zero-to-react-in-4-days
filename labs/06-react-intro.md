# React Intro Lab

Up to now we've been exercising HTML and CSS as a buildup to React. In the next labs you'll be asked to create a React app with components that resemble those you've created as vanilla HTML/CSS files. Feel free to reuse as much of that old code as you want. 

## Creating a React app

1. Create a new React app using vite. Name the project "restaurant". Make sure you specify that this app uses TypeScript as its language.
1. Run and test it. Make a change or two to the App component to prove that it works alright and that you understand the flow of the app.

## Attaching the API
In this section we're going to get our React app and our RESTful API server talking.

1. Double-check that the server is running and serving good API data at `http://localhost:3008/api/menuItems`.
1. Edit App.tsx. Make the top of it look like this:
```typescript
import { useEffect, useState } from 'react'
import reactLogo from './assets/react.svg'
import viteLogo from '/vite.svg'
import './App.css'

function App() {
  const [count, setCount] = useState(0)
  useEffect(() => {
    fetch('/api/menuItems')
      .then(res => res.json())
      .then(data => console.log(data));
  });

  return (
```
2. Run and test. Look in the console. Did it work? It shouldn't have.

If you don't understand the same origin policy (SOP) built into browsers, read up on it (here)[https://developer.mozilla.org/en-US/docs/Web/Security/Same-origin_policy]. In a nutshell, the SOP will prevent us from making data requests from localhost:3008 (the data server) if our web page was served from localhost:5173 (the vite dev server).

When you eventually deploy your site, you'll build your React app and copy the compiled app to the public folder of your server so they'll both be served from the same origin. But during debugging that's a lot of repetitive and slow work for every little change. We can make our vite dev server proxy our API server by changing the `vite.config.js` file.

1. Make your vite.config.js file look like this:
```typescript
import { defineConfig } from 'vite'
import react from '@vitejs/plugin-react-swc'
export default defineConfig({
  plugins: [react()],
  server: {
    proxy: {
      '/api': {
        target: 'http://localhost:3008/',
        secure: false,
        // changeOrigin: true,
        // rewrite: (path) => path.replace(/^\/api/, ''),
      },
      '/images': {
        target: 'http://localhost:3008/',
        secure: false,
        // changeOrigin: true,
        // rewrite: (path) => path.replace(/^\/api/, ''),
      },
    },
  },
})
```

1. Run and test again. You should see data in the console.