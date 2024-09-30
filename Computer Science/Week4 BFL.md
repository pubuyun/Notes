
## Extension

```
FUNCTION SUBSTRING(x : STRING, y : INTEGER, z : INTEGER) RETURNS STRING
    RETURN MID(x, y, z)
ENDFUNCTION

FUNCTION is_palindrome(str:STRING) RETURNS BOOLEAN
    DECLARE rev_str:STRING
    rev_str <- ""
    DECLARE i:INTEGER
    FOR i <- LENGTH(str) TO 1 STEP -1
        rev_str <- rev_str & SUBSTRING(str, i ,1)
    NEXT i
    IF str = rev_str THEN
        RETURN TRUE
    ELSE 
        RETURN FALSE
    ENDIF
ENDFUNCTION

FUNCTION randomint(lowest:INTEGER, highest:INTEGER) RETURNS INTEGER
    //randint from (lowest, highest]
    RETURN ((RAND(highest) MOD (highest-lowest)) + lowest)
ENDFUNCTION 

FUNCTION factorial(x : INTEGER) RETURNS INTEGER
    IF x = 0 THEN
        RETURN 1
    ENDIF
    RETURN x * factorial(x - 1)
ENDFUNCTION

FUNCTION calculator(num1:REAL, num2:REAL, operator:CHAR) RETURNS REAL
    CASE OF operator
        '+': RETURN num1 + num2
        '-': RETURN num1 - num2
        '*': RETURN num1 * num2
        '/': RETURN num1 / num2
        '%': RETURN num1 MOD num2
        OTHERWISE:  OUTPUT "Wrong operator"
                    RETURN 0
    ENDCASE
ENDFUNCTION

OUTPUT is_palindrome("acoca")
OUTPUT randomint(1000, 1001)
OUTPUT factorial(5)
OUTPUT calculator(10.1, 20.2, '*')
```

```
FUNCTION SUBSTRING(x : STRING, y : INTEGER, z : INTEGER) RETURNS STRING
    RETURN MID(x, y, z)
ENDFUNCTION

FUNCTION is_valid(str:STRING) RETURNS BOOLEAN
    DECLARE exp:BOOLEAN
    DECLARE i:INTEGER
    DECLARE has_digit:BOOLEAN
    exp <- (LENGTH(str) >= 10 AND LENGTH(str) <= 20)
    has_digit <- FALSE

    FOR i <- 1 TO LENGTH(str) 
        exp <- exp AND SUBSTRING(str, i, 1) <> " "
        has_digit <- has_digit OR IS_NUM(SUBSTRING(str, i, 1))
    NEXT i
    exp <- exp AND TO_LOWER(str) <> str
    exp <- exp AND has_digit
    RETURN exp
ENDFUNCTION

DECLARE pswd:STRING
INPUT pswd
OUTPUT is_valid(pswd)
```


## Homework
### Email
```
FUNCTION SUBSTRING(x : STRING, y : INTEGER, z : INTEGER) RETURNS STRING
    RETURN MID(x, y, z)
ENDFUNCTION

FUNCTION is_valid(str:STRING) RETURNS BOOLEAN
    DECLARE exp:BOOLEAN
    DECLARE i:INTEGER
    FOR i <- 1 TO LENGTH(str) 
        exp <- exp OR SUBSTRING(str, i, 1) = "@"
    NEXT i
    exp <- exp AND SUBSTRING(str, 1, 1) <> "@" AND SUBSTRING(str, LENGTH(str), 1) <> "@"
    RETURN exp
ENDFUNCTION

DECLARE email:STRING
REPEAT
    OUTPUT "Enter your email address" 
    INPUT email
UNTIL is_valid(email)
OUTPUT "Valid"
```

## Class Activities
### Question4
```
FUNCTION factorial(x : INTEGER) RETURNS INTEGER
    IF x = 0 THEN
        RETURN 1
    ENDIF
    RETURN x * factorial(x - 1)
ENDFUNCTION
```
### Question5
```
// Bank account simulation
DECLARE Money:REAL
DECLARE Continue:BOOLEAN
DECLARE Choice:STRING
DECLARE MoneyInput:REAL

PROCEDURE depositMoney(money:REAL)
    Money <- Money + money
ENDPROCEDURE
FUNCTION withdrawMoney(money:REAL) RETURNS REAL
    IF Money >= money THEN
        RETURN Money - money
    ELSE 
        RETURN -1
    ENDIF
ENDFUNCTION

REPEAT
    OUTPUT "deposit or withdraw?"
    INPUT Choice
    OUTPUT "How much money do you want to", Choice
    INPUT MoneyInput
    CASE OF Choice
        "deposit": CALL depositMoney(MoneyInput)
        "withdraw": IF withdrawMoney(MoneyInput)>=0 THEN
            Money <- withdrawMoney(MoneyInput)
        ELSE    
            OUTPUT "Not enough money to withdraw"
        ENDIF
    ENDCASE
    OUTPUT "Balance:", Money
    OUTPUT "Continue? (TRUE or FALSE)"
    INPUT Continue
UNTIL NOT Continue

```
### Question6
```
FUNCTION MultiplyString(str:STRING, num:INTEGER) RETURNS STRING
    DECLARE res:STRING
    DECLARE i:INTEGER
    res <- ""
    FOR i <- 1 TO num
        res <- res & str
    NEXT i
    RETURN res
ENDFUNCTION

CONSTANT EVENT_NAME = "EVENT_NAME"
CONSTANT SEAT_NUMBER = "10"
CONSTANT VIPPRICE = 100
CONSTANT REGULARPRICE = 50


PROCEDURE PrintTicket(event_name: STRING, ticket_type: STRING, seat_number: STRING)
    OUTPUT "------------------------------------------------------"
    OUTPUT "|" & MultiplyString(" ", 26 - LENGTH(event_name) DIV 2 + LENGTH(event_name) MOD 2) & event_name & MultiplyString(" ", 26 - LENGTH(event_name) DIV 2) & "|"
    OUTPUT "|                                                    |"
    OUTPUT "|                                                    |"
    OUTPUT "|" & MultiplyString(" ", 38) & ticket_type & MultiplyString(" ", 14 - LENGTH(ticket_type)) & "|"
    OUTPUT "|                                                    |"
    OUTPUT "|" & MultiplyString(" ", 38) & seat_number & MultiplyString(" ", 14 - LENGTH(seat_number)) & "|"
    OUTPUT "|                                                    |"
    OUTPUT "|                                                    |"
    OUTPUT "------------------------------------------------------"
ENDPROCEDURE

FUNCTION CalculatePrice(age:INTEGER, ticketType:STRING) RETURNS INTEGER
    DECLARE DiscountMultiplier : REAL
    IF age < 12 OR age > 60 THEN
        DiscountMultiplier <- 0.5
    ELSE
        DiscountMultiplier <- 1
    ENDIF
    CASE OF ticketType
        "VIP": RETURN VIPPRICE*DiscountMultiplier
        "Regular": RETURN REGULARPRICE*DiscountMultiplier
        OTHERWISE: OUTPUT "Wrong Type"
    ENDCASE
    RETURN -1
ENDFUNCTION

DECLARE TicketTypeInput:STRING
DECLARE Age:INTEGER

OUTPUT "What type of ticket do you want to buy(VIP, Regular)"
INPUT TicketTypeInput
OUTPUT "What is your age"
INPUT Age
OUTPUT "Price:", CalculatePrice(Age, TicketTypeInput)
IF CalculatePrice(Age, TicketTypeInput) <> -1 THEN
    CALL PrintTicket(EVENT_NAME, TicketTypeInput, SEAT_NUMBER)
ENDIF
```