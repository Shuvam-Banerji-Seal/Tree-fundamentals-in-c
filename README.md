# Binary Tree Operations in C

This C program implements operations on a binary tree, including insertion, deletion, searching, and various traversals such as inorder, preorder, postorder, and level order. The program allows users to interactively perform these operations through a menu-driven interface. Additionally, the program provides traversal information to assist users in understanding the different traversal techniques employed.

## Data Structures

### 1. `struct TreeNode`
   - Description: Structure representing a node in the binary tree.
   - Members:
     - `val`: Integer value stored in the node.
     - `left`: Pointer to the left child node.
     - `right`: Pointer to the right child node.

## Functions Overview

### 1. `menu()`
   - Description: Function to display a menu for user interaction and execute corresponding tree operations based on user input.
   - Algorithm:
     - The function continuously displays a menu of options for the user to choose from.
     - It reads the user's choice and calls the respective function to perform the selected operation on the binary tree.

### 2. `main()`
   - Description: Main function to call the `menu()` function and start the program.

### 3. `create(int data)`
   - Description: Function to create a new tree node with the given data.
   - Parameters:
     - `data`: Integer value to be assigned to the new node.
   - Returns: Pointer to the newly created node.
   - Algorithm:
     - Allocates memory for a new tree node.
     - Initializes the node with the given data and sets its left and right pointers to NULL.
     - Returns a pointer to the newly created node.
   - Example:
     ```c
     struct TreeNode* node = create(10);
     ```

### 4. `insert(int data)`
   - Description: Function to insert a new node with the given data into the binary tree.
   - Parameters:
     - `data`: Integer value to be inserted into the tree.
   - Algorithm:
     - If the tree is empty, creates a new node and sets it as the root.
     - Otherwise, performs a level-order traversal using a queue to find the appropriate position to insert the new node.
     - Inserts the new node as the left child if the current node has no left child, or as the right child if it has no right child.
   - Example:
     ```c
     insert(20);
     ```

### 5. `delete(int key)`
   - Description: Function to delete a node with the given key from the binary tree.
   - Parameters:
     - `key`: Integer value representing the node to be deleted from the tree.
   - Algorithm:
     - If the tree is empty, returns.
     - Performs a level-order traversal using a queue to find the node with the given key.
     - Replaces the data of the node to be deleted with the data of the deepest node in the tree.
     - Deletes the deepest node and updates its parent's pointer accordingly.
   - Example:
     ```c
     delete(15);
     ```

### 6. `search(int key)`
   - Description: Function to search for a node with the given key in the binary tree.
   - Parameters:
     - `key`: Integer value representing the node to be searched for in the tree.
   - Returns: `1` if the node is found, `-1` otherwise.
   - Algorithm:
     - If the tree is empty, returns -1.
     - Performs a level-order traversal using a queue to search for the node with the given key.
     - Returns 1 if the node is found, -1 otherwise.
   - Example:
     ```c
     int result = search(25);
     ```

### 7. `height(struct TreeNode* root)`
   - Description: Function to calculate the height of the binary tree.
   - Parameters:
     - `root`: Pointer to the root node of the tree.
   - Returns: Height of the tree.
   - Algorithm:
     - If the tree is empty, returns 0.
     - Recursively calculates the height of the left and right subtrees.
     - Returns the maximum height among the left and right subtrees, plus 1.
   - Example:
     ```c
     int treeHeight = height(root);
     ```

### 8. `inorder(struct TreeNode* root)`
   - Description: Function to perform an inorder traversal of the binary tree.
   - Parameters:
     - `root`: Pointer to the root node of the tree.
   - Algorithm:
     - If the current node is NULL, returns.
     - Recursively traverses the left subtree.
     - Prints the value of the current node.
     - Recursively traverses the right subtree.
   - Example:
     ```c
     inorder(root);
     ```

### 9. `preorder(struct TreeNode* root)`
   - Description: Function to perform a preorder traversal of the binary tree.
   - Parameters:
     - `root`: Pointer to the root node of the tree.
   - Algorithm:
     - If the current node is NULL, returns.
     - Prints the value of the current node.
     - Recursively traverses the left subtree.
     - Recursively traverses the right subtree.
   - Example:
     ```c
     preorder(root);
     ```

### 10. `postorder(struct TreeNode* root)`
   - Description: Function to perform a postorder traversal of the binary tree.
   - Parameters:
     - `root`: Pointer to the root node of the tree.
   - Algorithm:
     - If the current node is NULL, returns.
     - Recursively traverses the left subtree.
     - Recursively traverses the right subtree.
     - Prints the value of the current node.
   - Example:
     ```c
     postorder(root);
     ```

### 11. `levelorder()`
   - Description: Function to perform a level order traversal of the binary tree.
   - Algorithm:
     - If the tree is empty, prints "Tree is Empty!" and returns.
     - Uses a queue to traverse the tree level by level.
     - Prints the value of each node as it is visited.
   - Example:
     ```c
     levelorder();
     ```

### 12. `traversalInfo()`
   - Description: Function to print traversal information explaining various traversal techniques.
   - Algorithm:
     - Prints information about four different types of tree traversals: inorder, preorder, postorder, and level order.
   - Example:
     ```c
     traversalInfo();
     ```
## Additional Notes

- The program utilizes a queue data structure for level-order traversal, allowing efficient exploration of tree nodes level by level.
- All functions are implemented with recursive algorithms to traverse or manipulate tree nodes.
- It's important to manage memory properly, especially when allocating and deallocating memory for tree nodes using `malloc` and `free`.

## Example Usage

```c
#include <stdio.h>
#include <stdlib.h>

// Include the binary tree operations header file here

int main() {
    // Create a new binary tree node with value 10
    struct TreeNode* root = create(10);

    // Insert new nodes into the binary tree
    insert(20);
    insert(15);
    insert(25);
    insert(5);

    // Perform various tree operations
    printf("Height of the tree: %d\n", height(root));
    printf("Inorder Traversal: ");
    inorder(root);
    printf("\nPreorder Traversal: ");
    preorder(root);
    printf("\nPostorder Traversal: ");
    postorder(root);
    printf("\nLevel Order Traversal: ");
    levelorder();

    // Search for a node in the tree
    int key = 15;
    int result = search(key);
    if (result == 1) {
        printf("\nNode with value %d found in the tree.\n", key);
    } else {
        printf("\nNode with value %d not found in the tree.\n", key);
    }

    // Delete a node from the tree
    delete(20);

    // Print traversal information
    printf("\nTraversal Information:\n");
    traversalInfo();

    return 0;
}

```
## Conclusion
This program provides a comprehensive set of operations for working with binary trees in C, including insertion, deletion, searching, and various traversal techniques. It serves as a useful reference for understanding and implementing binary tree algorithms efficiently.
