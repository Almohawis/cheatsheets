# SQL

| Numbers       | INT                      |
| ------------- | ------------------------ |
| String        | varchar(255)             |
| String        | Text                     |
| DATE AND TIME | time (فقط الوقت 24 ساعة) |
| data          | date                     |
|               | datetime                 |
|               |                          |
|               |                          |

NULL - NOT NULL - حقل فاضي او حقل غير فاضي

# Create User إنشاء مستخدم

    CREATE USER 'username'@'localhost' IDENTIFIED BY 'password';
    
    GRANT ALL PRIVILEGES ON database_name.* TO 'username'@'localhost';
    OR
    GRANT ALL PRIVILEGES ON *.* TO 'username'@'localhost';
    
    FLUSH PRIVILEGES; 

## Create DataBase انشاء قاعدة بيانات

    CREATE DATABASE name CHARACTER SET utf8mb4 COLLATE utf8mb4_bin;

## Delete DataBase حذف قاعدة بيانات

    DROP DATABASE name

## Create Table - انشاء جدول

    CREATE TABLE name(
       id int(11) unsigned auto_increment PRIMARY key,
        name varchar(3) not null,
        description text null    
    
    )

## Input Data - إدخال بيانات

    INSERT into products (name, description)
    VALUES ('Pc', 'A Gaming Pc');

## Show Data - اظهار البيانات

    SELECT * FROM name 
    
    SELECT name,description from products

## searsh - بحث

    SELECT * FROM products WHERE id=2

او لاجل يبحث ويجيب التكمله

    SELECT * FROM products WHERE name LIKE  'Ser%' ;
    SELECT * FROM products WHERE name LIKE  '%Ser' ;

لكن الأحرف الكبيرة و الصغيره حساسه

## الترتيب

    SELECT * FROM products ORDER BY id; 
    
    SELECT * FROM products ORDER BY id DESC;
    
    SELECT * FROM products ORDER BY id ASC, name DESC

بعدين ارحع اشرح اكثر

## حد عدد البيانات المستخرجه

`LIMIT number`

    SELECT * FROM `products` LIMIT 1

# تحديث المدخلات

    UPDATE products SET name = 'Tesing' WHERE id = 4

حذف

    DELETE FROM products WHERE id > 10;

# إضافة عامود جديد

    ALTER TABLE products ADD COLUMN prices decimal(6, 2) UNSIGNED NOT NULL;

تعديل على عامود في الجدول

    ALTER TABLE products MODIFY id int(12)
    
    ALTER TABLE products MODIFY name text
    
    
    
    INSERT INTO products (name, description, price) VALUES ("Dell PowerEdge T620", "Server Dell 2013 2 Intel Xezon With 24 Thred And 94 GB Of Ram" , 1400,50);
    INSERT INTO products (name, description, price) VALUES ("Dell PowerEdge R820", "Server Dell 2019 4 Intel Xezon With 64 Thred And 512 GB Of Ram" , 6500);
    INSERT INTO products (name, description, price) VALUES ("Dell PowerEdge R730", "Server Dell 2017 2 Intel Xezon With 32 Thred And 64 GB Of Ram" , 2500.99)

تغيير الإسم

    ALTER TABLE products CHANGE name title text

حذف عامود

    ALTER TABLE products DROP price
