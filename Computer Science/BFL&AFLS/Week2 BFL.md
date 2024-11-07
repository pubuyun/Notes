```
DECLARE num1 : INTEGER
DECLARE num2 : INTEGER

OUTPUT "Enter number 1"
INPUT num1
OUTPUT "Enter number 2"
INPUT num2

OUTPUT "DIV result: ", num1 DIV num2, "\nMOD result: ", num1 MOD num2
```

```
num1 = int(input("Input number 1: "))
num2 = int(input("Input number 2: "))
print("Div result:", num1//num2, ", Mod result:", num1%num2)
```

```
DECLARE num1:REAL
DECLARE num2:REAL
DECLARE num3:REAL

OUTPUT "Enter number 1:"
INPUT num1
OUTPUT "Enter number 2:"
INPUT num2
OUTPUT "Enter number 3:"
INPUT num3
  
IF num3-num2>0 AND num3-num1>0 THEN
    OUTPUT "Number 3 is the biggest"
ENDIF

IF num2-num1>0 AND num2-num3>0 THEN
    OUTPUT "Number 2 is the biggest"
ENDIF

IF num1-num2>0 AND num1-num3>0 THEN
    OUTPUT "Number 1 is the biggest"
ENDIF
```

```
DECLARE KeyPressed:CHAR
DECLARE Xpos:INTEGER
DECLARE Ypos:INTEGER

Xpos <- 0
Ypos <- 0

OUTPUT "Press a key"
INPUT KeyPressed

CASE OF KeyPressed
    'W' : Ypos <- Ypos - 1
    'A' : Xpos <- Xpos - 1
    'S' : Ypos <- Ypos + 1
    'D' : Xpos <- Xpos + 1
    OTHERWISE: OUTPUT "Invalid key"
ENDCASE

OUTPUT Xpos, Ypos
```

```
DECLARE Color:STRING

OUTPUT "INPUT a color:"
INPUT Color

CASE OF Color 
    "blue" : OUTPUT "water"
    "yellow" : OUTPUT "metal"
    "green" : OUTPUT "wood"
    "red" : OUTPUT "fire"
ENDCASE
```

```
DECLARE Sum:REAL
DECLARE Score:REAL
DECLARE Average:REAL
DECLARE i:INTEGER

Sum <- 0
FOR i <- 1 TO 8
    OUTPUT "Input the score of subject", i
    INPUT Score
    Sum <- Sum + Score
NEXT i
Average <- Sum/8
OUTPUT "Your average score is ", Average
```

```
DECLARE Password:STRING
CONSTANT PASSWORD = "jd8UpP2+d"

REPEAT
    INPUT Password
UNTIL Password = PASSWORD

OUTPUT "Correct Password"
```

```
DECLARE Guess:INTEGER
CONSTANT Secret = 18

REPEAT
    OUTPUT "Guess a number:"
    INPUT Guess
    IF Secret < Guess THEN
        OUTPUT "Bigger than secret"
    ENDIF
    IF Secret > Guess THEN
        OUTPUT "Smaller than secret"
    ENDIF
UNTIL Guess = Secret
OUTPUT "Correct"
```

``` 
DECLARE Ans:STRING
REPEAT 
    OUTPUT "Do you want to stop?"
    INPUT Ans
UNTIL Ans = "Yes"
```

```
DECLARE Num:REAL
DECLARE Total:REAL

Total <- 0
REPEAT
    INPUT Num
    Total <- Total + Num
UNTIL Num = -1
Total <- Total - Num
OUTPUT Total
```