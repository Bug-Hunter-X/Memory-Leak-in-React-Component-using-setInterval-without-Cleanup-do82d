# React UseEffect setInterval Cleanup
This repository demonstrates a common error in React components that use `setInterval` within the `useEffect` hook without providing a cleanup function. This leads to memory leaks as the interval continues to run even after the component unmounts.

## Bug Description
The `MyComponent` component uses `setInterval` to update a counter every second. However, it's missing a return statement in the `useEffect` callback to clear the interval before the component unmounts.

## Solution
The solution involves returning a cleanup function from the `useEffect` callback which calls `clearInterval` to stop the interval. This prevents memory leaks.