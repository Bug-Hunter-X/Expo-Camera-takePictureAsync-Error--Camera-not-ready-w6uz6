# Expo Camera takePictureAsync Error: Camera not ready

This repository demonstrates a common error encountered when using the Expo Camera API: `takePictureAsync` being called before the camera is ready.

The `bug.js` file shows the problematic code, resulting in the error. The solution is provided in `bugSolution.js`, addressing the asynchronous initialization of the camera.

## Problem

Calling `takePictureAsync` too early leads to the 'Camera is not ready' error. This often occurs within lifecycle methods or immediately within a `useEffect` hook before the camera has completely initialized.

## Solution

The solution involves using the camera's `status` property to track initialization.  The `takePictureAsync` function is only called after the camera is ready (`status === 'ready')`.