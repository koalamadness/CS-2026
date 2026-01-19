# Computer Science
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
