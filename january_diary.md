# Computer Science
## 2026/01/23

textLabel.setText("Errors: " + errorCount + "   Pairs: " + pairCount);

## 2026/01/22
SELECT city, company_name, contact_name, "customers" AS relationship FROM customers
union
SELECT city, company_name, contact_name, "suppliers" FROM suppliers;
SELECT ROUND(AVG(unit_price),2), SUM(units_in_stock), sum(discontinued) FROM products;

SELECT category_name, round(AVG(unit_price),2) FROM categories
LEFT JOIN products ON categories.category_id = products.category_id
group by products.category_id;

SELECT year(order_date), month(order_date), COUNT(*) FROM orders
group by year(order_date), month(order_date);

SELECT p.product_name, s.company_name, c.category_name FROM products p
JOIN suppliers s on p.supplier_id = s.supplier_id
JOIN categories c ON p.category_id = c.category_id;
SELECT city, company_name, contact_name FROM customers 
WHERE city like "%l%" order by contact_name;

SELECT company_name, contact_name, fax FROM customers 
WHERE fax IS NOT null;

SELECT first_name, last_name, hire_date FROM employees 
order by hire_date DESC liMIT 1;
SELECT employee_id, order_id, customer_id, required_date, shipped_date FROM orders 
WHERE shipped_date > required_date;

SELECT order_id FROM orders 
WHERE MOD(order_id, 2) == 0;

SELECT city, company_name, contact_name FROM customers 
WHERE city like "%l%" order by contact_name;
SELECT category_name, description FROM categories 
order by category_name;

SELECT contact_name, address, city FROM customers 
WHERE country NOT IN ("Germany", "Mexico", "Spain");

SELECT order_date, shipped_date, customer_id, freight FROM orders 
WHERE order_date = "2018-02-26";
SELECT company_name, contact_name, fax FROM customers 
WHERE fax IS NOT null;

SELECT first_name, last_name, hire_date FROM employees 
order by hire_date DESC liMIT 1;

SELECT ROUND(AVG(unit_price),2), SUM(units_in_stock), sum(discontinued) FROM products;
SELECT employee_id, order_id, customer_id, required_date, shipped_date FROM orders 
WHERE shipped_date > required_date;

SELECT order_id FROM orders 
WHERE MOD(order_id, 2) == 0;

SELECT city, company_name, contact_name FROM customers 
WHERE city like "%l%" order by contact_name;
SELECT category_name, description FROM categories 
order by category_name;

SELECT contact_name, address, city FROM customers 
WHERE country NOT IN ("Germany", "Mexico", "Spain");

SELECT order_date, shipped_date, customer_id, freight FROM orders 
WHERE order_date = "2018-02-26";
Finished
  restartButton.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                if (!gameReady) {
                    return;
                }

                gameReady = false;

                card1Selected = null;
                card2Selected = null;
                shuffleCards();
                for (JButton jButton : board) {
                    jButton.setIcon(cardBackImageIcon);
                }

                errorCount = 0;
                textLabel.setText("Errors: " + Integer.toString(errorCount));
                hideCardTimer.start();
            }
  if (gameReady && card1Selected != null && card2Selected != null) {
            card1Selected.setIcon(cardBackImageIcon);
            card1Selected = null;
            card2Selected.setIcon(cardBackImageIcon);
            card2Selected = null;
        } else {

            for (JButton jButton : board) {
                jButton.setIcon(cardBackImageIcon);
            }
            gameReady = true;
        }
tile.addActionListener(new ActionListener() {
                @Override
                public void actionPerformed(ActionEvent e) {
                    if (!gameReady) {
                        return;
                    }
                    JButton tile = (JButton) e.getSource();
                    if (tile.getIcon() == cardBackImageIcon) {
                        if (card1Selected == null) {
                            card1Selected = tile;
                            int index = board.indexOf(card1Selected);
                            card1Selected.setIcon(cardSet.get(index).cardImageIcon);
                        }
                        else if (card2Selected == null) {
                            card2Selected = tile;
                            int index = board.indexOf(card2Selected);
                            card2Selected.setIcon(cardSet.get(index).cardImageIcon);
                        }
                    }
                }
## 2026/01/21
SELECT doctor_id, concat(first_name," ", last_name)	, MIN(admission_date), max(admission_date) FROM doctors
LEFT JOIN admissions ON doctor_id = attending_doctor_id
group by doctor_id;   

SELECT
  province_name,
  COUNT(*) as patient_count
FROM patients pa
  join province_names pr on pr.province_id = pa.province_id
group by pr.province_id
order by patient_count desc;
SELECT patient_id, attending_doctor_id, diagnosis FROM admissions
where (MOD(patient_id, 2) = 1 AND attending_doctor_id IN (1,5,19)) 
OR (attending_doctor_id LIKE "%2%" AND len(patient_id) = 3) ;   

SELECT first_name, last_name, COUNT(*) AS admissions_total FROM doctors
LEFT JOIN admissions ON doctor_id = attending_doctor_id
group by doctor_id; 
SELECT MAX(weight) - MIN(weight) AS weight_delta FROM patients
where last_name = "Maroni";

SELECT * FROM admissions
where patient_id = 542
ORDER BY admission_date DESC LIMIT 1;


SELECT DAY(admission_date), COUNT(*) FROM admissions
group by day(admission_date) order by COUNT(*) DESC;
SELECT first_name, last_name, birth_date FROM patients
WHERE year(birth_date) between 1970 AND 1979
order by birth_date asc;

SELECT concat(upper(last_name), ",", lower(first_name)) FROM patients
order by first_name desc;

SELECT province_id, SUM(height) AS sum_height FROM patients
group by province_id
having SUM(height) >= 7000;
SELECT patient_id, first_name FROM patients 
WHERE 
	len(first_name) >= 6 
	AND first_name LIKE "s%s";

SELECT patients.patient_id, first_name, last_name FROM patients 
LEFT JOIN admissions on patients.patient_id = admissions.patient_id
where diagnosis = "Dementia";

SELECT first_name FROM patients 
order by LEN(first_name) , first_name ASC;
SELECT 
  (SELECT count(*) FROM patients WHERE gender='M') AS male_count, 
  (SELECT count(*) FROM patients WHERE gender='F') AS female_count;

SELECT first_name, last_name, allergies FROM patients
WHERE allergies = "Penicillin" or allergies = "Morphine"
order by allergies asc, first_name, last_name;

SELECT patient_id, diagnosis FROM admissions
group by patient_id, diagnosis
having COUNT(*) > 1 ;
SELECT city, count(*) AS num_patients FROM patients
group by city
order by num_patients desc,
city asc;

SELECT first_name, last_name, "Patient" AS role FROM patients
union ALL
select first_name, last_name, "Doctor" FROM doctors;

SELECT allergies, COUNT(*) AS total_diagnosis FROM patients
group by allergies
HAVING allergies IS NOT null
order by total_diagnosis DESC;
## 2026/01/20

SELECT first_name
FROM patients group by first_name
having count(first_name) = 1;
SELECT DISTINCT YEAR(birth_date)
FROM patients order by birth_date ASC;

SELECT distinct city
FROM patients WHERE province_id = "NS";

SELECT first_name, last_name, birth_date
FROM patients WHERE height > 160 AND weight > 70;

SELECT first_name, last_name, allergies
FROM patients where allergies IS not NULL AND city = "Hamilton";

SELECT first_name, last_name, gender FROM patients WHERE gender = "M";

SELECT first_name, last_name FROM patients WHERE allergies IS null;

SELECT first_name FROM patients WHERE first_name like "C%";

SELECT first_name, last_name FROM patients WHERE weight between 100 and 120;

SELECT CONCAT(first_name ," ", last_name) AS full_name 
FROM patients;

SELECT patients.first_name, patients.last_name, province_names.province_name 
FROM patients
LEFT JOIN province_names 
ON patients.province_id = province_names.province_id;

SELECT COUNT(*)
FROM patients
WHERE birth_date like "2010%";

SELECT first_name, last_name , height
FROM patients
WHERE height = (
select MAX(height) from patients
);

SELECT *
FROM patients
WHERE patient_id IN (1, 45, 534, 879, 1000);

SELECT count(*)
FROM admissions;

SELECT *
FROM admissions WHERE admission_date = discharge_date;

SELECT patient_id, count(admission_date)
FROM admissions WHERE patient_id = 579;

## 2026/01/19
SELECT MAX(years_employed) FROM employees;
SELECT role, AVG(years_employed) FROM employees GROUP BY role;
SELECT building, SUM(years_employed) FROM employees GROUP BY building;

SELECT COUNT(*) FROM employees WHERE role = "Artist";
SELECT role, COUNT(*) FROM employees GROUP BY ROLE;
SELECT SUM(years_employed) FROM employees GROUP BY role HAVING role = "Engineer";

SELECT director, COUNT(title) FROM movies GROUP BY director;
SELECT director, SUM(domestic_sales + international_sales) FROM movies LEFT JOIN boxoffice ON id = movie_id GROUP BY director;

SELECT teacher_id, COUNT(DISTINCT subject_id) AS cnt
FROM teacher
GROUP BY teacher_id;

SELECT person.firstName, person.lastName, address.city, address.state
FROM person
LEFT JOIN address ON person.personId = address.personId;

SELECT user_id, COUNT(follower_id) AS followers_count
FROM followers GROUP BY user_id ORDER BY user_id ASC;

## 2026/01/16
Aunerisma 

## 2026/01/15
    void hideCards() {
        for (JButton jButton : board) {
            jButton.setIcon(cardBackImageIcon);
        }
        gameReady = true;
    }
 for (int i =0; i < cardSet.size(); i++){
            JButton tile = new JButton();
            tile.setPreferredSize(new Dimension(cardWidth, cardHeight));
            tile.setOpaque(true);
            tile.setIcon(cardSet.get(i).cardImageIcon);
            tile.setFocusable(false);
            board.add(tile);
            boardPanel.add(tile);
        }
     restartButton.setFont(new Font("Arial", Font.PLAIN, 16));
        restartButton.setText("Restart Game");
        restartButton.setPreferredSize(new Dimension(boardWidth, 30));
        restartButton.setFocusable(false);
        restartGamePanel.add(restartButton);
        frame.add(restartGamePanel, BorderLayout.SOUTH);

## 2026/01/14

   frame.setLayout(new BorderLayout());
        frame.setSize(boardWidth, boardHeight);
        frame.setLocationRelativeTo(null);
        frame.setResizable(false);
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);

        textLabel.setFont(new Font("Arial", Font.PLAIN, 20));
        textLabel.setHorizontalAlignment(JLabel.CENTER);
        textLabel.setText("Errors: " + Integer.toString(errorCount));

        textPanel.setPreferredSize(new Dimension(boardWidth, 30));
        textPanel.add(textLabel);
        frame.add(textPanel, BorderLayout.NORTH);
        frame.pack();
        frame.setVisible(true);

    void shuffleCards() {
        System.out.println(cardSet);
        //shuffle
        for (int i = 0; i < cardSet.size(); i++){
            int j = (int) (Math.random() * cardSet.size());
            Card temp = cardSet.get(i);
            cardSet.set(i, cardSet.get(j));
            cardSet.set(j, temp);

        }
    }

    void setupCards() {
        cardSet = new ArrayList<Card>();
        for(String cardName : cardList) {
            Image cardImg = new ImageIcon(getClass().getResource("./img/" + cardName + ".jpg")).getImage();
            ImageIcon cardImageIcon = new ImageIcon(cardImg.getScaledInstance(cardWidth, cardHeight, Image.SCALE_SMOOTH));

            Card card = new Card(cardName, cardImageIcon);
            cardSet.add(card);
        }

        cardSet.addAll(cardSet);

        Image cardBackImage = new ImageIcon(getClass().getResource("./img/back.jpg")).getImage();
        cardBackImageIcon = new ImageIcon(cardBackImage.getScaledInstance(cardWidth, cardHeight, Image.SCALE_SMOOTH));
    }

    void shuffleCards() {
        System.out.println(cardSet);
    }
    void setupCards() {
        cardSet = new ArrayList<Card>();
        for(String cardName : cardList) {
            Image cardImg = new ImageIcon(getClass().getResource("./img/" + cardName + ".jpg")).getImage();
            ImageIcon cardImageIcon = new ImageIcon(cardImg.getScaledInstance(cardWidth, cardHeight, Image.SCALE_SMOOTH));

            Card card = new Card(cardName, cardImageIcon);
            cardSet.add(card);
        }

        cardSet.addAll(cardSet);

        Image cardBackImage = new ImageIcon(getClass().getResource("./img/back.jpg")).getImage();
        cardBackImageIcon = new ImageIcon(cardBackImage.getScaledInstance(cardWidth, cardHeight, Image.SCALE_SMOOTH));
        
    }
## 2026/01/13

SELECT movies.title, domestic_sales, international_sales FROM boxoffice
INNER JOIN movies ON movies.id = boxoffice.movie_id;
SELECT movies.title, domestic_sales, international_sales FROM boxoffice
INNER JOIN movies ON movies.id = boxoffice.movie_id WHERE international_sales > domestic_sales;
SELECT movies.title, rating FROM boxoffice
INNER JOIN movies ON movies.id = boxoffice.movie_id 
ORDER BY rating DESC;

SELECT DISTINCT building_name FROM buildings LEFT JOIN employees ON building_name = building WHERE role NOT NULL;
SELECT DISTINCT building_name ,capacity FROM buildings LEFT JOIN employees ON building_name = building;
SELECT DISTINCT building_name, role FROM buildings LEFT JOIN employees ON building_name = building;

SELECT name, role FROM employees WHERE building IS NULL;
SELECT building_name FROM buildings LEFT JOIN employees ON building = building_name WHERE role IS NULL;

SELECT title, (domestic_sales + international_sales) / 1000000 AS total_sales_inM FROM movies LEFT JOIN boxoffice ON id = movie_id ;
SELECT title, rating/10 * 100 FROM movies LEFT JOIN boxoffice ON id = movie_id ;
SELECT title, rating * 10 AS rating_percent
FROM movies
  JOIN boxoffice
    ON movies.id = boxoffice.movie_id;
SELECT title, year
FROM movies
WHERE year % 2 = 0;

import java.awt.*;
import java.awt.event.*;
import java.util.ArrayList;
import javax.swing.*;

public class MatchCards {

    class Card {
        String cardName;
        ImageIcon cardImageIcon;

        public Card(String cardName, ImageIcon cardImageIcon) {
            this.cardName = cardName;
            this.cardImageIcon = cardImageIcon;
        }

        public String toString() {
            return cardName;
        }
    }

    String[] cardList = { //track cardNames
            "darkness",
            "double",
            "fairy",
            "fighting",
            "fire",
            "grass",
            "lightning",
            "metal",
            "psychic",
            "water"
    };


    int rows = 4;
    int columns = 5;
    int cardWidth = 90;
    int cardHeight = 128;

    ArrayList<Card> cardSet;
    ImageIcon cardBackImageIcon;

    MatchCards() {
        setupCards();
        //shuffleCards();
    }

    void setupCards() {
        cardSet = new ArrayList<Card>();
        for(String cardName : cardList) {
            Image cardImg = new ImageIcon(getClass().getResource("./img/" + cardName + ".jpg")).getImage();
        }

    }
}
