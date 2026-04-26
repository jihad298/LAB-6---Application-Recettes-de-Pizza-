# LAB-6---Application-Recettes-de-Pizza-
# 🍕 Pizza Recipes App (Android Java)

## Overview

Android application demonstrating structured architecture, custom ListView rendering, activity navigation, and basic in-memory data persistence using a service layer.

The app simulates a pizza catalog with detailed recipe views and animated UI transitions.

---

## Key Features

* Splash screen with animations and timed navigation
* List-based catalog using `ListView` + custom adapter
* Detailed view screen for selected items
* Data transfer between activities using `Intent`
* In-memory data management (no database)
* Smooth UI animations for transitions and scrolling

---

## Architecture Overview

### Design Patterns

* **Singleton** → centralized service instance (`ProduitService`)
* **DAO pattern** → abstract CRUD interface (`KitchenVault<T>`)
* **ViewHolder pattern** → optimized `ListView` rendering (`PizzaAdapter`)
* **Generic interface** → reusable data contract

---

## Project Structure

```
classes/
  → Produit (data model)

dao/
  → KitchenVault<T> (CRUD interface)

service/
  → ProduitService (Singleton, in-memory storage)

adapter/
  → PizzaAdapter (ListView binding + ViewHolder)

ui/
  → SplashActivity
  → ListPizzaActivity
  → PizzaDetailActivity
```

---

## Data Model

Each pizza contains:

* ID (unique identifier)
* Name
* Price
* Image resource
* Preparation time
* Ingredients
* Description
* Cooking steps

---

## Data Layer

### KitchenVault<T>

Defines CRUD operations:

* Create
* Read
* Update
* Delete
* List all entries

### ProduitService

* Implements `KitchenVault<Produit>`
* Uses `ArrayList` as storage
* Singleton pattern ensures single shared dataset
* Preloaded with sample recipes

---

## UI Layer

### Splash Screen

* Animated logo entrance
* Sequential UI transitions
* Auto navigation after delay

---

### Pizza List Screen

* Displays catalog using `ListView`
* Each row shows:

  * Image
  * Name
  * Price
  * Preparation time
* Click item → opens detail screen
* Passes selected ID via Intent

---

### Detail Screen

* Retrieves pizza using service layer
* Displays full recipe information
* Handles invalid/missing data safely
* Entry animation applied to content

---

## UI Styling

* Primary theme: deep red palette
* Card-based layout for list items
* Price highlight badges
* Light text contrast for readability

---

## Animations

* Splash logo: scale + rotate + fade
* List items: fade + slide up
* Screen transitions: fade effects
* Bounce effect on splash elements

---

## Sample Data

The app includes 10 predefined pizza recipes with:

* Name
* Price range (1€–8€)
* Preparation time (20–50 min)

---

## Tech Stack

* Java
* Android SDK (API 24+)
* ListView (legacy UI component)
* Custom Adapter pattern
* Intent-based navigation

---

## How to Run

1. Open project in Android Studio
2. Add required images to `res/mipmap` (`pizza1` → `pizza10`)
3. Sync Gradle
4. Run on emulator or physical device

---

## Engineering Summary

This project demonstrates:

* Separation of concerns (UI / Service / Data)
* Basic MVC-like structure in Android
* Efficient list rendering using ViewHolder
* Activity communication via Intent
* Lightweight in-memory persistence model

---
