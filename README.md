# Expo useSharedValue Asynchronous Update Issue

This repository demonstrates a common issue encountered when using Expo's `useSharedValue` hook with asynchronous operations. The problem is that updates to the shared value aren't reflected in the UI immediately, leading to stale state.

## Bug Description
The `useSharedValue` hook, when updated asynchronously (e.g., within a `setTimeout`, `fetch` call, or other asynchronous operation), doesn't trigger an immediate re-render. This results in the UI not reflecting the most current value of the shared value.  This can lead to unexpected behavior and inconsistent UI state.

## Solution
The solution involves using `useAnimatedValue` and `withTiming` or `withSpring` from `react-native-reanimated` to smoothly animate transitions. These methods provide more control over state updates and ensure that UI changes are properly synchronized with the shared value.

## Reproduction Steps
1. Clone this repository.
2. Run `npm install`.
3. Run `expo start`. Observe the inconsistent state.
4. Examine the solution in `AsyncSharedValueSolution.js` to see the fix.