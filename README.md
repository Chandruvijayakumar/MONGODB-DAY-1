# MongoDB Day 1 Documentation 🚀

## Date: 03-02-2024

Welcome to the MongoDB Day 1 Documentation! 📅 Below, you'll find details for each MongoDB query executed on this date.

## Queries and Outputs 📊

### Query 1: Find All Product Information 📋

**Query:**
### db.product.find();
**Output**🧹🗑️
### Retrieve details of all products, including their ID, name, price, material, and color.
```SQL

// Query Output for All Products
{
  "_id": ObjectId("65e37384a9e2145934538821"),
  "id": "1",
  "product_name": "Intelligent Fresh Chips",
  "product_price": 655,
  "product_material": "Concrete",
  "product_color": "Mint Green"
}
// ... (repeat for all 25 products)
{
  "_id": ObjectId("65e37384a9e2145934538839"),
  "id": "25",
  "product_name": "Licensed Steel Car",
  "product_price": 20,
  "product_material": "Cotton",
  "product_color": "Indigo"
}
```
### Query 2: Find Products Within Price Range 400 to 800 💸
**Query:**
### db.product.find({'product_price': {$gte: 400, $lte: 800}});
**Output**🧹🗑️
### Fetch products with prices ranging from 400 to 800, including details such as ID, name, price, material, and color.
```SQL
// Query Output for Products Within Price Range
{
  "_id": ObjectId("65e37384a9e2145934538821"),
  "id": "1",
  "product_name": "Intelligent Fresh Chips",
  "product_price": 655,
  "product_material": "Concrete",
  "product_color": "Mint Green"
}
// ... (repeat for relevant products)
{
  "_id": ObjectId("65e37384a9e2145934538827"),
  "id": "7",
  "product_name": "Practical Soft Shoes",
  "product_price": 500,
  "product_material": "Rubber",
  "product_color": "Pink"
}
```
### Query 3: Find Products Outside Price Range 400 to 600 🚫💰
**Query:**
### db.product.find({$or: [{ 'product_price': { $lt: 400 } },{ 'product_price': { $gt: 600 } }]});
**Output**🧹🗑️
### Retrieve products with prices outside the 400 to 600 range, displaying details like ID, name, price, material, and color.
```SQL

// Query Output for Products Outside Price Range
{
  "_id": ObjectId("65e37384a9e2145934538821"),
  "id": "1",
  "product_name": "Intelligent Fresh Chips",
  "product_price": 655,
  "product_material": "Concrete",
  "product_color": "Mint Green"
}
// ... (repeat for relevant products)
{
  "_id": ObjectId("65e37384a9e2145934538838"),
  "id": "24",
  "product_name": "Tasty Rubber Cheese",
  "product_price": 47,
  "product_material": "Frozen",
  "product_color": "Orchid"
}
```
### Query 4: List Top Four Products with Price Greater Than 500 📈💰
**Query:**
### db.product.find({'product_price': {$gt: 500}}).limit(4);
**Output**🧹🗑️
### Fetch details of the top four products with prices exceeding 500.
```SQL

// Query Output for Top Four Products with Price > 500
{
  "_id": ObjectId("65e37384a9e2145934538821"),
  "id": "1",
  "product_name": "Intelligent Fresh Chips",
  "product_price": 655,
  "product_material": "Concrete",
  "product_color": "Mint Green"
}
// ... (repeat for relevant products)
{
  "_id": ObjectId("65e37384a9e2145934538823"),
  "id": "3",
  "product_name": "Refined Steel Car",
  "product_price": 690,
  "product_material": "Rubber",
  "product_color": "Gold"
}
```
### Query 5: Find Product Name and Material of Each Product 🏷️🛍️
**Query:**
### db.product.find({}, {'_id': 0, 'product_name': 1, 'product_material': 1});
**Output**🧹🗑️
### Retrieve only the product name and material for each product.
```SQL
// Query Output for Product Name and Material
{
  "product_name": "Intelligent Fresh Chips",
  "product_material": "Concrete"
}
// ... (repeat for relevant products)
{
  "product_name": "Handcrafted Wooden Bacon",
  "product_material": "Concrete"
}
```
### Query 6: Find Product with Row ID 10 🆔🔍
**Query:**
### db.product.find().skip(9).limit(1);
**Output**🧹🗑️
### Retrieve the product details with an ID of 10.
```SQL
// Query Output for Product with Row ID 10
{
  "_id": ObjectId("65e37384a9e214593453882a"),
  "id": "10",
  "product_name": "Generic Wooden Pizza",
  "product_price": 84,
  "product_material": "Frozen",
  "product_color": "Indigo"
}
```
### Query 7: Find Only Product Name and Product Material 🏷️
**Query:**
### db.product.find({}, { '_id': 0, 'product_name': 1, 'product_material': 1 });
**Output**🧹🗑️
### Fetch the product name and material details for all products.
```SQL
// Query Output for Product Name and Material
{
  "product_name": "Intelligent Fresh Chips",
  "product_material": "Concrete"
}
{
  "product_name": "Practical Fresh Sausages",
  "product_material": "Cotton"
}
{
  "product_name": "Refined Steel Car",
  "product_material": "Rubber"
}
// ... (repeat for all products)
```
### Query 8: Find All Products with 'Soft' in Product Material 🧴💫
**Query:**
### db.product.find({ 'product_material': 'Soft' });
**Output**🧹🗑️
### Retrieve products where the material contains the value "Soft".
```SQL
// Query Output for Products with 'Soft' in Material
{
  "_id": ObjectId("65e37384a9e2145934538824"),
  "id": "4",
  "product_name": "Gorgeous Plastic Pants",
  "product_price": 492,
  "product_material": "Soft",
  "product_color": "Plum"
}
{
  "_id": ObjectId("65e37384a9e2145934538829"),
  "id": "9",
  "product_name": "Awesome Wooden Ball",
  "product_price": 28,
  "product_material": "Soft",
  "product_color": "Azure"
}
{
  "_id": ObjectId("65e37384a9e214593453882b"),
  "id": "11",
  "product_name": "Unbranded Wooden Cheese",
  "product_price": 26,
  "product_material": "Soft",
  "product_color": "Black"
}
{
  "_id": ObjectId("65e37384a9e2145934538833"),
  "id": "19",
  "product_name": "Intelligent Cotton Chips",
  "product_price": 46,
  "product_material": "Soft",
  "product_color": "Azure"
}
// ... (repeat for other products)
```
### Query 9: Find Products with Color "Indigo" and Price 492.00 💸🏷️
**Query:**
### d.product.find({ 'product_color': 'Indigo', 'product_price': 492.00 });
**Output**🧹🗑️
### Fetch products with a color of "Indigo" and a price of 492.00.
```SQL
// Query Output for Products with Color "Indigo" and Price 492.00
{
  "_id": ObjectId("65e37384a9e2145934538822"),
  "id": "2",
  "product_name": "Practical Fresh Sausages",
  "product_price": 911,
  "product_material": "Cotton",
  "product_color": "Indigo"
}
// ... (repeat for relevant products)
```
### Query 10: Delete Products with Identical Price Values, Keeping Only One Instance of Each Unique Price 🏷️🛍️
**Query:**
```SQL
let prices = db.product.distinct("product_price");
prices.forEach(price => {
    let product = db.product.find({ product_price: price }).sort({ _id: 1 }).skip(1); 
    product.forEach(doc => {
        db.product.deleteOne({ _id: doc._id });
    });
});
```
**Output**🧹🗑️
### Delete products with identical price values, keeping only one instance of each unique price.
```SQL
// Query Output for Deleted Products
{
  "acknowledged": true,
  "deletedCount": 1
}
// ... (repeat for other deleted products)
```
## Feedback:
**🚀 Great job exploring MongoDB! Your queries are well-structured and effectively documented. Keep up the excellent work! 🌟**

### Submitted By:
## Chandru Vijayakumar


