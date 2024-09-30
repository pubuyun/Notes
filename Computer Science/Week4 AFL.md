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


PROCEDURE ProcessTests()
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
ENDPROCEDURE

PROCEDURE ProcessSubjectsData()
    // Processing Subjects 
    StuSum <- StuSum + SubSum
    IF SubHighest > StuHighest THEN 
        StuHighest <- SubHighest
    ENDIF
    IF SubLowest < StuLowest THEN
        StuLowest <- SubLowest
    ENDIF
ENDPROCEDURE

PROCEDURE ProcessClassesData()
    ClsSum <- ClsSum + StuSum
    IF StuHighest > ClsHighest THEN 
        ClsHighest <- StuHighest
    ENDIF
    IF StuLowest < ClsLowest THEN
        ClsLowest <- StuLowest
    ENDIF
ENDPROCEDURE

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
        SubSum <- 0
        SubHighest <- 0
        SubLowest <- 101

        CALL ProcessTests()
        CALL ProcessSubjectsData()

        Out <- Out & "      Subject Average:" & SubSum/TSTNUM & " Subject Highest:" & SubHighest & " Subject Lowest:" & SubLowest & "\n"
    NEXT j
    Out <- Out & "  Student Average:" & StuSum/SUBNUM/TSTNUM & " Student Highest:" & StuHighest & " Student Lowest:" & StuLowest & "\n"
    CALL ProcessClassesData()
NEXT i
Out <- Out & "Class Average:" & ClsSum/STUNUM/SUBNUM/TSTNUM & " Class Highest:" & ClsHighest & " Class Lowest:" & ClsLowest & "\n"
OUTPUT Out
```