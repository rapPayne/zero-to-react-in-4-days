# Events Lab

1. Edit App.tsx. Create a new function called addToCart(). It should receive a single MenuItem. This function should merely console.log() the menu item.
1. Find where you've added the `<Menu />` component and make it look like this:
```typescript
<Menu addToCart={addToCart} />
```
This will pass the addToCart function down into the Menu component as a "prop" (more on this idea later).

1. Now edit Menu.tsx and change the function declaration to look like this:
```typescript
interface Props {  // Add this interface
  addToCart: (menuItem: MenuItemType) => void,
}
export const Menu = ({ addToCart }: Props) => {
```
or
```typescript
interface Props {  // Add this interface
  addToCart: (menuItem: MenuItemType) => void,
}
export function Menu({ addToCart }: Props) {
```
This allows your Menu component to receive the addToCart function from its parent.

1. Now the payoff. Find all of the "Add" buttons on your menuItems. Add a click event to each to `addToCart(menuItem)`. 
1. Run and test. Work with the code until clicking each button console.log()s its proper menuItem to the browser console.

Later on we'll learn how to add a cart to the App component and display the cart's contents in the Cart component. But for now, we're just testing that the event is working properly.