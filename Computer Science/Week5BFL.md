```
CONSTANT PHRASE = "The quick brown fox jumps over the lazy dog"
DECLARE Name : STRING
 
FUNCTION FindIndex(str:STRING, target:STRING) RETURNS INTEGER
    DECLARE i:INTEGER
    DECLARE lstr:STRING
    lstr <- TO_LOWER(str)
    FOR i <- 1 TO LENGTH(lstr)
        IF MID(lstr, i, 1) = target THEN
            RETURN i
        ENDIF
    NEXT i
    RETURN -1
ENDFUNCTION

INPUT Name
Name <- TO_LOWER(Name)

DECLARE sum:INTEGER
DECLARE i:INTEGER
sum <- 0
FOR i <- 1 TO LENGTH(Name)
    OUTPUT FindIndex(PHRASE, MID(Name, i, 1))
    sum <- sum + FindIndex(PHRASE, MID(Name, i, 1))
NEXT i
OUTPUT sum
```
