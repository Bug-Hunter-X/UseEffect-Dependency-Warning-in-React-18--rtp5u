# React 18 useEffect Dependency Warning

This repository demonstrates a common warning encountered when upgrading to React 18 (and later versions) related to the `useEffect` hook's dependencies array.  Incorrectly omitting necessary dependencies can lead to stale closures and unexpected behavior.  The example showcases the problem and provides a corrected solution. 

## Problem

The `bug.js` file contains a `MyComponent` that demonstrates the issue. The `useEffect` hook logs the `count` value, but the `count` variable is not included in the dependency array (`[count]`).  In React 18+, this will generate a warning because the effect may not re-run when `count` changes causing unexpected behavior. 

## Solution

The `bugSolution.js` file provides the corrected component.  By including `count` in the dependency array, we ensure that the effect runs whenever `count` updates, resolving the warning and ensuring correct functionality.