# React Router Dom: Unhandled routes causing unexpected behavior

This repository demonstrates a common issue in React Router Dom v6 where missing routes for paths not explicitly defined can lead to unexpected behavior or errors.  The bug is present in `bug.js` and a solution is provided in `bugSolution.js`.

## Bug Description

The application uses `react-router-dom` to handle navigation. However, if a user tries to navigate to a route that's not explicitly defined (e.g., typing in an incorrect URL), the application might display an error or unexpected behavior. This is because there is no catch-all route to handle these cases. The default behavior is to render nothing, which might appear as a broken application to users.

## Solution

The solution involves adding a `Route` with `path="*"` to act as a catch-all route.  This route will render a component (in this case, `NotFound`) for any path not matched by other routes, gracefully handling invalid routes.  See `bugSolution.js` for the fix.  The `NotFound` component can display a 404 error or any appropriate message to the user.