# Computer Science

## 2026/02/05


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
