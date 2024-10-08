
# QuickStatements 3.0 Documentation

## Introduction
QuickStatements 3.0 is a tool designed to streamline the process of adding and modifying large quantities of data on Wikidata. It allows users to submit, update, and manage data efficiently, leveraging both CSV and command-based formats. This tool is particularly useful for users who need to handle bulk edits to Wikidata entities, ensuring accurate and rapid data manipulation.

QuickStatements is developed as part of Wiki Movimento Brasil's ongoing efforts to improve the Wikimedia ecosystem, making data contributions more accessible to both technical and non-technical users.

## Project Overview
### Problem Statement
Many users face challenges when managing large datasets on Wikidata, where manual input is slow and prone to error. With the increasing amount of data that needs to be uploaded, modified, or deleted, there is a critical need for an efficient, user-friendly tool that can handle bulk operations.

### Solution
QuickStatements 3.0 offers a streamlined interface for users to upload and edit data using batch commands or CSV files. It improves upon the previous versions by introducing enhanced functionality, stability, and a more intuitive user interface. The platform automates repetitive tasks, ensuring that users can submit bulk data accurately and efficiently.

## Home Page Functionality

The homepage of QuickStatements 3.0 serves as the entry point for users to interact with the tool. It provides access to the key features of the application and allows users to navigate through the core functionalities of QuickStatements.

### 1. **Welcome Section**
The homepage begins with a simple and welcoming header:
```html
<h1>Welcome to QuickStatements 3.0</h1>
```
This section serves as an introduction for users, clearly indicating that they have arrived at the main interface of the tool.

### 2. **New Batch Button**
One of the most important features of QuickStatements 3.0 is the ability to create new batches for data submission. This is facilitated by a prominent "New Batch" button on the homepage:
```html
<a role="button" href="{% url 'new_batch' %}"> New batch </a>
```
By clicking this button, users are taken to the `new_batch` page, where they can define a new batch of data commands for submission.

### 3. **Batch Lookup Form**
The homepage also allows users to look up specific batches by their ID. This feature is particularly useful for users who want to review the status or details of a particular batch they have previously submitted.

The batch lookup form is structured as follows:
```html
<form id="batchForm">
  <fieldset role="group">
    <input id="batchInput" type="number" placeholder="Batch ID..." oninput="updateBatchForm()" required />
    <input type="submit" value="See batch details" />
  </fieldset>
</form>
```
- **Batch ID Input**: Users can input a batch ID to retrieve specific batch details.
- **Submit Button**: Clicking the submit button directs the user to the batch details page, where they can view the status of the batch, its commands, and other relevant information.

### 4. **User Lookup Form**
Similar to batch lookup, the homepage also provides a feature for users to search for batches by username. This feature helps users track all the batches associated with a particular user account.

The form for user lookup is structured as follows:
```html
<form id="userForm">
  <fieldset role="group">
    <input id="userInput" type="text" placeholder="Username..." oninput="updateUserForm()" required />
    <input type="submit" value="See batches by user" />
  </fieldset>
</form>
```
- **Username Input**: Users can input a username to retrieve a list of batches submitted by that user.
- **Submit Button**: Clicking the submit button will display all batches associated with the provided username.

### 5. **Navigation Bar**
The navigation bar at the top of the homepage offers quick access to the following links:
- **Home**: The main page of the tool.
- **New Batch**: Redirects users to create a new batch of data commands.
- **Last Batches**: (Planned Feature) A link to view recent batches submitted by users.
- **Git Repository**: A link to the project's GitHub repository for developers and contributors.

```html
<nav>
  <ul>
    <li><a href="{% url 'home' %}"><strong>QuickStatements 3.0</strong></a></li>
    <li><a href="{% url 'new_batch' %}">New batch</a></li>
    <li><a href="">Last batches</a></li>
    <li><a href="https://github.com/WikiMovimentoBrasil/quickstatements3">Git</a></li>
  </ul>
  <ul>
    {% if user.is_anonymous %}
    <li><a href="">Login</a></li>
    {% else %}
    <li><a href="">User:{{user}}</a></li>
    <li><a href="">Your last batches</a></li>
    {% endif %}
  </ul>
</nav>
```

### 6. **User Authentication Section**
If the user is anonymous, a login link is displayed to allow them to authenticate and access user-specific features. If the user is logged in, the navigation bar will display their username and provide access to their last batches.

## Conclusion
The homepage of QuickStatements 3.0 serves as the primary hub for managing data on Wikidata. Through its user-friendly interface, it offers quick access to the core functionalities of the tool, such as creating new batches, viewing batch details, and managing user data submissions. The streamlined layout ensures that users can navigate efficiently, improving their experience with data management tasks.

This documentation explains all the key features of the homepage, ensuring that users understand how to utilize the main tools available on QuickStatements 3.0.

