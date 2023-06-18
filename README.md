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

<br>

**11. Remove duplicates from an array**

The easiest way imo to remove duplicates from an existing array is to convert it to a Set() (think of them as a type of array where each value can only occur once, even if you try to add a repeated value later) and then convert it back to array using the spread operator (...) (as the name implies, it spreads an interable into its individual elements)

```
const repeatedNumbers = [1, 1, 1, 2, 2, 3, 4, 5, 5, 6, 7, 8, 9];

const uniqueNumbers = [...new Set(repeatedNumbers)];
```

<br>

**12. Creating shallow copies of objects and arrays**

The spread operator (...) can be used to create shallow copies of an existing object or array (click [here](https://developer.mozilla.org/en-US/docs/Glossary/Shallow_copy) to read more about shallow copies)

```
const newArray = [...oldArray];

const newObject = {...oldObject};
```

<br>

**13. Convert an array to a list**

Take a given array, convert it to a list (turns the elements into li tags) and finally append them to a list
with an id

```
const arrayToList = (arr, id) =>
  (arrEl => (
    (arrEl = document.querySelector(`#${id}`)),
    (arrEl.innerHTML += arr.map(item => `<li>${item}</li>`).join(''))
  ))();
```

<br>

**14. Average**

Takes the numbers of an array and returns their average

```
const average = (...nums) => nums.reduce((acc, val) => acc + val, 0) / nums.length;
```
