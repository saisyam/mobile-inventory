# Mobile Inventory
Web application to manage inventory, sales and purchase

# Scope
The application should support the following features:
1. Maintaining the device inventory. CRUD operations on the devices
2. Sale/Purchase of the devices. Sale/purchase may happen directly from the customer or from the market. Market means other vendor.
3. Capturing buyer/seller information
4. Generating reports

# Technology
We will be using Python FastAPI for developing the backend APIs and SQLite database for development. We use PostgreSQL for production deployment. React Native for mobile application.

# Highlevel DB schema
```
CREATE TABLE device_details (
    device_id INTEGER NOT NULL PRIMARY KEY,
    make VARCHAR(20),
    model VARCHAR(20),
    imei1 VARCHAR(15),
    imei2 VARCHAR(15),
    price DECIMAL(7, 2),
    created_date DATETIME
);

CREATE TABLE sale_details (
    sale_id INTEGER NOT NULL PRIMARY KEY,
    device_id INTEGER,
    buyer_name VARCHAR(20),
    buyer_aadhaar_no VARCHAR(12),
    buyer_pan_no VARCHAR(15),
    buyer_address VARCHAR(200),
    buyer_mobile_no VARCHAR(10),
    selling_price DECIMAL(7, 2),
    sale_date DATETIME,
    direct TINYINT(1),
    comments VARCHAR(300)
);

CREATE TABLE purchase_details (
    purchase_id INTEGER NOT NULL PRIMARY KEY,
    device_id INTEGER,
    seller_name VARCHAR(20),
    seller_aadhaar_no VARCHAR(12),
    seller_pan_no VARCHAR(15),
    seller_address VARCHAR(200),
    seller_mobile_no VARCHAR(10),
    purchase_price DECIMAL(7, 2),
    purchase_date DATETIME,
    direct TINYINT(1),
    comments VARCHAR(300)
);
```


