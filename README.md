# Uncontrolled useEffect causing infinite render loop

This repository demonstrates a common React bug where the `useEffect` hook runs on every render, leading to an uncontrolled infinite render loop and performance issues.  The issue arises from the missing dependency array in the `useEffect` hook.

## Bug Description
The provided `MyComponent` uses `useEffect` without a dependency array.  This means the effect runs after every render, creating a cycle where the effect triggers a re-render, which triggers the effect again, and so on.

## Solution
Adding a dependency array to the `useEffect` hook solves the problem. The dependency array should include any values from the component's scope that the effect depends on.  If the effect doesn't depend on any values from the component's scope, an empty array `[]` should be provided.