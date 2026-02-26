# Computer Science
## 2026/02/26
SELECT name, category, price FROM product
WHERE category = 'pants' AND (price <= 10 OR price >= 40);
SELECT title, genre FROM book WHERE pub_year = 1998 AND LENGTH(title) = 5;
## 2026/02/25
UNIQUE CHECK(years < 18) AUTO INCREMENT
ALTER table
INSERT INTO VALUES()
DELETE FROM 
INNER JOIN LEFT JOIN RIGHT JOIN FULL JOIN SEL JOIN 
UNION UNION ALL
ddl, dml, tcl, dcl
ROLLBACK COMMIT SAVEPOINT
GRANT REVOKE
comparator
## 2026/02/24
  List<Integer> numbers = Arrays.asList(1, 2, 3, 4, 5);

        List<Integer> result = numbers.stream()
                .map(n -> n * n)
                .toList();
An example of an abstract class in the JDK is AbstractMap, which is part of the Collections Framework. Its subclasses (which include HashMap, TreeMap, and ConcurrentHashMap) share many methods (including get, put, isEmpty, containsKey, and containsValue) that AbstractMap defines.

An example of a class in the JDK that implements several interfaces is HashMap, which implements the interfaces Serializable, Cloneable, and Map<K, V>. By reading this list of interfaces, you can infer that an instance of HashMap (regardless of the developer or company who implemented the class) can be cloned, is serializable (which means that it can be converted into a byte stream; see the section Serializable Objects), and has the functionality of a map. In addition, the Map<K, V> interface has been enhanced with many default methods such as merge and forEach that older classes that have implemented this interface do not have to define.
ith interfaces, all fields are automatically public, static, and final,
<img width="705" height="348" alt="image" src="https://github.com/user-attachments/assets/b73db63a-8173-48ec-8250-652e3894b005" />

Java Development Kit, or JDK, is a software development kit that is a superset of JRE. It is the foundational component that enables Java application and Java applet development. It is platform-specific, so separate installers are needed for each operating system (for example, Mac, Unix, and Windows).

The role of JDK in Java
JDK contains all the tools that are required to compile, debug, and run a program developed using the Java platform. (It’s worth noting that Java programs can also be run by using command line.)
Java Runtime Environment, or JRE, is a set of software tools responsible for execution of the Java program or application on your system.

JRE uses heap space for dynamic memory allocation for Java objects. JRE is also used in JDB (Java Debugging).
JVM components
JVM consists of three main components or subsystems:

Class Loader Subsystem is responsible for loading, linking, and initializing a Java class file (that is, “Java file”), otherwise known as dynamic class loading.
Runtime Data Areas contain method areas, PC registers, stack areas, and threads.
Execution Engine contains an interpreter, compiler, and garbage collection area.
A test case defines the fixture to run multiple tests. Some of the important methods of TestCase class are as follows −


import org.junit.runner.JUnitCore;
import org.junit.runner.Result;
import org.junit.runner.notification.Failure;

public class TestRunner1 {
   public static void main(String[] args) {
      Result result = JUnitCore.runClasses(TestJunit1.class);
		
      for (Failure failure : result.getFailures()) {
         System.out.println(failure.toString());
      }
		
      System.out.println(result.wasSuccessful());
   }
}  	
Choose your own adventure! Here, we will look at three ways to run JUnits:

Straight from the command line
From the IDE (Eclipse and IntelliJ)
Using build systems (Maven and Gradle)

The expected outcome, which the test author defines.
The actual output, which is the return value of the method being called
The delta, which allows for an acceptable deviation between the expected and actual values. This delta is specific to the fact that we’re validating the value of a double type.
The JUnit assertion methods, which are included in the org.junit.jupiter.api.Assertions class in JUnit 5 and 6, and the org.junit.Assert class in JUnit 4, are commonly used to determine the pass/fail status of test cases. 
Capture the Output of the Method Under Test
In Part 8, if the method under test returns a value, it should be captured in a variable so that its value can be asserted on.
he "When" Section & How to Invoke the Method Under Test
In Part 7, the When section of the test includes initializing variables that need to be passed when calling the method being tested and then calling the test method (part 8). The variables should be given meaningful values that cause the test to exercise the parts of the test method that we care about
The "Given" Section & How to Set Up a Test
In Part 6, the Given section of the test, we construct a new instance of the class under test and initialize it as appropriate. 
Test Method Naming in JUnit
For Part 5, again, note the naming convention testMethodName, where methodName is the name of the method being tested in the class under test. 
There are many other annotations, but some of the most common for JUnit 5 and 6 are the following.

@BeforeEach identifies a method that should be run before each test method in the class. It’s typically used to update or reset the state needed for the test methods to run properly.
@AfterEach identifies a method that should be run after each test method in the class. It can be used to reset variables, delete temporary files, and so on.
@Disabled specifies that a test method should not be run.
@BeforeAll identifies a method that should be run once before any test methods are run.
@AfterAll identifies a method that should be run once after all test methods are run.
JUnit Annotations & How They’re Used
In Part 4, we see our first JUnit-specific syntax: the @Test annotation. Annotations are extremely important when creating JUnits. This is how the JUnit framework identifies the important parts of the unit test.
How to Define a JUnit Test Class
Part 3 defines the start of our test class. The important thing to take note of here is the naming convention used for the class, which is ClassNameTest.
Imports & Dependencies in JUnit
## 2026/02/19
List comprehension is a concise and powerful way to create new lists by applying an expression to each item in an existing iterable (like a list, tuple or range). It helps you write clean, readable and efficient code compared to traditional loops.


In Python, decorators are flexible way to modify or extend behavior of functions or methods, without changing their actual code.

A decorator is essentially a function that takes another function as an argument and returns a new function with enhanced functionality.
Decorators are often used in scenarios such as logging, authentication and memorization, allowing us to add additional functionality to existing functions or methods in a clean, reusable way.
mutable, imuttalbe, reference valor ADD() DATE() yield match generator
The pass statement in Python is a placeholder that does nothing when executed.

It is used to keep code blocks valid where a statement is required but no logic is needed yet.
Examples situations where pass is used are empty functions, classes, loops or conditional blocks.
print(~(~2))
## 2026/02/18
The slice operator is a feature in programming (most notably in Python and JavaScript) used to extract a portion (or "slice") of a sequence, such as a string, list, or tuple [:]
Git is a popular version control system.

append() extend()
append() adds a single item (of any type) to the end of a list.
extend() adds all elements from an iterable (like a list, tuple, or set) to the end of the current list.
optional
buff optimize write file
streasm img, pdf, audio
readLine()
newLine()
get add remove clear 
streams reduce map filter collect 
hash set list interface hashmap treeset linkedlist
buddreded reader weirter fileoutstream instream
try resoruces 
Normalization 
drop, trucnate, delete 
## 2026/02/17

Una view es una tabla virtual basada en una consulta SELECT. No almacena datos físicamente, sino que ejecuta la consulta cada vez que se accede a ella. Se usa para seguridad, simplificación de consultas y abstracción de la base de datos.

1. Consistent Lock Ordering 
📌 1. Segunda persona con mayor salario
SELECT MAX(salary)
FROM employees
WHERE salary < (SELECT MAX(salary) FROM employees);


O usando LIMIT:

SELECT salary 
FROM employees
ORDER BY salary DESC
LIMIT 1 OFFSET 1;

📌 2. Encontrar empleados con salario mayor al promedio
SELECT *
FROM employees
WHERE salary > (SELECT AVG(salary) FROM employees);

📌 3. Encontrar duplicados en una tabla
SELECT name, COUNT(*)
FROM employees
GROUP BY name
HAVING COUNT(*) > 1;

📌 4. Diferencia entre INNER JOIN y LEFT JOIN

Pregunta típica teórica + práctica:

SELECT e.name, d.department_name
FROM employees e
LEFT JOIN departments d
ON e.dept_id = d.id;
*args tuple *kids[0]
**kwargs keyword arguments 
ANY ALL
iterator
Thread run Runnable
java 8 
try except
## 2026/02/16
 SELECT salesman_id AS 'ID', name AS 'name', city, 'Salesman' AS 'Type' FROM Salesman WHERE city = 'London'
UNION
SELECT customer_id, cust_name , city, 'Customer' FROM Customer WHERE city = 'London';

SELECT 'Customer' AS Type, ContactName, City, Country
FROM Customers
UNION
SELECT 'Supplier', ContactName, City, Country
FROM Suppliers;
SQL UNION Operator

junit
wrapper autobux unbox
array list / array 

poly abs encap inher
final finally finalize 
As the opposite, unchecked exceptions aren’t checked at the compile time. 

The most common unchecked exceptions are: ArrayIndexOutOfBoundsException, IllegalArgumentException, NullPointerException. 

Unchecked exceptions are thrown during runtime. The following code will throw a NullPointerException. Probably it’s one of the most common exceptions in Java.


**Collections Primitive**

4.1. Checked and Unchecked Exceptions
A checked exception means that it’s checked at the compile time. Note, that we must handle this exception. Otherwise, a method must specify an exception by using throws keyword.

The most common checked exceptions are IOException, FileNotFoundException, ParseException. FileNotFoundException may be thrown when we create FileInputStream from File. 

== equal
abstract extend one interface implement many 
String[] args
public static void
JDK development KIT -> JRE Java Runtime Environment -> JVM Java Virtual Machine
try - catch throw throws

## 2026/02/13
SELECT products.product_name, products.price FROM products ORDER BY products.price DESC;

## 2026/02/12
SELECT s.first_name, s.last_name, c.course_name, e.grade FROM students s INNER JOIN enrollments e ON s.student_id = e.student_id
INNER JOIN courses c ON c.course_id = e.course_id;
SELECT first_name, last_name, email, major FROM students WHERE email LIKE '%university.edu';
SELECT first_name, last_name, hire_date FROM professors WHERE department = 'Computer Science';
SELECT first_name, last_name, enrollment_date FROM students WHERE enrollment_date > '2022-12-31';
SELECT AVG(credits) AS 'average_credits' FROM courses;
SELECT first_name, last_name, major FROM students WHERE graduation_year = 2026;
SELECT COUNT(*) AS 'total_courses' FROM courses;
## 2026/02/11
SELECT * FROM students;
SELECT first_name, last_name, graduation_year FROM students WHERE major = 'Computer Science';
SELECT courses.course_name, courses.credits FROM courses ORDER BY credits DESC;
## 2026/02/10
SELECT departments.department_name, COUNT(employees.employee_id) AS 'employee_count' FROM departments
LEFT JOIN employees ON departments.department_id = employees.department_id
GROUP BY departments.department_name;
Electro
SELECT employee_id AS 'Employee Number', CONCAT(first_name, ' ', last_name) AS 'Full Name', salary AS 'Annual Salary', hire_date AS 'Start Date' FROM employees;
SELECT employees.first_name, employees.last_name, departments.department_name 
FROM employees
INNER JOIN departments ON departments.department_id = employees.department_id;
## 2026/02/09
SELECT 
      departments.department_name, departments.location, employees.first_name, employees.last_name
FROM departments
LEFT JOIN employees ON departments.department_id = employees.department_id
ORDER BY departments.department_name, employees.first_name;
SELECT first_name, last_name, salary FROM employees WHERE salary BETWEEN 60000 AND 90000;
SELECT first_name, last_name, department_id FROM employees WHERE department_id IN (10, 20);
SELECT first_name, last_name FROM employees WHERE first_name LIKE 'a%';
SELECT AVG(salary) AS average_salary FROM employees;
SELECT AVG(salary) FROM employees;
SELECT SUM(salary) AS total_salary FROM employees;
SELECT COUNT(*) AS total_employees FROM employees;
SELECT first_name, last_name, salary FROM employees ORDER BY salary DESC LIMIT 3;
SELECT first_name, last_name, manager_id FROM employees WHERE manager_id IS NULL;
SELECT first_name, last_name, department_id FROM employees WHERE department_id != 10;
SELECT first_name, last_name, department_id FROM employees WHERE department_id = 10 OR department_id = 40;
SELECT first_name, last_name, salary FROM employees ORDER BY salary DESC;
SELECT first_name, last_name, salary FROM employees WHERE salary > 80000;
SELECT * FROM employees;
SELECT * FROM city WHERE population > 100000 AND countrycode = 'USA';
SELECT department_name FROM departments;
## 2026/02/06
import org.junit.jupiter.api.Test;
import static org.junit.jupiter.api.Assertions.*;

class MainTest {

    @Test
    void testExample() {
        assertEquals(4, 2 + 2);
    }
}
        if (!file.exists()) {
            highScore = 0;
            return;
        }

        try (BufferedReader br = new BufferedReader(new FileReader(file))) {
            String line = br.readLine();
            if (line != null && !line.isEmpty()) {
                highScore = Integer.parseInt(line);
            }
        } catch (IOException | NumberFormatException e) {
            highScore = 0;
        }

    }
## 2026/02/05
 void placeHighScore() {

        try {
            BufferedReader br = new BufferedReader(new FileReader("highscore.txt"));
            String line = br.readLine();
            br.close();

            if (line != null) {
                highScore = Integer.parseInt(line);
            }

        } catch (IOException e) {
            e.printStackTrace();
        }

    }

## 2026/02/04

if(turnPlayerOne){
            playerOneTimer.stop();
        } else {
            playerTwoTimer.stop();
        }

        errorCount = 0;
        pairCount = 0;
        playerOneScore = 0;
        playerTwoScore = 0;

        secCounter = 0;
        playerOneTime = 0;
        playerTwoTime = 0;

SELECT employees.name, departments.name FROM employees INNER JOIN departments ON employees.department_id = departments.id;
     playerOneTimer = new Timer(1000, _ -> {
            playerOneTime++;
        });


        playerTwoTimer = new Timer(1000, _ -> {
            playerTwoTime++;
        });


        totalTimer = new Timer(1000, _ ->{
            secCounter ++;

            printTimeTable();

        });
                if (turnPlayerOne) {
            playerOneTimer.stop();
            playerTwoTimer.start();
        } else {
            playerTwoTimer.stop();
            playerOneTimer.start();
        }
## 2026/02/03
-Electro
