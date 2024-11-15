
---

# Contact Management Application

This is a simple React-based contact management application that allows users to:

- View a list of contacts.
- Search for contacts by name or phone number.
- Add, edit, and delete contacts.
- View contact details in a modal.

## Table of Contents

- [Project Overview](#project-overview)
- [Tech Stack](#tech-stack)
- [File Structure](#file-structure)
- [Installation](#installation)
- [Usage](#usage)
- [Components Explanation](#components-explanation)

## Project Overview

This project is a contact management app built using React. The app fetches sample contact data from an external URL and provides functionality to perform CRUD (Create, Read, Update, Delete) operations. Contacts can be searched, viewed, edited, or deleted, all managed through modals and state.

## Tech Stack

- **React.js** – For building the user interface.
- **CSS** – For styling.
- **React Hooks** – `useState`, `useEffect` for state management and side effects.

## File Structure

The file structure of the project is as follows:

```
src/
├── components/
│   ├── ContactCard.js
│   ├── ContactList.js
│   ├── Modal.js
│   ├── SearchBar.js
├── App.js
├── App.css
```

## Installation

1. Clone the repository:

   ```bash
   git clone <repository-url>
   ```

2. Navigate into the project folder:

   ```bash
   cd <project-folder>
   ```

3. Install dependencies:

   ```bash
   npm install
   ```

4. Run the app:

   ```bash
   npm start
   ```

The app will run at `http://localhost:3000`.

## Usage

- You can view contacts, add new contacts, edit existing ones, or delete them.
- Use the search bar at the top to filter contacts by name or phone number.
- Modals are used for adding and editing contact details, and contact details can be viewed without editing by clicking the "👁️" button.

---

## Components Explanation

### 1. `App.js`

This is the main component that manages the entire app's state and functionality. It imports other components such as `ContactList` and `Modal`.

#### Key Features:
- **State Variables**:
  - `contacts`: Stores the list of contacts.
  - `isModalOpen`: Controls the visibility of the modal.
  - `modalData`: Stores the data of the currently opened contact for editing or viewing.
  - `viewContact`: Holds the contact data when a user clicks to view details.
  - `searchTerm`: Stores the search term to filter contacts.
  
- **useEffect Hook**:
  - Fetches contacts data from an external JSON file when the component mounts.
  
- **Helper Functions**:
  - `openModal`: Opens the modal for adding or editing a contact.
  - `closeModal`: Closes the modal.
  - `addOrUpdateContact`: Adds a new contact or updates an existing one.
  - `deleteContact`: Deletes a contact.
  - `viewContactDetails`: Opens the modal to view contact details.
  - `handleSearch`: Filters contacts based on the search term.

---

### 2. `ContactList.js`

This component renders the list of contacts. It displays a button to add a new contact and iterates over the `contacts` prop to show each contact using the `ContactCard` component.

#### Key Features:
- **Props**:
  - `contacts`: The list of filtered contacts to display.
  - `openModal`: Function to open the modal.
  - `deleteContact`: Function to delete a contact.
  - `viewContactDetails`: Function to view contact details.
  - `handleSearch`: Function to update the search term.

- **Search Bar**:
  - The `SearchBar` component is included here for users to search through the contacts.

---

### 3. `Modal.js`

This component renders a modal dialog used for adding, editing, or viewing contact details. The modal is customizable based on whether the user is editing or viewing a contact.

#### Key Features:
- **Props**:
  - `contact`: The contact data (either for editing or viewing).
  - `closeModal`: Function to close the modal.
  - `onSave`: Function to save the contact after editing.
  - `isViewOnly`: A boolean flag to disable editing when viewing contact details.
  
- **State**:
  - `formData`: Manages the form input values for name, email, and mobile number.
  
- **Helper Functions**:
  - `handleChange`: Updates the form data as the user types in the input fields.
  - `handleSubmit`: Submits the form and saves the contact by calling the `onSave` function.

---

### 4. `ContactCard.js`

This component represents a single contact in the contact list. It displays the contact’s name and mobile number, and includes action buttons for viewing, editing, or deleting the contact.

#### Key Features:
- **Props**:
  - `contact`: The individual contact data.
  - `openModal`: Function to open the modal for editing the contact.
  - `deleteContact`: Function to delete the contact.
  - `viewContactDetails`: Function to view the contact details.
  
- **Action Buttons**:
  - "👁️" button: Opens the modal to view the contact details.
  - "✏️" button: Opens the modal to edit the contact.
  - "🗑️" button: Deletes the contact.

---

### 5. `SearchBar.js`

This component provides a search bar to filter contacts by name or phone number.

#### Key Features:
- **Props**:
  - `handleSearch`: Function to update the search term in the parent component.
  
- **Search Input**:
  - The input field captures the search term entered by the user, triggering the filtering of contacts in `App.js`.

---


---

## Conclusion

This React contact management app demonstrates how to build a simple CRUD application using React and hooks. It includes features such as modals for adding/editing contacts, search functionality, and a clean interface for managing contact details.

