---
layout: post
title:      "Differences between React State and Redux State"
date:       2018-12-14 00:53:15 -0500
permalink:  all_you_need_to_know_about_-_react_redux_state
---


**What is difference between React State and Redux Store State ?**

Let us understand, 

**What is React state?**

React state it is a Javascript Object

React state is stored and managed locally inside a component 

When state is changed, the component re-renders

Who schedules updates to our component state changes ? 

** it is the setState() method**

You can either pass an object or function to a setState() method

Another point to remember is setState() is asynchronous inside event handlers.

For example , even if parent and child calls setState() during click event, Child is not re-rendered twice


When the state needs to be shared with other components, it is passed down through props.

Usually, the top most component in your application needing access shall hold that value in its state.
		 
		 

**What is Redux State?**

When using Redux in our application, state is stored globally in the store.

Any component that needs access to the value may subscribe to the store 
and gain access to that value. (usually this is *container component*, using *connect* method)

There are two ways to initialise state into Redux store

* createStore method comes with optional argument preloadedState 

* Reducers can also specify initial value. 

   For example, 
	 
	 `function myReducer(state = someDefaultValue, action)`


 
* With Combine Reducers

 Those reducers whose state is specified in preloadedState will receive that state.
 
 [Redux docs provide more details ....](https://redux.js.org/recipes/structuring-reducers/initializing-state)

**How to organise your Redux state**

It is recommended to put plain serializable objects, arrays, and primitives into your store.

If you want to organize nested or duplicate data in state, it should generally be stored in normalized fashion.

For example data with IDs, nesting, or relationships


**When and Where to store state?**

Assuming that your application does use Redux, 
you need to determine what parts of the state are stored in the Redux store, 
and what parts are stored in React component state.

If answer to any of these basic questions is "Yes" then , you should store your data into Redux

Do other parts of your application care about this state?

Do you need to be able to create further derived state based on this original state?

Is the same state being used to drive multiple components?

and there are more questions


***Any data which is changing rapidly in your application, ***

For example, 

user typing characters in textfield in a form, or filter a list of items, or show or hide checkbox items in to-do list 

I would like to store in local React State

***Any data that user navigates through application, ***

For example, 

this could be data loaded from your API 
or after submitting a form data or if you have un related components needing the same state, 

I would like to store state into Redux Store. 

You can also use Redux store, when you want to track changes in state, 
like implementing undo - redo or replay events ... 


In conclusion, 
Their could be many considerations depending on your application and where to store state in React/Redux applications.

















