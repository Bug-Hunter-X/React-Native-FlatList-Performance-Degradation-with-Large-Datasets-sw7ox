# React Native FlatList Performance Issue

This repository demonstrates a common performance problem in React Native's FlatList component when dealing with large datasets and frequent data updates. The original code exhibits slow scrolling, lag, and potential crashes. The solution implements optimized techniques to address these issues.

## Problem

The `FlatList` component, while efficient for many use cases, can struggle with performance when faced with:

* **Large datasets:** Thousands of items can lead to significant rendering overhead.
* **Frequent data updates:** Constant changes to the dataset trigger unnecessary re-renders.

## Solution

The solution employs the following strategies:

* **`keyExtractor`:**  A unique key is provided for each item to prevent unnecessary re-renders.
* **`ItemSeparatorComponent`:** Use a separator component instead of relying on styling for separation to reduce render operations. 
* **`removeClippedSubviews`:**  This prop is set to `true` which improves performance by removing offscreen components from the render tree.
* **`initialNumToRender`:**  Optimize initial rendering by specifying the number of items to initially render. 
* **Data chunking or windowing:** Consider strategies to limit the number of items rendered at any given time, loading additional data as needed.