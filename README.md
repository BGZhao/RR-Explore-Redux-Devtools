# RR-Explore-Redux-Devtools
assignment 7.7.2
# Activity: Explore Redux DevTools
In this activity, we will add another reducer to our existing Redux store that we established in the code-along presented in Module 7.7.1. Like we saw in Module 6: Redux Fundamentals, we will build a simple to-do list in Redux, but this time we will have the opportunity to explore state with the Redux Devtools!

We won't get too involved with the user experience or visual merits of the application during this code-along.

To get started, open the React application we generated in Lesson 1. It's fine if you don't have the application in a working state. Clone the repository from this link: https://github.com/HackerUSA-CE/RR-Explore-Redux-Devtools/tree/counter

## 1. Planning
First, we should take account of the elements we will need to generate to develop the new features for our application.

We will need to store an array of strings for our state variable. On the Redux end, initial state will be fairly easy to set up (just an empty array to get started). Next, we should think about what actions we want to build into our "slice." What actions should a to-do list have? In the case of this exercise, we'll start with the following features:

Add a to-do item with addTodo
Remove a to-do item with removeTodo
Clear all to-do items with clearTodos
On the React end, we will need to build:

A to-do list component
A form to handle adding a list item
Render the list
A "clear" button
## 2. Build the Slice
Because we have already established our store, we can move directly into building a new slice to support our new reducer!

Generate a new file called todoSlice.js inside your features folder. Inside todoSlice.js, import createSlice from the Redux toolkit and establish initial state.


Click here to copy
Then, following the pattern we used to develop counterSlice.js, build a todoSlice!

Tip: 'addTodo' and 'clearTodos' will likely be easier to write than 'removeTodo'. It might be worthwhile to build those reducers before confronting the more challenging one!
Remember to export your actions to todoSlice.actions and export the default todoSlice.reducer.

## 3. Include the New Reducer
Navigate to store.js and import todoReducer. Then, adapt your store to look like so:

export const store = configureStore({
    reducer: {
        counter: counterReducer,
        todo: todoReducer
    }
})

Click here to copy
At this point, test your application to ensure your store is "plugged in" correctly. Your Redux Devtools should look something like this, with the new store included:


If your Redux Devtools window looks something like this, that's fantastic! Immediately after adding a Reducer to our store, we can see that the store is aware of the new reducer and is ready to hold data. Now it's as simple as building a UI so we can use the features in our reducer!

## 4. Build the UI
Next, build the UI for the application. We only need to generate one new component for this, but feel free to get creative and make as many as you like to separate all concerns. Remember, we're working with global state, so there's no need to worry about how props are passed or managing individual component state!

Use what we learned when adding the form for a custom "counter" payload to develop the form that should handle addTodo.

When you're done, your UI might look something like this:


## 5. Assign Dispatch
Now that the UI is composed, we simply need to attach functions that call the appropriate action via Redux dispatch!

Start by "plugging in" the functionality for addTodo. Then, let's test the behavior. Ensure your application can perform the functionality displayed below:


Notice what Redux Devtools is tracking now! When you add a new to-do item, watch as the action is represented on the left-hand side of the panel. If you are tracking state using the same chart view as the gif, you will see the array expanding in real-time!

Take a moment to explore the Redux Devtools to get a better understanding of what the toolkit is doing and how it might be able to help in future debugging. Take time to discuss this topic with your fellow learners!

## 6. Finish Adding Dispatch
Now that we know Redux is "plugged in" and our dispatch is not throwing errors, continue building the application. Implement the clear functionality so we can clear our list of to-dos and then add an onClick behavior for each item in the to-do list that will remove only the item clicked.

If you get stuck, feel free to check the solution code at this GitHub repository: https://github.com/HackerUSA-CE/RR-Explore-Redux-Devtools/tree/main
