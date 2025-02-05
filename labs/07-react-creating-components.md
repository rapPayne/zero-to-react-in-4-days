# Creating Components Lab

There's no community concensus as to what to call components that take up the entire screen. Some call them "scenes" or "screens". Others call them "pages" but that's misleading since React is a SPA. For this course, let's refer to them as "scenes".

1. Create these scene-level components:

| Component | Comments |
|-----------|----------|
| Menu      | The food menu |
| Register  | User registration form |
| Login     | User login form |
| Orders    | (Plural) List of orders |
| Order     | (Singular) Details of a single food order |
| Cart      | Shopping cart |


For now, these can each just display their name as a big `<h1>`.
1. Create each. Then manually edit App.tsx to add them one at a time so you can see each one appear in App.tsx.

Later on we'll learn how to do routing so that the user can navigate to the components but until then, you'll manually swap out each one to view your work and to debug.

## Adding commonality
In the html pages you created earlier, you had the same navbar on both pages. If you had a footer, they'd have been the same. All features common to all pages should be put in the master component, App.tsx.
1. Create the navbar at the top of App.tsx. Feel free to copy/paste from your html pages. 
1. Create a footer at the bottom of App.txs with a copyright notice.

