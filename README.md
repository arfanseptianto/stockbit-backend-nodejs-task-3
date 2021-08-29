# STOCKBIT BACKEND NODE.JS TASK - 3

Please refactor the code below to make it more concise, efficient and readable with good logic flow. 

```js
function findFirstStringInBracket(str) { 
    if (str.length > 0) { 
        let indexFirstBracketFound = str.indexOf("("); 
        if (indexFirstBracketFound >= 0) { 
            let wordsAfterFirstBracket = str.substr(indexFirstBracketFound); 
            if (wordsAfterFirstBracket) { 
                wordsAfterFirstBracket = wordsAfterFirstBracket.substr(1); 
                let indexClosingBracketFound = wordsAfterFirstBracket.indexOf(")"); 
                if (indexClosingBracketFound >= 0) { 
                    return wordsAfterFirstBracket.substring(0, indexClosingBracketFound); 
                } else { 
                    return ''; 
                } 
            } else { 
                return ''; 
            } 
        } else { 
            return ''; 
        } 
    } else { 
        return ''; 
    } 
}
```

### ANSWER
```js
function findFirstStringInBracket(str) { 
    if (!str.length) 
        return ''; 

    let indexFirstBracketFound = str.indexOf("("); 
    if (indexFirstBracketFound < 0) 
        return ''; 

    let wordsAfterFirstBracket = str.substr(indexFirstBracketFound + 1); 
    if (!wordsAfterFirstBracket) 
        return ''; 

    let indexClosingBracketFound = wordsAfterFirstBracket.indexOf(")"); 
    if (indexClosingBracketFound < 0) 
        return ''; 

    return wordsAfterFirstBracket.substring(0, indexClosingBracketFound); 
}
```
