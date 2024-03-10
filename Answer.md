1Q.ANS: 1.One product can belong to only one product category.
        2.However, one product category can have multiple products associated with it.
		
	CREATE TABLE product (
    product_id INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(50) NOT NULL,
    description VARCHAR(100) UNIQUE NOT NULL,
    SKU VARCHAR(100) NOT NULL,
    created_id INT,
    inventory_id INT,
    price DECIMAL,
    discount_id INT,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    modified_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    deleted_at TIMESTAMP DEFAULT NULL,
    FOREIGN KEY (created_id) REFERENCES product_category(id)  -- Establishing the one-to-many relationship
	);
----------------------------------------------------------------------------------------------------------------------
2Q.ANS: To ensure that each product in the "Product" table has a valid category assigned to it, 
you can use a foreign key constraint with the NOT NULL constraint on the created_id column in the "Product" table. 
This way, every product must have a valid category assigned to it, and the database will enforce this constraint.

CREATE TABLE product (
    product_id INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(50) NOT NULL,
    description VARCHAR(100) UNIQUE NOT NULL,
    SKU VARCHAR(100) NOT NULL,
    created_id INT NOT NULL, -- Ensuring the column is not null
    inventory_id INT,
    price DECIMAL,
    discount_id INT,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    modified_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    deleted_at TIMESTAMP DEFAULT NULL,
    FOREIGN KEY (created_id) REFERENCES product_category(id)  -- Establishing the one-to-many relationship
);
