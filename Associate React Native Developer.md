# **Associate React Native Developer – Assessment Task**

## **Objective**

Build a small **React Native mobile app** (Android or iOS) with 2–3 screens that demonstrate:

* UI implementation from a given layout
* API integration
* Component structuring
* Navigation
* State management fundamentals
* Code quality and design consistency

---

**Create a simple "Product Listing App"** with:

1. **Product List Screen**
2. **Product Details Screen**
3. **Favourite a Product** (local state)

You can use **any public API** or **mock JSON** for product data.

---

# **Requirements**

## **1. Product List Screen**

Display a list of products using a simple card layout.

Each card should include:

* Product image
* Product title
* Product price
* "View Details" button

Features:

* Fetch data from a **public API** (example below) or from a `products.json` file.
* Show a loading state.
* Show an error message if network/API fails.
* Add basic pull-to-refresh (if possible).

Example public API (choose any):

```
https://fakestoreapi.com/products
```

---

## **2. Product Details Screen**

When a user taps a product, navigate to a details screen that shows:

* Large product image
* Title
* Price
* Description
* "Add to Favorites" button (toggle)

Should include:

* Back button
* Scrollable layout
* Clean styling with proper spacing and typography

---

## **3. Favourites (Local State)**

Implement a simple **favorites feature**:

* Maintain a local list of favorite product IDs
* Toggle using a heart icon or button
* Show "*Added to Favourites*" visual feedback
* Persist favorites using **AsyncStorage** (optional bonus)

---

## **4. Navigation**

Use **React Navigation** with:

* Stack Navigator for:

  * Product List
  * Product Details

---

## **5. Code Quality Guidelines**

* Use functional components + React Hooks
* Use `FlatList` for rendering lists
* Use `StyleSheet` or styled-components (candidate choice)
* Organize files meaningfully:

  * `screens/`
  * `components/`
  * `services/`
  * `assets/`
* Avoid inline styles where possible
* Maintain consistent naming and structure

---

# **Bonus (Optional, Not Required but Nice to Have)**

* Convert code to **TypeScript**
* Add a **search bar** on the list screen
* Add a **favorites filter** button
* Add **basic animations** (fade-in product card)
* Add tests using Jest or React Native Testing Library
* Store favorites using AsyncStorage
* Improve UI with your own layout enhancements

---

# **Expected Submission**

The candidate must share:

### 1. **GitHub Repository Link**

Containing:

* React Native project
* Components
* Screens
* API service
* README.md

### 2. **README File Should Include**

* Setup instructions
* How to install dependencies
* How to run the project
* Brief explanation of your approach
* Assumptions or improvements you would make
