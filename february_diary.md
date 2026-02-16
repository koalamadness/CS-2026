# Computer Science

## 2026/02/16
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
