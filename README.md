# Useful JS Snippets

Here's where I like to keep a collection of javascript snippets that I've found useful.

I try to keep names as self-explanatory as possible, but of course they can be changed

---

**1.- areEqual**

Checks if all elements of an array are equal, returns true or false

```
const areEqual = array => array.every(value => value === array.at(0));
```

**2.- Capitalize**

Capitalizes the first letter of a given string

```
const capitalizeSingle = ([firstLetter, ...restWord]) => `${firstLetter.toUpperCase()}${restWord.join('')}`
```

**3.- CapitalizeAllWords**

Capitalizes the first letter of every single words of a given string (uses a regExp to select the first letter of a word if it's lowercase, not much of a reason to change a word if it's already uppercase)

```
const capitalizeAllWords = string => string.replace(/\b[a-z]/g, letter => letter.toUpperCase());
```

**4.- HowManyTimes**

Counts the number of times a value is found in an array

```
const howManyTimes = (array, value) => array.reduce((a, v) => (v === value ? a + 1 : a), 0);
```

**5.- DaysBetween**

Returns the difference in days between two dates (both have to be Date())

```
const daysBetween = (startDate, endDate) => (endDate - startDate) / (1000 * 3600 * 24);
```
