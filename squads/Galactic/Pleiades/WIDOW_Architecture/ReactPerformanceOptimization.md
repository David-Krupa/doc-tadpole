# React Performance Optimization

## Purpose

- Discuss React component performance
- How to determine when performance optimization is necessary
- Present techniques to optimize and improve React performance

## Background

First, there is no hard and fast rule saying all code must be optimized to its highest level of performance. In fact, while creating the "perfectly optimized" component is a laudable goal, extreme optimization requires extreme amounts of time. Component optimization should be balanced against time to develop and user requirements.

## Prerequisites

Read the [React documentation on optimizing performance](https://reactjs.org/docs/optimizing-performance.html).

## Basic Performance Optimizations

Well designed components and proper use is the first step to optimizing components. These steps include:

- Reduce the number of components rendered at any given time. Writing components to the DOM (a process called [reconciliation](https://reactjs.org/docs/reconciliation.html)) is time-intensive. The fewer components that have to be written the faster the app can be.
- Virtualize long lists of components. This is discussed in the [React docs](https://reactjs.org/docs/optimizing-performance.html).
- Not subscribing a component to any more state than is required. This includes state passed as props, obtained from Redux, or state that is local to a component. This is because .
- Providing a proper [non-changing "key" for lists](https://reactjs.org/docs/lists-and-keys.html#keys) of React components. React uses the key prop to help determine if a component is the same instance as in a previous render. This influences React’s decision on if the component requires a re-render.
- Do not render a disabled MUI component when simple text will suffice.

## React Profiler

The React Profiler can be used to help determine if there is a performance problem. It can also help find the source of the problem.

<https://www.youtube.com/watch?v=00RoZflFE34> by Ben Awad discusses using the React Profiler and using React.memo to prevent excessive component re-rendering.

## MUI Specific

**Replace disabled interactive components with text when able**.

Interactive Material UI (MUI) components such as AutoComplete and TextField require more processing and rendering than a standard text label. For example, and AutoComplete component will create a selection list whether it is disabled or not. It is faster to display only the value that should be shown than a disabled AutoComplete, TextField, or other MUI component.

## Resources

- Dan Abramov [Before You Memo](https://overreacted.io/before-you-memo/)
- Kent C Dodds
  - [One Simple Trick to Optimize React Re-renders](https://kentcdodds.com/blog/optimize-react-re-renders)
  - [Fix the slow render before you fix the re-render](https://kentcdodds.com/blog/fix-the-slow-render-before-you-fix-the-re-render)
- Mark Erikson and Eugene Bakin [React/Redux Performance and Optimization](https://github.com/markerikson/react-redux-links/blob/master/react-performance.md)

### Presentations

Excessive component rendering can be a source of React slowdowns. Preventing unnecessary rendering of child components can help solve this problem.

[React Component Optimization](https://docs.google.com/presentation/d/1rd0P-5tBZ9B58o9EkF7Soq584k8fokV1sw-Lat8H7fk/edit?usp=sharing%20)

[React Profiler Introduction](https://docs.google.com/presentation/d/1ysfyY3VymvJRVD4nFVoZ23L21Krmsr8WDcsdSyAHCCI/edit?usp=sharing)

<https://www.youtube.com/watch?v=o-alRbk_zP0> by Ben Awad
