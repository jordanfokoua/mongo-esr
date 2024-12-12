
# **MongoDB ESR Example Dataset**

This repository contains a sample dataset (`book-library.books.json.zip`) designed to demonstrate MongoDB query optimization techniques using the **ESR Rule** (Equality → Sort → Range). The dataset was generated using **Mockaroo** and is structured to mimic a library system with fictional book records.

---

## **Dataset Overview**

The dataset includes fields such as:  

- `title`: The title of the book.  
- `author`: The author of the book.  
- `genre`: The genre of the book (e.g., Fiction, Non-Fiction).  
- `publication_date`: The publication date of the book.  
- `price`: The price of the book.  
- `rating`: The average rating of the book.  
- `available`: A boolean indicating if the book is available for checkout.  
- `deleted`: A boolean flag for logical deletion.  

---

## **How to Use This Dataset**

### **1. Download and Extract the Dataset**  

1. Clone this repository or download it as a ZIP file:  

   ```bash
   git clone git@github.com:jordanfokoua/mongo-esr.git
   ```

2. Navigate to the repository directory and extract the `book-library.books.json.zip` file:  

   ```bash
   unzip book-library.books.json.zip
   ```

---

### **2. Import the Dataset into MongoDB**

To import the dataset into your MongoDB instance, follow these steps:

#### **Option 1: Using `mongoimport` (CLI)**  

1. Open your terminal.  
2. Run the following command to import the dataset:  

   ```bash
   mongoimport --db library --collection books --file book-library.books.json --jsonArray
   ```

   - `--db library`: Specifies the database name (`library`).  
   - `--collection books`: Specifies the collection name (`books`).  
   - `--file book-library.books.json`: The extracted dataset file.  
   - `--jsonArray`: Indicates the file contains a JSON array of documents.  

3. Verify the import by opening the MongoDB shell and checking the collection:  

   ```bash
   mongo
   use library
   db.books.count()
   ```

---

#### **Option 2: Using MongoDB Compass (GUI)**  

1. Open **MongoDB Compass** and connect to your MongoDB instance.  
2. Create a database called `library`.  
3. Create a collection named `books`.  
4. Inside the `books` collection, click on **"Add Data" → "Import JSON"**.  
5. Select the extracted `book-library.books.json` file.  

---

## **Dataset Details**

This dataset is designed for experimenting with query optimization techniques such as:  

- Filtering documents using equality conditions.  
- Sorting results by multiple fields.  
- Applying range filters.  
- Demonstrating performance differences between queries with and without indexes.  

For a step-by-step guide to query optimization using this dataset, check out my blog post: [How we used the ESR rule to lift MongoDB queries performance](blog.jordanfokoua.dev/optimize-mongo-queries-with-esr/)  

---

## **License**

This project is licensed under the MIT License. Feel free to use or modify the dataset for your own projects.  

---

Got questions or feedback? Feel free to open an issue or reach out!  
