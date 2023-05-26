# MySQL_h_2
## 1. Используя операторы языка SQL, создайте табличку “sales”. Заполните ее данными ##   
      
CREATE TABLE homework2.sales (    
id INT PRIMARY KEY AUTO_INCREMENT,    
order_date DATE NOT NULL,    
busket INT NOT NULL    
);   
     
INSERT INTO homework2.sales (order_date, busket) VALUES    
('2023-05-26', 102),   
('2023-05-27', 103),    
('2023-05-28', 40),    
('2023-05-29', 180),    
('2023-05-30', 400);    

SELECT * FROM homework2.sales;    
    
## 2. Сгруппируйте значений количества в 3 сегмента — меньше 100, 100-300 и больше 300. ##     
      
ALTER TABLE sales ADD orders VARCHAR(45);    
UPDATE sales SET orders=       
CASE       
WHEN busket > 300 THEN 'Большой заказ'     
WHEN busket > 99 THEN  'Средний заказ'    
ELSE 'Маленький заказ'    
END;    
     
SELECT * FROM homework2.sales WHERE orders 'Большой заказ';     
SELECT * FROM homework2.sales WHERE orders 'Средний заказ';     
SELECT * FROM homework2.sales WHERE orders 'Маленький заказ';     
     
## 3. Создайте таблицу “orders”, заполните ее значениями. Покажите “полный” статус заказа, используя оператор CASE ##      
       
CREATE TABLE homework2.orders (    
id INT PRIMARY KEY AUTO_INCREMENT,    
employeeid VARCHAR(45) NOT NULL,    
amount DECIMAL (10,2) DEFAULT 0.00,    
order_status VARCHAR(45) NOT NULL    
);   
     
INSERT INTO homework2.orders (employeeid, busket, order_status) VALUES    
('e03', 15.00, 'OPEN' ),    
('e01', 25.50,'OPEN'),    
('e05', 100.70, 'CLOSED'),    
('e02', 22.18,'OPEN'),    
('e04', 9.5,'CANSELLED'),    
('e04', 99.99,'OPEN');    
     
SELECT * FROM homework2.orders;    
     
SELECT id, order_status,       
CASE     
WHEN order_status = 'OPEN' THEN 'Order is in open state. '   
WHEN order_status = 'SLOSED' THEN 'Order is closed'    
WHEN order_status = 'CANSELLED' THEN 'Order is cancelled. '    
ELSE 'Status unknown'    
END AS order_summary    
FROM orders;    
          
          
 ## 4. Чем NULL отличается от 0? ##    
        
 NULL - это отсутствие значения     
 0 - это значение, хранящееся в памяти
