# Library Management System
# Table of Contents

1. [Overview](#overview)
2. [Features](#features)
3. [Architecture](#architecture)
4. [Data Structures](#data-structures)
   - [Book](#book)
   - [User](#user)
   - [StackNode](#stacknode)
   - [QueueNode](#queuenode)
   - [TreeNode](#treenode)
5. [Code Structure](#code-structure)
   - [Main Function](#main-function)
   - [Book Functions](#book-functions)
   - [User Functions](#user-functions)
   - [Stack Functions](#stack-functions)
   - [Queue Functions](#queue-functions)
   - [Binary Search Tree (BST) Functions](#binary-search-tree-bst-functions)
6. [Usage](#usage)
7. [Files](#files)
8. [Example](#example)
9. [Future Improvements](#future-improvements)
10. [Contributing](#contributing)


## Overview

This project is a comprehensive library management system implemented in C. It allows users to manage books and users, facilitating various operations such as adding, removing, updating, and searching for both books and users. Additionally, the system supports borrowing and returning books, tracking recent activities through a stack, and managing requests using a queue. The project ensures persistent storage by saving and loading books and users from files, and employs a binary search tree (BST) for efficient book searching.

## Features

- **Book Management**: Add, remove, update, search, and display books.
- **User Management**: Add, remove, update, search, and display users.
- **Borrowing System**: Borrow and return books, updating their availability status.
- **Activity Tracking**: Maintain a stack of recent activities.
- **Request Queue**: Manage user requests using a queue.
- **Persistent Storage**: Save and load books and users from files.
- **Binary Search Tree (BST)**: Efficient search of books by title.

## Architecture

![Fonctionnement du Système de Gestion de Bibliothèque](https://github.com/omarhark/library_management_system/assets/141445140/9b22eeb6-334d-4f64-937a-9beacabc0ea8)


## Data Structures

### Book

```c
typedef struct Book {
    int id;
    char title[100];
    char author[50];
    char genre[30];
    int available; // 1 if available, 0 if borrowed
    struct Book *next;
} Book;
```

### User
```c
typedef struct User {
    int id;
    char name[50];
    char contact[50];
    struct User *next;
} User;
```

### StackNode
```c
typedef struct StackNode {
    int bookId;
    struct StackNode *next;
} StackNode;

```
### QueueNode
```c
typedef struct QueueNode {
    int userId;
    int bookId;
    struct QueueNode *next;
} QueueNode;
```
### TreeNode
```c
typedef struct TreeNode {
    Book *book;
    struct TreeNode *left;
    struct TreeNode *right;
} TreeNode;

```

## Code Structure
### Main Function

The main function provides a menu-driven interface for the user to interact with the system. It initializes the data structures, handles user input, and calls the appropriate functions based on the user's choice.
```c
int main() {
    Book *bookList = NULL;
    User *userList = NULL;
    StackNode *recentActivities = NULL;
    QueueNode *requestQueueFront = NULL, *requestQueueRear = NULL;
    TreeNode *bookTree = NULL;

    int choice, id;
    char title[100], author[50], genre[30], name[50], contact[50];

    while ((choice = displayMenu()) != 13) {
        switch (choice) {
            // Case statements for each menu option
        }
    }

    // Save all data to files before exiting
    saveBooksToFile(bookList);
    saveUsersToFile(userList);

    return 0;
}

```
### Book Functions
`addBook`

Adds a new book to the linked list and saves it to the file.
```c
void addBook(Book **head, int id, const char *title, const char *author, const char *genre) {
    // Implementation
}

```

`removeBook`

Removes a book from the linked list and updates the file.
```c
void removeBook(Book **head, int id) {
    // Implementation
}
```

`updateBook`

Updates the details of an existing book and updates the file.
```c
void updateBook(Book *head, int id, const char *newTitle, const char *newAuthor, const char *newGenre) {
    // Implementation
}
```


`searchBook`

Searches for a book by its ID in the linked list.
```c
Book *searchBook(Book *head, int id) {
    // Implementation
}
```



`displayBooks`

Displays all books in the linked list.
```c
void displayBooks(Book *head) {
    // Implementation
}

```



`saveBooksToFile`

Saves the linked list of books to a file.


```c
void saveBooksToFile(Book *head) {
    // Implementation
}
```

### User Functions
`addUser`

Adds a new user to the linked list and saves it to the file.

```c
void addUser(User **head, int id, const char *name, const char *contact) {
    // Implementation
}

```

`removeUser`

Removes a user from the linked list and updates the file.

```c
void removeUser(User **head, int id) {
    // Implementation
}

```
`updateUser`

Updates the details of an existing user and updates the file.

```c
void updateUser(User *head, int id, const char *newName, const char *newContact) {
    // Implementation
}

```


`searchUserByName`

Searches for a user by name in the linked list.

```c
User *searchUserByName(User *head, const char *name) {
    // Implementation
}


```


`searchUserById`

Searches for a user by ID in the linked list.

```c
User *searchUserById(User *head, int id) {
    // Implementation
}
```

`displayUsers`

Displays all users in the linked list.

```c
void displayUsers(User *head) {
    // Implementation
}
```

`saveUsersToFile`

Saves the linked list of users to a file.

```c
void saveUsersToFile(User *head) {
    // Implementation
}
```

### Stack Functions
`push`

Pushes a book ID onto the stack of recent activities.

```c
void push(StackNode **top, int bookId) {
    // Implementation
}
```

`pop`

Pops a book ID from the stack.

```c
int pop(StackNode **top) {
    // Implementation
}
```

`displayStack`

Displays the stack of recent activities.

```c
void displayStack(StackNode *top) {
    // Implementation
}
```

### Queue Functions
`enqueue`

Adds a user request to the queue.

```c
void enqueue(QueueNode **front, QueueNode **rear, int userId, int bookId) {
    // Implementation
}
```

`dequeue`

Removes a user request from the queue.

```c
void dequeue(QueueNode **front, QueueNode **rear) {
    // Implementation
}
```

`displayQueue`

Displays the queue of user requests.

```c
void displayQueue(QueueNode *front) {
    // Implementation
}
```

### Binary Search Tree (BST) Functions
`insertBookToBST`

Inserts a book into the BST based on its title.

```c
void insertBookToBST(TreeNode **root, Book *book) {
    // Implementation
}
```

`searchBookInBST`

Searches for a book by its title in the BST.

```c
Book *searchBookInBST(TreeNode *root, const char *title) {
    // Implementation
}
```

`displayBST`

Displays all books in the BST in order.

```c
void displayBST(TreeNode *root) {
    // Implementation
}
```

## Usage

1. **Compile the code**: Use a C compiler to compile the code.
    ```sh
    gcc -o library_management library_management.c
    ```

2. **Run the executable**: Execute the compiled file.
    ```sh
    ./library_management
    ```

3. **Follow the menu**: The program will display a menu with various options. Enter the number corresponding to your choice and follow the prompts.

## Files

- **books.txt**: Stores the list of books.
- **users.txt**: Stores the list of users.

## Example

To add a book:

1. Run the program.
2. Choose option 1 (Add Book).
3. Enter the book ID, title, author, and genre when prompted.

The book will be added to the list, saved to the file, and inserted into the BST for efficient searching.

## Future Improvements

- Implement a graphical user interface (GUI) for better user interaction.
- Enhance error handling and input validation.
- Add more features such as book reservation, user authentication, and overdue book tracking.

## Contributing

Contributions are welcome! Please fork the repository, make your changes, and submit a pull request.

