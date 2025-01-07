# Stale Closure in useEffect with setInterval
This example demonstrates a common issue when using `setInterval` within React's `useEffect` hook.  The problem arises from how JavaScript closures work.  The `count` variable used inside `setInterval` is captured at the time the `useEffect` is initially called, resulting in the counter not updating correctly.

## How to reproduce
1. Clone this repository.
2. Run `npm install` to install dependencies.
3. Run `npm start` to start the development server.
4. Observe that the counter increments only once, then stops updating.

## Solution
The solution involves using the functional update form of `setCount` to ensure that the counter always uses the latest state value.