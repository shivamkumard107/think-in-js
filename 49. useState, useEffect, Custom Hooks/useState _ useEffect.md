Here's an example that demonstrates the usage of both useState and useEffect hooks in a functional component:

```jsx
import React, { useState, useEffect } from 'react';

const ExampleComponent = () => {
  // useState hook to manage a counter
  const [counter, setCounter] = useState(0);

  // useEffect hook to perform side effects
  useEffect(() => {
    // This effect will run after every render of the component
    console.log('Effect triggered');

    // Cleanup function for when the component unmounts or before the next effect runs
    return () => {
      console.log('Effect cleanup');
    };
  });

  // Event handler to increment the counter
  const incrementCounter = () => {
    setCounter(counter + 1);
  };

  return (
    <div>
      <p>Counter: {counter}</p>
      <button onClick={incrementCounter}>Increment</button>
    </div>
  );
};

export default ExampleComponent;
```

In this example, the component uses the useState hook to create a state variable called `counter` and a corresponding function `setCounter` to update its value. The initial value of the `counter` is set to 0.

The useEffect hook is used to **perform side effects**. In this case, it logs a message to the console after every render of the component. It also **returns a cleanup function** that will be executed before the next effect runs or when the component unmounts.

The component renders the current value of `counter` and a button. Clicking the button triggers the `incrementCounter` function, which updates the state by incrementing the counter.

When you run this component, you will see the counter value and a button. Every time you click the button, the counter will increment, and you'll see the effect message logged in the console. When the component unmounts or before the next effect runs (e.g., when the counter changes), the cleanup function will be executed, and the cleanup message will be logged in the console.