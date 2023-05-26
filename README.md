# MySQL_h_2
## 1. Используя операторы языка SQL, создайте табличку “sales”. Заполните ее данными ##   
CREATE TABLE homework2.sales (    
id INT PRIMARY KEY AUTO_INCREMENT,    
order_date DATE NOT NULL,    
busket INT NOT NULL    
);    
INSERT INTO homework.sales (order_date, busket) VALUES    
('2023-05-26', 102),   
('2023-05-27', 103),    
('2023-05-28', 40),    
('2023-05-29', 180),    
('2023-05-30', 400);    

SELECT * FROM homework2.sales;    
## 2. Сгруппируйте значений количества в 3 сегмента — меньше 100, 100-300 и больше 300. ##     
