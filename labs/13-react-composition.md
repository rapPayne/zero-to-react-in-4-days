# Composition Lab

In this lab we're going to pass data and functions as props from one component to a child.

## From App to the Cart

1. Edit App.tsx. Pass the `cart`, `removeFromCart`, and `changeCartItem` as props to the `Cart` component. This will cause the linter to complain that these props are not defined. That's okay, we'll fix that in the next step.
1. Edit Cart.tsx. Accept the `cart`, `removeFromCart`, and `changeCartItem` props. Hint: You'll need to adjust the TypeScript interface for the props.
1. Iterate the cart items in the JSX. Replace any hardcoded cart items you may have put there for placeholders.
1. Wire up the "remove" button to call `removeFromCart`.
1. Wire up the "firstName" input and "notes" textarea to call `changeCartItem` when they change.
1. Run and test. Verify that you can remove cartItems, and change the first name and notes of items in the cart.

