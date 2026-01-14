---
layout: default
title: Snack Stack
---

# Snack Stack

## Table of Contents
- [Snack Stack](#snack-stack)
  - [Table of Contents](#table-of-contents)
  - [Overview](#overview)
    - [Problem](#problem)
    - [Approach](#approach)
    - [Use Case Ideas](#use-case-ideas)
    - [Beyond the Basics](#beyond-the-basics)
  - [Deployment](#deployment)
  - [Continuous Integration](#continuous-integration)
  - [Team Contract](#team-contract)
  - [User Guide](#user-guide)
    - [Sign in page](#sign-in-page)
    - [Dashboard](#dashboard)
    - [View your pantry](#view-your-pantry)
    - [Add and Edit your pantry](#add-and-edit-your-pantry)
    - [Create Shopping Lists](#create-shopping-lists)
    - [Find Recipes](#find-recipes)
  - [Developer Guide](#developer-guide)
    - [Installation](#installation)
    - [Application Design](#application-design)
  - [Milestones](#milestones)
    - [Milestone 1 Progress](#milestone-1-progress)
    - [Milestone 2 Progress](#milestone-2-progress)
    - [Milestone 3 Progress](#milestone-3-progress)
    - [Milestone 4 Progress](#milestone-4-progress)
    - [Milestone 5 Progress](#milestone-5-progress)
    - [Milestone 6 Progress](#milestone-6-progress)
    - [Milestone 7 Progress](#milestone-7-progress)
  - [Development Team](#development-team)

<!--
comment out add in later as we progress through project
* [User Guide](#user-guide)
* [Community Feedback](#community-feedback)
* [Developer Guide](#developer-guide)
* [Development History](#development-history)
* [Continuous Integration](#continuous-integration)
* [Walkthrough videos](#walkthrough-videos)
* [Example enhancements](#example-enhancements)
* [Team](#team)
-->

---

## Overview

### Problem
_What's the point of a pantry app?_
- People often forget what they have in their pantry, fridge, or spice rack
- Expired food leads to waste and wasted money 
- Grocery shopping is inefficient without knowing what's already at home

### Approach
- Create a digital inventory system for pantry, fridge, freezer, and spices
- Allow users to easily add, remove, and update items
- Automatically generate shopping lists when items are low or missing
- Simple and clean interface so it's quick to use every day

### Use Case Ideas
- Before going to the store, check what items are low or expired
- While cooking, search the app to see if you have a specific ingredient
- Share the pantry list with family or roomates so everyone is synced
- Use expiration reminders to finish food before it spoils

### Beyond the Basics
- Barcode scanner for quick item entry
- Recipe suggestions based on available ingredients 
- Reports that show spending trends and reduce food waste
- Possible integration with smart home assistance like Alexa or Google Assistant

## Deployment
Snack Stack is deployed through Vercel, taking advantage of its seamless integration with GitHub and strong support for Next.js applications. The repository’s main branch is connected directly to Vercel, which means that any changes merged into main automatically trigger a new production build. This continuous deployment pipeline ensures that the application is always up to date with the latest code.

During each deployment, Vercel installs the project dependencies, generates the Prisma client, applies any pending database migrations, and then builds the Next.js application for production. Once the build process completes, Vercel publishes the new version of the site, replacing the old one with zero downtime. This automated flow allows the team to focus on development while keeping deployment consistent and reliable.

The live site can be accessed here: [Snack Stack](https://pantry-pal-gamma.vercel.app)

---

## Continuous Integration
[![ci-badge](https://github.com/snack-stack-uhm/snack-stack/workflows/snack-stack-uhm/badge.svg)](https://github.com/snack-stack-uhm/snack-stack/actions/workflows/ci.yml)


---

## Team Contract
[Link to Team Contract](https://docs.google.com/document/d/1QSisK4_q7C7179ZbYHU2LISKLjH-Tgl0kmKb8poIX38/edit?usp=sharing)

<!-- PDF.js settings -->
<div id="pdf-viewer" style="
    max-width:900px;
    margin:20px auto;
    border:1px solid #ccc;
    border-radius:8px;
    box-shadow:0 4px 10px rgba(0,0,0,0.1);
    overflow-y:auto;
    height:800px;
    background-color:white;
    padding:10px;
"></div>

<script src="https://cdnjs.cloudflare.com/ajax/libs/pdf.js/3.11.174/pdf.min.js"></script>
<script>
const url = '/assets/team-contract.pdf';
const container = document.getElementById('pdf-viewer');

pdfjsLib.getDocument(url).promise.then(pdf => {
  for (let i = 1; i <= pdf.numPages; i++) {
    pdf.getPage(i).then(page => {
      const scale = 1.5;
      const viewport = page.getViewport({ scale });
      const canvas = document.createElement('canvas');
      const ctx = canvas.getContext('2d');
      canvas.height = viewport.height;
      canvas.width = viewport.width;
      canvas.style.display = 'block';
      canvas.style.margin = '10px auto';
      container.appendChild(canvas);
      page.render({ canvasContext: ctx, viewport: viewport });
    });
  }
});
</script>

---

## User Guide
An intro to using Snack Stack  

### Sign in page
Sign up for Snack Stack and verify your email to sign in
![Pantry App Sign Up_Screenshot](assets/m4/m4_signup.png)
![Pantry App Sign In_Screenshot](assets/m4/m4_signin.png)

### Dashboard
Users have easy access to all pages through Pantry Pal's dashboard
![Pantry App Dashboard_Screenshot](assets/m5/m5_dashboard.png)

### View your pantry
Snack Stack allows you to easily keep track of what ingredients you have in your household, where they are, and how much of them you have left
![Pantry App InventoryList_Screenshot](assets/m5/m5_pantry_table.png)
![Pantry App InventoryCards_Screenshot](assets/m5/m5_pantry_cards.png)

### Add and Edit your pantry
Keep track of your spices and food by adding them to your pantry  
![Pantry App Add Item_Screenshot](assets/m5/m5_addProduceModal.png)
![Pantry App Edit Item_Screenshot](assets/m5/m5_editProduceModal.png)
![Pantry App Delete Item_Screenshot](assets/m4/m4_deleteitem.png)

### Create Shopping Lists
Easily create and manage your shopping list based on what’s running low in your pantry. Check off items as you shop to keep your inventory up to date.
![Pantry App CreateShoppingList_ScreenShot](assets/m6/m6_create_shoppinglist.png)
![Pantry App ShoppingList_Screenshot](assets/m4/m4_shoppinglists.png)
![Pantry App ViewShoppingList_Screenshot](assets/m4/m4_shoppinglist_view.png)

### Find Recipes
Discover recipes you can make with the ingredients you already have. Snack Stack helps you reduce waste and find meal ideas tailored to your pantry.
![Pantry App Recipes Screenshot](assets/m5/m5_recipes.png)
![Pantry App Recipes I Can Make](assets/m5/m5_recipes_make.png)
![Pantry App Recipes Instructions](assets/m5/m5_recipes_instructions.png)

---

## Developer Guide
This section provides information of interest to developers wishing to use this code base as a basis for their own development tasks.

### Installation
First, install [Node.js](https://nodejs.org/en/download/)

Second, visit the [Snack Stack application github page](https://github.com/snack-stack-uhm/snack-stack), and click the “Use this template” button to create your own repository initialized with a copy of this application. Alternatively, you can download the sources as a zip file or make a fork of the repo. However you do it, download a copy of the repo to your local computer.

Third, cd into the pantry-pal directory and install libraries with:
```
$ npm install
```

Fourth, run the system with:
```
$ npm run dev
```

If all goes well, the application will appear at [http://localhost:3000](http://localhost:3000).

### Application Design
Pantry Pal is based upon the ICS Software Engineering [Next.js Application Template](https://github.com/ics-software-engineering/nextjs-application-template).

---

## Milestones
  * [Milestone 1 Progress](#milestone-1-progress)
  * [Milestone 2 Progress](#milestone-2-progress)
  * [Milestone 3 Progress](#milestone-3-progress)
  * [Milestone 4 Progress](#milestone-4-progress)
  * [Milestone 5 Progress](#milestone-5-progress)
  * [Milestone 6 Progress](#milestone-6-progress)
  * [Milestone 7 Progress](#milestone-7-progress)

### Milestone 1 Progress
[Milestone 1 Project Board](https://github.com/orgs/snack-stack-uhm/projects/2)

![Pantry App Screenshot](assets/m1/pantry_pals_homepage.png)
![Pantry App Inventory_Screenshot](assets/m1/inventory.png)
![Pantry App ShoppingList_Screenshot](assets/m3/m3_shopping_list.png)

### Milestone 2 Progress
[Milestone 2 Project Board](https://github.com/orgs/snack-stack-uhm/projects/7)

![Snack Stack Landing Page](assets/m2/m2_pantry_pals_landing.png)
![Snack Stack Sign In Page](assets/m2/m2_signin_page.png)
![Snack Stack Sign Up Page](assets/m2/m2_signup_page.png)
![Snack Stack Pantry Page](assets/m2/m2_view_pantry_page.png)
![Snack Stack About Us Page 1](assets/m2/m2_about_us_page1.png)
![Snack Stack About Us Page 2](assets/m2/m2_about_us_page2.png)
![Snack Stack Recipe Page](assets/m2/M2_recipePage.png)

### Milestone 3 Progress
[Milestone 3 Project Board](https://github.com/orgs/snack-stack-uhm/projects/10)

![M3 Landing Page](assets/m3/m3_landing.png)
![M3 Pantry Page Table](assets/m3/m3_pantry1.png)
![M3 Pantry Page Cards](assets/m3/m3_pantry2.png)
![M3 Add Item Modal](assets/m3/m3_add.png)
![M3 Edit Item Modal](assets/m3/m3_edit.png)
![M3 Shopping List Page](assets/m3/m3_shopping1.png)
![M3 Shopping List Modal](assets/m3/m3_shopping2.png)
![M3 Recipes Page](assets/m3/m3_recipes.png)
![Mockup idea](assets/m1/Dashboard_Mock_Up.png)

### Milestone 4 Progress
[Milestone 4 Project Board](https://github.com/orgs/snack-stack-uhm/projects/11)

![M4 Landing Page](assets/m4/m4_landing.png)
![M4 Dashboard Page](assets/m4/m4_dashboard.png)
![M4 Dashboard Mockup](assets/m4/m4_dashboard_mockup.png)
![M4 Pantry Page Table](assets/m4/m4_pantry_list.png)
![M4 Pantry Page Cards](assets/m4/m4_pantry_cards.png)
![M4 Add Item Modal](assets/m4/m4_additem.png)
![M4 Edit Item Modal](assets/m4/m4_edititem.png)
![M4 Delete Item Modal](assets/m4/m4_deleteitem.png)
![M4 Shopping List Page](assets/m4/m4_shoppinglists.png)
![M4 View Shopping List Modal](assets/m4/m4_shoppinglist_view.png)
![M4 Delete Shopping List Modal](assets/m4/m4_shoppinglist_delete.png)
![M4 Recipes Page 1](assets/m4/m4_recipes1.png)
![M4 Recipes Page 2](assets/m4/m4_recipes2.png)

### Milestone 5 Progress
[Milestone 5 Project Board](https://github.com/orgs/snack-stack-uhm/projects/12)

![M5 Dashboard Page](assets/m5/m5_dashboard.png)
![M5 Pantry Page Table](assets/m5/m5_pantry_table.png)
![M5 Pantry Page Cards](assets/m5/m5_pantry_cards.png)
![M5 Add Produce Modal](assets/m5/m5_addProduceModal.png)
![M5 Edit Produce Modal](assets/m5/m5_editProduceModal.png)
![M5 Add Location Modal](assets/m5/m5_addLocationModal.png)
![M5 Delete Location Modal](assets/m5/m5_deleteLocationModal.png)
![M5 Recipes Page](assets/m5/m5_recipes.png)
![M5 Recipes I Can Make](assets/m5/m5_recipes_make.png)
![M5 Add Recipes Modal](assets/m5/m5_addRecipeModal.png)
![M5 Recipe Instructions](assets/m5/m5_recipes_instructions.png)
![M5 Add To Shopping List from Main View](assets/m5/m5_addtoshoppinglist.png)
![M5 Add To Shopping List from List View](assets/m5/m5_addtoshoppinglist2.png)

### Milestone 6 Progress
[Milestone 6 Project Board](https://github.com/orgs/snack-stack-uhm/projects/13)

![M6 Pantry Page Table](assets/m6/m6_pantry_table.png)
![M6 Pantry Page Cards](assets/m6/m6_pantry_cards.png)
![M6 Add Produce Modal](assets/m6/m6_add_item_modal.png)
![M6 Recipes Page](assets/m6/m6_recipes.png)
![M6 Recipes I Can Make](assets/m6/m6_make_recipes.png)
![M6 Edit Recipes](assets/m6/m6_edit_recipes.png)
![M6 Edit Recipes Modal](assets/m6/m6_edit_recipe_modal.png)
![M6 Recipe Instructions 1](assets/m6/m6_recipe_instructions1.png)
![M6 Recipe Instructions 2](assets/m6/m6_recipe_instructions2.png)
![M6 View Shopping List](assets/m6/m6_view_shopping_list.png)
![M6 Create New Shopping List](assets/m6/m6_create_shoppinglist.png)

### Milestone 7 Progress
[Milestone 7 Project Board](https://github.com/orgs/snack-stack-uhm/projects/14)

![M7 Landing Page](assets/m7/m7_landing.png)
![M7 Add Produce Modal](assets/m7/m7_addItemModal.png)
![M7 Recipes Page](assets/m7/m7_recipesPage.png)
![M7 Add Recipes Modal](assets/m7/m7_addRecipeModal.png)
![M7 Edit Recipes Modal](assets/m7/m7_editRecipeModal.png)
![M7 Shopping List Page](assets/m7/m7_shoppingListPage.png)
![M7 Shopping List Modal](assets/m7/m7_shoppingListModal.png)

---

## Development Team
<img src="assets/m4/githubicon.png" width="15" height="15">[Justin Smith](https://github.com/justnsmith)  
<img src="assets/m4/githubicon.png" width="15" height="15">[James Ivan Cartagena](https://github.com/jicaartagena)  
<img src="assets/m4/githubicon.png" width="15" height="15">[Jason Nguyen](https://github.com/jknguyen2003)  
<img src="assets/m4/githubicon.png" width="15" height="15">[Haley Teramoto](https://github.com/haleyteramoto)  
<img src="assets/m4/githubicon.png" width="15" height="15">[Pelita Felicitas](https://github.com/pelitaf)  
<img src="assets/m4/githubicon.png" width="15" height="15">[Jarell Ballesteros](https://github.com/jarellb)  
<img src="assets/m4/githubicon.png" width="15" height="15">[Cohen Ruport](https://github.com/cohenruport)  
<img src="assets/m4/githubicon.png" width="15" height="15">[Amy Shin](https://github.com/tlsdbfla00)  
<img src="assets/m4/githubicon.png" width="15" height="15">[Jared Seto](https://github.com/jseto808)  

## Team Contract
[Link to Team Contract](https://docs.google.com/document/d/1agUDEXML0mpS8pNNdEmx55DyYQOOBeRJWTL9lC9QDy4/edit?usp=sharing)
