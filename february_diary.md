# Computer Science
## 2026/02/09

SELECT * FROM city WHERE population > 100000 AND countrycode = 'USA';
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
