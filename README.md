# Firebase Asynchronous Data Access Error

This repository demonstrates a common error encountered when using the Firebase SDK to access data from Firestore. The error occurs when attempting to access document snapshot properties before the asynchronous operation that fetches the data has completed.

## Problem

The provided JavaScript code (`bug.js`) demonstrates accessing a document snapshot's properties directly within a `.then()` callback.  However, since the data retrieval is asynchronous, the snapshot's properties might not be populated at the moment of access, resulting in an error.

## Solution

The solution (`bugSolution.js`) addresses this by implementing a check to ensure the snapshot contains data before accessing its properties.  This prevents errors and handles cases where the document might not exist or be empty.

## How to reproduce

1.  Clone this repository.
2.  Install the Firebase SDK: `npm install firebase`
3.  Set up your Firebase project and configure the `firebase.initializeApp()` function in `bug.js` and `bugSolution.js` with your project credentials.
4.  Ensure a Firestore document exists at the specified path.
5.  Run `node bug.js` to observe the error.
6.  Run `node bugSolution.js` to see the corrected implementation. 
