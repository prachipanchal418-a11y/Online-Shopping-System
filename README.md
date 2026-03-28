# 🛒 Online Shopping System (C++)

## 📌 Introduction

The **Online Shopping System** is a console-based application developed using **C++** and **Object-Oriented Programming (OOP)** concepts. This system simulates a basic e-commerce platform where users can add products, view available items, add products to a cart, and generate a final bill.

It is designed to help understand how real-world shopping systems work in a simplified manner.

---

## 🎯 Objectives of the Project

* To implement an online shopping system using C++
* To apply OOP concepts like **classes, objects, and encapsulation**
* To manage products and cart operations efficiently
* To create a user-friendly menu-driven application

---

## 🧠 Methodology / System Design

### 🔹 Classes Used:

1. **Product Class**

   * Stores product details (ID, Name, Price)
   * Functions:

     * `input()` → Take product details
     * `display()` → Show product details

2. **Cart Class**

   * Stores cart details (Name, Price, Quantity)

---

### 🔄 System Flow:

1. Admin/User adds products
2. Products are displayed
3. User selects product by ID
4. Product is added to cart with quantity
5. User views cart
6. System generates final bill

---

## 💻 Implementation / Source Code
```
#include <iostream>
#include <vector>
using namespace std;

class Product {
public:
    int id;
    string name;
    float price;

    void input() {
        cout << "Enter Product ID: ";
        cin >> id;
        cout << "Enter Product Name: ";
        cin >> name;
        cout << "Enter Product Price: ";
        cin >> price;
    }

    void display() {
        cout << id << "\t" << name << "\t" << price << endl;
    }
};

class CartItem {
public:
    int id;
    string name;
    float price;
    int quantity;
};

vector<Product> products;
vector<CartItem> cart;

// Admin add product
void addProduct() {
    Product p;
    p.input();
    products.push_back(p);
    cout << "Product Added Successfully!\n";
}

// Display products
void displayProducts() {
    cout << "\nProduct List:\n";
    cout << "ID\tName\tPrice\n";
    for (int i = 0; i < products.size(); i++) {
        products[i].display();
    }
}

// Add to cart
void addToCart() {
    int pid, qty;
    cout << "Enter Product ID to Add to Cart: ";
    cin >> pid;

    for (int i = 0; i < products.size(); i++) {
        if (products[i].id == pid) {
            CartItem c;
            c.id = products[i].id;
            c.name = products[i].name;
            c.price = products[i].price;
            cout << "Enter Quantity: ";
            cin >> qty;
            c.quantity = qty;
            cart.push_back(c);
            cout << "Added to Cart!\n";
            return;
        }
    }
    cout << "Product Not Found!\n";
}

// View Cart
void viewCart() {
    cout << "\nCart Items:\n";
    cout << "ID\tName\tPrice\tQty\n";
    for (int i = 0; i < cart.size(); i++) {
        cout << cart[i].id << "\t" << cart[i].name << "\t"
             << cart[i].price << "\t" << cart[i].quantity << endl;
    }
}

// Generate Bill
void generateBill() {
    float total = 0;
    cout << "\n----- BILL -----\n";
    cout << "Name\tPrice\tQty\tTotal\n";

    for (int i = 0; i < cart.size(); i++) {
        float t = cart[i].price * cart[i].quantity;
        cout << cart[i].name << "\t" << cart[i].price << "\t"
             << cart[i].quantity << "\t" << t << endl;
        total += t;
    }

    cout << "-----------------\n";
    cout << "Total Amount: " << total << endl;
}

// Main Menu
int main() {
    int choice;

    while (true) {
        cout << "\n===== Online Shopping System =====\n";
        cout << "1. Add Product (Admin)\n";
        cout << "2. View Products\n";
        cout << "3. Add to Cart\n";
        cout << "4. View Cart\n";
        cout << "5. Generate Bill\n";
        cout << "6. Exit\n";
        cout << "Enter Choice: ";
        cin >> choice;

        switch (choice) {
        case 1:
            addProduct();
            break;
        case 2:
            displayProducts();
            break;
        case 3:
            addToCart();
            break;
        case 4:
            viewCart();
            break;
        case 5:
            generateBill();
            break;
        case 6:
            exit(0);
        default:
            cout << "Invalid Choice!\n";
        }
    }
}
```

## ⚙️ Features

* Add new products
* Display available products
* Add products to cart
* View cart items
* Generate total bill
* Menu-driven interface

## 📊 Sample Output

```
===== ONLINE SHOPPING SYSTEM =====
1. Add Product
2. Display Products
3. Add to Cart
4. View Cart
5. Generate Bill
6. Exit
```

---

## 📌 Conclusion

This project demonstrates the implementation of a basic online shopping system using C++. It enhances understanding of OOP concepts, data handling, and user interaction in real-world applications.

---

## 🚀 Future Improvements

* Add user login system 🔐
* Store data using file handling 📁
* Add product search functionality 🔍
* Improve UI using graphics or GUI
* Add payment system simulation 💳

---

## 🛠️ Technologies Used

* C++
* Object-Oriented Programming (OOP)
* STL (vector)

---

## 👨‍💻 Author

Prachi Panchal
B.Tech CSE (1st Year)
JG University

---
