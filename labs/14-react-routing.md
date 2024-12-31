# React Routing Lab

Up to now you've been manually swapping out components. It's time to integrate the components into a whole and implement routing so that the user can navigate seamlessly.

## The routing table

1. Edit App.tsx. You've been hardcoding the other components to get them to appear by putting their JSX tags somewhere below the nav menu and above the footer. 
1. In that location, add a bunch of routes. You'll need routes for the Menu, Login, Register, Cart, and Orders. Hint: Don't forget that you'll be using `<Route>`, `<Routes>`, and `<BrowserRouter>`.
1. Run and test. It should work great at first glance.

## Using efficient links

Your navigation is very inefficient. Each click of link sends a whole new request to the server. Let's fix that.
1. Find every place there is a `<a>` tag. Replace it with a `<Link>` tag.

## Routing parameters

Navigate to the "/orders" route. It should show a list of past orders. When you click on one, we'd like the user to navigate to "/orders/12345" where the 12345 is the order ID of the order clicked on. The user should see the details of order 12345.

1. Edit Orders.tsx. Find where you're iterating the orders. Make the order clickable by surrounding it with a `<Link>` whose `to` property should be "/orders/{order.id}"
1. Make sure that clicking on it will route the user to the "Order" (not "Orders" plural) route. Look at the url in the browser. Does it contain the route parameter as expected?
1. Now let's use that route parameter. In App.tsx change the route table entry for "/order" to include the route parameter.
1. Edit Orders.tsx again. You're currently hardcoding the orderId. Instead, import and call useParams so that you're reading the orderId from the browser address bar. Console.log() it to prove that you're reading it correctly.

Now that you've got the orderId, you should be using it to make an API request from the API server for that order and displaying it. The details should be different for every different orderId.
