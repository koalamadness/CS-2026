# Computer Science
## 2026/03/19

## 2026/03/18

## 2026/03/17
Electro sf ping cat
## 2026/03/13

## 2026/03/12
Migration ORM Annotation Hibernate Microservices Bean API Gateway JWT bug
## 2026/03/11
SELECT f.title, l.name, f.rating, f.rental_rate FROM film f
JOIN language l ON f.language_id = l.language_id
WHERE rating = 'PG' AND rental_rate > 0.99
ORDER BY rental_rate DESC, title;

POSTGRE
package com.example.students.repository;

import com.example.students.model.Estudiante;
import org.springframework.data.jpa.repository.JpaRepository;
import org.springframework.stereotype.Repository;

@Repository
public interface EstudianteRepository extends JpaRepository<Estudiante, Long> {
}
package com.example.students.model;

import jakarta.persistence.*;

@Entity
@Table(name = "estudiantes") 
public class Estudiante {

    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;

    private String nombre;
    private String apellido;
    private String email;
    private String carrera;

    // Getters y Setters
    public Long getId() { return id; }
    public void setId(Long id) { this.id = id; }

    public String getNombre() { return nombre; }
    public void setNombre(String nombre) { this.nombre = nombre; }

    public String getApellido() { return apellido; }
    public void setApellido(String apellido) { this.apellido = apellido; }

    public String getEmail() { return email; }
    public void setEmail(String email) { this.email = email; }

    public String getCarrera() { return carrera; }
    public void setCarrera(String carrera) { this.carrera = carrera; }
}
## 2026/03/10
SELECT u.username, COUNT(DISTINCT p.post_id) AS total_posts, COUNT(DISTINCT c.comment_id) AS total_comments, COUNT(DISTINCT l.like_id) AS total_likes_given, COUNT(DISTINCT p.post_id) + COUNT(DISTINCT c.comment_id) + COUNT(DISTINCT l.like_id) AS total_engagement FROM users u LEFT JOIN posts p ON u.user_id = p.user_id LEFT JOIN comments c ON u.user_id = c.user_id LEFT JOIN likes l ON u.user_id = l.user_id GROUP BY u.user_id, u.username ORDER BY total_engagement DESC;
SELECT g.group_name, g.description, u.username AS creator_username, g.member_count, g.created_at
FROM users u
JOIN groups g ON u.user_id = g.created_by
WHERE g.privacy = 'public';
SELECT p.post_id, u.username, p.content AS post_content_preview, p.likes_count
FROM users u 
JOIN posts p ON u.user_id = p.user_id
ORDER BY p.likes_count DESC
LIMIT 10;
Cl
Bait
Rin
Sister
## 2026/03/09

## 2026/03/06
docker Bean Singleton Factory Layered
## 2026/03/05
Electro
Controller Service Repository DTO Entity Mapper 
JWT
## 2026/03/04
SELECT COUNT(*) AS total_queries 
FROM search_queries;
SELECT users.user_id FROM users
WHERE users.user_id NOT IN (
SELECT DISTINCT u.user_id
FROM users u
JOIN search_queries sq ON u.user_id = sq.user_id);
SELECT search_date, COUNT(query_id) AS total_searches
FROM search_queries
GROUP BY search_date;
YAML
DTO
IoC
Micro
Docker
## 2026/03/03
SELECT * FROM users WHERE device_type = 'mobile';
SELECT country, COUNT(user_id) AS user_count
FROM users
GROUP BY country;
SELECT COUNT(user_id) AS total_users 
FROM users;
SELECT DISTINCT query_text FROM search_queries
WHERE search_date >= '2024-01-18'
ORDER BY query_text;
SELECT w.warehouse_name,
       w.location,
       COUNT(DISTINCT e.employee_id) AS employee_count,
       COUNT(DISTINCT s.shipment_id) AS shipment_count,
       w.capacity
FROM warehouses w 
left JOIN employees e ON e.warehouse_id = w.warehouse_id
LEFT JOIN shipments s ON s.warehouse_id = w.warehouse_id
GROUP BY w.warehouse_name;
SELECT p.category, COUNT(DISTINCT p.product_id) AS product_count, ROUND(AVG(r.rating), 2) AS avg_rating FROM products p INNER JOIN reviews r ON p.product_id = r.product_id GROUP BY p.category HAVING AVG(r.rating) > 4.0 ORDER BY avg_rating DESC;
SELECT e.first_name, e.last_name, e.hire_date, w.warehouse_name, w.location AS warehouse_location FROM employees e INNER JOIN warehouses w ON e.warehouse_id = w.warehouse_id WHERE strftime('%Y', e.hire_date) = '2024' ORDER BY e.hire_date DESC;
SELECT o.order_id, CONCAT(c.first_name, ' ', c.last_name) AS customer_name, o.order_date
FROM customers c
JOIN orders o ON o.customer_id = c.customer_id
WHERE o.order_date > DATE('2024-01-15');
SELECT product_name, price, stock_quantity FROM products WHERE category = 'Electronics';
SELECT first_name, last_name, email, country FROM customers WHERE prime_member = 1;
Cons
Unique
SELECT employees.first_name, employees.last_name, warehouses.location AS warehouses_location
FROM employees
INNER JOIN warehouses ON employees.warehouse_id = warehouses.warehouse_id;
## 2026/03/02
10. What is the purpose of the Optional class?

In Java, the Optional class is used to represent a value that may or may not be present, helping to avoid null and reduce the risk of NullPointerException.
8. What is the purpose of the volatile keyword in Java?
SELECT ID
FROM COMPANY
WHERE EMPLOYEES > 10000
ORDER BY ID;
_doc_
intersection
insert
*args
[vals for val in vals]
<img width="971" height="463" alt="image" src="https://github.com/user-attachments/assets/bc188648-781d-4054-b6f1-c9bbccd0b85e" />
<img width="1146" height="524" alt="image" src="https://github.com/user-attachments/assets/7b8d43bb-cbd4-4e70-a660-3a841ef910a7" />
<img width="1062" height="274" alt="image" src="https://github.com/user-attachments/assets/77170bdb-2af9-4322-84d2-a28c57fb1251" />
<img width="1048" height="477" alt="image" src="https://github.com/user-attachments/assets/ed22370e-18cc-439c-a595-46488fbf34d8" />
<img width="976" height="367" alt="image" src="https://github.com/user-attachments/assets/6d8fabba-cab4-4c48-b5dd-53c2f3f340b8" />

<img width="983" height="606" alt="image" src="https://github.com/user-attachments/assets/73b79923-23e3-43a0-a7a2-97b15731e55e" />
<img width="1009" height="496" alt="image" src="https://github.com/user-attachments/assets/4caf44e3-d4da-40f8-a0ab-1d7258a21852" />
<img width="964" height="405" alt="image" src="https://github.com/user-attachments/assets/3c71aa35-3cee-4607-b231-95b8053a8fa2" />
<img width="1018" height="506" alt="image" src="https://github.com/user-attachments/assets/5acb7519-a3f7-4b9f-b4bf-86cd5f8c9209" />
<img width="1049" height="528" alt="image" src="https://github.com/user-attachments/assets/83123286-2762-45fd-8f35-135b8f4a76fd" />
<img width="1042" height="528" alt="image" src="https://github.com/user-attachments/assets/051a06ee-b63a-4880-9be5-4fc843a0b1f9" />
