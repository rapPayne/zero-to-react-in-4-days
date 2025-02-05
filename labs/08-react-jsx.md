# JSX Lab

We're going to use JSX to flesh out our React app but we'll need some TypeScript types for our data first. Then we'll hardcode some data into App.tsx, and finally display that data.

## Create some TypeScript classes
1. Create a folder under `src` called "types". All of the following types will go in this folder.
1. First, create this type to hold the data for a single menuItem that has been added to the cart:
```typescript
export type CartItem = {
  id: number,
  itemId: number,
  name: string,
  category: string,
  price: number,
  imageUrl: string,
  firstName?: string,  // Diner's name
  notes?: string,  // Special instructions
}
```
3. Do a test query from the API service of all menuItems. Examine the properties that each menuItem has.
1. Create a MenuItem TypeScript type. Its properties should reflect the properties from the API service.
1. Do the same for a User type.
1. And once again for an Order type.

## Hardcode some menuItems
1. Edit your Menu.tsx component. Add this to the top:
```typescript
import { MenuItem as MenuItemType } from '../types/MenuItem'
const menuitems: MenuItemType[] = [
    {
      "id": 6,
      "name": "Salmon Sashimi",
      "description": "Premium salmon pieces, expertly carved. Covered with our signature curry-inspired sauce that is slightly sweet and slightly spicy. Indulge in the fresh taste of the ocean. Our Salmon Sashimi features vibrant slices of salmon, perfect for savoring its natural flavor. Served with wasabi, pickled ginger, and soy sauce for a delightful appetizer.",
      "category": "sushi",
      "price": 11.38,
      "imageUrl": "http://localhost:3008/images/food/sushi_1.jpg",
      "available": true
    },
    {
      "id": 7,
      "name": "Sakura Blossom Salmon Sushi Roll",
      "description": "Immerse yourself in a culinary masterpiece with our Sakura Blossom Salmon Sushi Roll. Handcrafted with the utmost precision, this roll features the finest Norwegian salmon, creamy avocado, and delicate sakura radish sprouts, elegantly wrapped in crisp nori seaweed and perfectly seasoned sushi rice. Topped with toasted sesame seeds, it's a symphony of flavors and textures, a celebration of artistry on a plate. Served with a house-made dipping sauce.",
      "category": "sushi",
      "price": 13.66,
      "imageUrl": "http://localhost:3008/images/food/sushi_2.jpg",
      "available": true
    },
    {
      "id": 8,
      "name": "Strawberry Parfait",
      "description": "Indulge in a sweet symphony of flavors and textures with our Strawberry Parfait. Layers of luscious, ripe strawberries, nestled between clouds of velvety vanilla custard and delicate, golden-brown granola clusters. Each spoonful is a harmonious blend of juicy, sun-kissed strawberries, creamy custard, and the satisfying crunch of granola. Topped with a dollop of freshly whipped cream and a garnish of fresh mint leaves, it's a delightful journey of taste and a visual masterpiece in a glass. A heavenly treat that's both elegant and comforting, the Strawberry Parfait is the perfect finale to any meal or a delightful indulgence anytime you crave a taste of pure bliss. Enjoy!",
      "category": "desserts",
      "price": 8.75,
      "imageUrl": "http://localhost:3008/images/food/desserts_1.jpg",
      "available": true
    },
    {
      "id": 9,
      "name": "Decadent Chocolate Cake with Mousse Layers",
      "description": "Indulge in the ultimate chocolate lover's delight with our Decadent Chocolate Cake. Moist, rich chocolate cake layers alternate with silky chocolate mousse, creating a symphony of textures and flavors. A drizzle of vibrant strawberry sauce crowns this masterpiece, adding a delightful touch of fruity sweetness. It's a sensory journey that combines the deep, dark allure of chocolate with the bright, tangy notes of strawberries, making each bite an exquisite experience.",
      "category": "desserts",
      "price": 9.5,
      "imageUrl": "http://localhost:3008/images/food/desserts_2.jpg",
      "available": true
    },
  ];
```

## Use your new menuItems
1. Edit your index.html page. Copy the menu item contents of it and put them in your Menu.jsx file. This should give you three or four (however many) menuItems on your landing page.
1. Run and test. Make sure the structure is okay. Don't worry about the styling yet. 
1. Our goal is to use the menuItems you pasted above instead of the data which is already there.
1. See the first item's description in the `<h2>`? Replace it with `{menuItem[0].name}`.
1. Run and test. Make sure you are displaying the data from the JavaScript object.
1. If that works, do the same for the imageurl, description, and price. 
1. Do the same for all of the menu items you've chosen to display. Copy/pasting is fine. We'll make it dynamic later.