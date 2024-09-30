```
DECLARE MyName:STRING

INPUT MyName
OUTPUT "Length", LENGTH(MyName)
OUTPUT "First three character", SUBSTRING(MyName, 1, 3)
OUTPUT "Upper Case", TO_LOWER(MyName)
OUTPUT "Lower Case", TO_UPPER(MyName)
```