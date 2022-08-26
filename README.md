# Useful JS Snippets

Here's where I like to keep a collection of javascript snippets that I've found useful.

I try to keep names as self-explanatory as possible, but of course they can be changed

---

**1. areEqual**

Checks if all elements of an array are equal, returns true or false

```
const areEqual = array => array.every(value => value === array.at(0));
```

<br>

**2. capitalizeSingle**

Capitalizes the first letter of a given string

```
const capitalizeSingle = ([firstLetter, ...restWord]) => `${firstLetter.toUpperCase()}${restWord.join('')}`
```

<br>

**3. capitalizeAllWords**

Capitalizes the first letter of every single words of a given string (uses a regExp to select the first letter of a word if it's lowercase, not much of a reason to change a word if it's already uppercase)

```
const capitalizeAllWords = string => string.replace(/\b[a-z]/g, letter => letter.toUpperCase());
```

<br>

**4. howManyTimes**

Counts the number of times a value is found in an array

```
const howManyTimes = (array, value) => array.reduce((a, v) => (v === value ? a + 1 : a), 0);
```

<br>

**5. daysBetween**

Returns the difference in days between two dates (both have to be Date())

```
const daysBetween = (startDate, endDate) => (endDate - startDate) / (1000 * 3600 * 24);
```

<br>

**6. replaceAll**

Less of a snippet, more of a YSK.

Introduced with ES2021 'replaceAll()' is a method that replaces all instances of a string, it takes two arguments, a _pattern_ (a.k.a whatever you want to replace, which can be a string or a regExp [you need to include g in your regExp]) and the _replacement_ (which can be a string or a function).

```
const originalString = 'dogs, cats, dogs and mouses';

const newString = originalString.replaceAll('dogs', 'bunnies'); //bunnies, cats, bunnies and mouses
```

<br>

**7. randomFromArray**

Gets a random element from an array

```
const randomFromArray = array => array[Math.floor(Math.random() * array.length)];
```

<br>

**8. removeHTMLTags**

Removes HTML tags from a string using a regExp

```
const removeHTMLTags = string => string.replaceAll(/<[^>]*>/g, '');
```

<br>

**9. maskValue**

'masks' all except the last x characters that you specify (masks the last 4 characters and uses '\*' as the mask by default, but you can change it)

```
const maskValue = (value, number = 4, mask = '*') => `${value}`.slice(-number).padStart(`${value}`.length, mask);

maskValue(123456789, 3, '#'); //######789
```

<br>

**10. currentURL**

Returns the current URL

```
const currentURL = () => window.location.href;
```
