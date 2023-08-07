A Javascript library to create user interface. 

- Used to create Single Page Applications(SPAs)
- Component Architecture
- Reconcilation algorithm 
	- Virtual DOM tree differing process with DOM tree
	- Optimised updation of DOM
- Decreased network calls. Works well in a low network situation
- Improves overall user experience

```bash
npx create-react-app my-app
```

```js
const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(
  <React.StrictMode> 
    <App />
  </React.StrictMode>
);
```

> React.StrictMode on any change in state renders the **interface twice**. Only for debugging purposes

