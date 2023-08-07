## Types of storage (Client Side Storage Utility)

1.  localStorage
    1.  getItem(key)
    2.  setItem(key, value)
    3.  clear()
    4.  removeItem(key)
2.  session storage
3.  cookies

### JSON

1.  JSON.stringify(arr) returns stringified array
2.  JSON.parse(stringArr) parse the stringified array to original JS array

## Event Lifecycle

1.  Capturing Phase
2.  Target Phase
3.  Bubbling Phase

addEventListener(event, eventHandler, useCapture); If useCapture is true, event Handlers runs in capture phase else it runs in bubbling phase.

![[Pasted image 20230226180007.png]]

capturing Phase (true) & bubbling Phase(false)

Only execute that event listener whose eventHandler contain event.stopPropagation()where it will stop further bubbling propagation. If useCapture is true for some listeners, it can still run before the listener in which we want to stop propagation.

## Event Throttling and Debouncing