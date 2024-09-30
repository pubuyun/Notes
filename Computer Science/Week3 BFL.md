```
DECLARE age:INTEGER
DECLARE violations:INTEGER

OUTPUT "Enter age"
INPUT age
OUTPUT "Enter how many violations you have"
INPUT violations

IF age>=18 AND violations<=3 THEN
    OUTPUT "Eligible"
ELSE
    OUTPUT "Not Eligible"
ENDIF
```
```
DECLARE MyName:STRING
FUNCTION SUBSTRING(x : STRING, y : INTEGER, z : INTEGER) RETURNS STRING
    RETURN MID(x, y, z)
ENDFUNCTION

INPUT MyName
OUTPUT "Length", LENGTH(MyName)
OUTPUT "First three character", SUBSTRING(MyName, 1, 3)
OUTPUT "Upper Case", TO_LOWER(MyName)
OUTPUT "Lower Case", TO_UPPER(MyName)

```
```
DECLARE str:STRING
DECLARE rev_str:STRING
INPUT str
rev_str <- ""

FUNCTION SUBSTRING(x : STRING, y : INTEGER, z : INTEGER) RETURNS STRING
    RETURN MID(x, y, z)
ENDFUNCTION

DECLARE i:INTEGER
FOR i <- LENGTH(str) TO 1 STEP -1
    rev_str <- rev_str & SUBSTRING(str, i ,1)
NEXT i

OUTPUT rev_str
```
```
DECLARE Rows:INTEGER
DECLARE Cols:INTEGER
DECLARE Display:STRING
Display <- ""
OUTPUT "Enter row"
INPUT Rows

OUTPUT "Enter col"
INPUT Cols

DECLARE Index1 : INTEGER
DECLARE Index2 : INTEGER
FOR Index1 <- 1 TO Rows
    FOR Index2 <- 1 TO Index1
        Display <- Display & "*"
    NEXT Index2
    Display <- Display & "\n"
NEXT Index1
OUTPUT Display
```
```
CONSTANT STUNUM = 2
CONSTANT SUBNUM = 3
CONSTANT TSTNUM = 4

DECLARE SubHighest : INTEGER
DECLARE SubLowest : INTEGER
DECLARE SubSum : INTEGER
DECLARE StuHighest : INTEGER
DECLARE StuLowest : INTEGER
DECLARE StuSum : INTEGER
DECLARE ClsHighest : INTEGER
DECLARE ClsLowest : INTEGER
DECLARE ClsSum : INTEGER
DECLARE Score : INTEGER
DECLARE Out : STRING
Out <- ""

DECLARE i : INTEGER
DECLARE j : INTEGER
DECLARE k : INTEGER

ClsHighest <- 0
ClsLowest <- 101
ClsSum <- 0
// Students
FOR i <- 1 TO STUNUM
    StuSum <- 0
    StuHighest <- 0
    StuLowest <- 101
    Out <- Out & "Student " & i & ":\n"
    // Subjects
    FOR j <- 1 TO SUBNUM
        Out <- Out & "  Subject" & j & "\n"
        // Tests
        SubSum <- 0
        SubHighest <- 0
        SubLowest <- 101

        FOR k <- 1 TO TSTNUM
            OUTPUT "Enter Score for Student", i, "Subject", j, "Test", k
            INPUT Score

            // Processing Tests
            SubSum <- SubSum + Score
            IF Score > SubHighest THEN 
                SubHighest <- Score
            ENDIF
            IF Score < SubLowest THEN
                SubLowest <- Score
            ENDIF

        NEXT k
        Out <- Out & "      Subject Average:" & SubSum/TSTNUM & " Subject Highest:" & SubHighest & " Subject Lowest:" & SubLowest & "\n"
        // Processing Subjects 
        StuSum <- StuSum + SubSum
        IF SubHighest > StuHighest THEN 
            StuHighest <- SubHighest
        ENDIF
        IF SubLowest < StuLowest THEN
            StuLowest <- SubLowest
        ENDIF

    NEXT j
    Out <- Out & "  Student Average:" & StuSum/SUBNUM/TSTNUM & " Student Highest:" & StuHighest & " Student Lowest:" & StuLowest & "\n"
    ClsSum <- ClsSum + StuSum
    IF StuHighest > ClsHighest THEN 
        ClsHighest <- StuHighest
    ENDIF
    IF StuLowest < ClsLowest THEN
        ClsLowest <- StuLowest
    ENDIF

NEXT i
Out <- Out & "Class Average:" & ClsSum/STUNUM/SUBNUM/TSTNUM & " Class Highest:" & ClsHighest & " Class Lowest:" & ClsLowest & "\n"
OUTPUT Out
```
