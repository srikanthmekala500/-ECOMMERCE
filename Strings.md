## Length of a String
```JavaScript
let firstName = "Vaishali";
console.log(firstName.length);
```
## Access String Element
```JavaScript
console.log(firstName.charAt(2)); // i
console.log(firstName[2]); // i
console.log(firstName.charCodeAt(2)); // 115 (Ascii Code)
```
## Check Presence of Character
```JavaScript
console.log(firstName.includes("r")); // false (& if present it return true)
console.log(firstName.indexOf("i")); // 2 (& if not present it return -1)
console.log(firstName.lastIndexOf("i")); // 7 
```
## Compare Two Strings
```JavaScript
let anotherName = "Vishal";
console.log(firstName.localeCompare(anotherName)); // -1 (& if strings are equal it return 0)
```
## Replace Substring
```JavaScript
const str = "Vishal is Best Frontend Developer. Vishal is Best Developer. ";
console.log(str.replace("Vishal", "Sujit")); // "Sujit is Best Frontend Developer. Vishal is Best Developer. "
console.log(str.replaceAll("Vishal", "Sujit")); // "Sujit is Best Frontend Developer. Sujit is Best Developer. "
```
## Substring of a String
```JavaScript
console.log(str.substring(6, 30)); 
console.log(str.slice(-10, -1));
```
## Split and Join
```JavaScript
console.log(str.split(""));
const subString = str.split(" ");
console.log(subString.join(" "));
```
## String Start and End
```JavaScript
console.log(str.startsWith("Vishal")); // true
console.log(str.endsWith("Developer")); // true
```
## Trim and Case Conversion
```JavaScript
const trimStr = str.trim();
const trimStrStart = str.trimStart();
const trimStrEnd = str.trimEnd();
console.log(trimStr, trimStr.length);
console.log(str.toLowerCase());
console.log(str.toUpperCase());
```
## Convert Number and Object to String
```JavaScript

const num = 123;
console.log(num, num.toString());

const obj = {
    name: "Vishal",
    course: "DSA with Vishal"
};
console.log(obj, JSON.stringify(obj));
```
## Concatenate Strings
```JavaScript
const lastName = "Rajput";
console.log(firstName + lastName);
console.log(`${firstName} ${lastName} is a Best Developer`);
console.log(firstName.concat(lastName, " is a", " Best"));
```
## Find the Index of the First Occurrence in a String
```JavaScript
 function findFirstOccurrence(mainString, subString) {
  return mainString.indexOf(subString);
}

console.log(findFirstOccurrence('hello world', 'world')); // Outputs: 6
console.log(findFirstOccurrence('hello world', 'foo'));   // Outputs: -1

```
## Reverse String
```JavaScript
function reverseString(str) {
  return str.split('').reverse().join('');
}

console.log(reverseString('hello')); // Outputs: 'olleh'
```
## Valid Anagram
```JavaScript
// To determine if two strings are valid anagrams of each other in JavaScript, you can follow these steps:

// Check if the strings have the same length. If they don’t, they can’t be anagrams.
// Sort the characters in both strings and then compare the sorted versions.
function areAnagrams(str1, str2) {
  // If lengths are different, they cannot be anagrams
  if (str1.length !== str2.length) {
    return false;
  }

  // Convert strings to arrays, sort them, and join them back to strings
  const sortedStr1 = str1.split('').sort().join('');
  const sortedStr2 = str2.split('').sort().join('');

  // Compare sorted versions
  return sortedStr1 === sortedStr2;
}

console.log(areAnagrams('listen', 'silent')); // Outputs: true
console.log(areAnagrams('hello', 'world'));   // Outputs: false
```
## Longest Common Prefix
```JavaScript
Check if the list is empty. If it is, return an empty string.
// Sort the strings. The longest common prefix of a list of strings will be common to the first and the last string in the sorted list.
// Compare characters of the first and last string to find the common prefix.
// Here’s a function to find the longest common prefix:

function longestCommonPrefix(strs) {
  if (strs.length === 0) return '';

  // Sort the strings
  strs.sort();

  // Get the first and last string after sorting
  const first = strs[0];
  const last = strs[strs.length - 1];

  // Find the common prefix between the first and last string
  let i = 0;
  while (i < first.length && i < last.length && first[i] === last[i]) {
    i++;
  }

  // Return the common prefix
  return first.substring(0, i);
}

console.log(longestCommonPrefix(['flower', 'flow', 'flight'])); // Outputs: 'fl'
console.log(longestCommonPrefix(['dog', 'racecar', 'car']));     // Outputs: ''
```
## Merge Strings Alternately
```JavaScript
function mergeAlternately(str1, str2) {
  let result = '';
  const len1 = str1.length;
  const len2 = str2.length;
  const minLen = Math.min(len1, len2);

  // Merge characters from both strings alternately
  for (let i = 0; i < minLen; i++) {
    result += str1[i] + str2[i];
  }

  // Append remaining characters from the longer string
  if (len1 > minLen) {
    result += str1.slice(minLen);
  } else if (len2 > minLen) {
    result += str2.slice(minLen);
  }

  return result;
}

console.log(mergeAlternately('abc', '12345')); // Outputs: 'a1b2c345'
console.log(mergeAlternately('hello', 'world')); // Outputs: 'hweolrllod'
```
## Length of Last Word
```JavaScript
function lengthOfLastWord(s) {
  // Trim the string to remove any leading or trailing spaces
  const trimmedString = s.trim();

  // Split the string by spaces to get an array of words
  const words = trimmedString.split(' ');

  // Get the last word from the array
  const lastWord = words[words.length - 1];

  // Return the length of the last word
  return lastWord.length;
}

console.log(lengthOfLastWord('Hello World'));   // Outputs: 5
console.log(lengthOfLastWord('   fly me   to   the moon  ')); // Outputs: 4
console.log(lengthOfLastWord('a ')); // Outputs: 1
console.log(lengthOfLastWord('')); // Outputs: 0
```
## Valid Palindrome
```JavaScript
function isPalindrome(s) {
  // Remove non-alphanumeric characters and convert to lowercase
  const cleanedString = s.replace(/[^a-zA-Z0-9]/g, '').toLowerCase();

  // Check if the cleaned string is the same forwards and backwards
  const reversedString = cleanedString.split('').reverse().join('');
  
  return cleanedString === reversedString;
}

console.log(isPalindrome('A man, a plan, a canal: Panama')); // Outputs: true
console.log(isPalindrome('race a car')); // Outputs: false
console.log(isPalindrome(' ')); // Outputs: true
```
## String Compression
```JavaScript
function compressString(s) {
  if (s.length === 0) return '';

  let compressed = '';
  let count = 1;

  for (let i = 1; i < s.length; i++) {
    if (s[i] === s[i - 1]) {
      count++;
    } else {
      compressed += s[i - 1] + count;
      count = 1;
    }
  }

  // Append the last character and its count
  compressed += s[s.length - 1] + count;

  // Return the shorter of the original or compressed string
  return compressed.length < s.length ? compressed : s;
}

console.log(compressString('aabcccccaaa')); // Outputs: 'a2b1c5a3'
console.log(compressString('abc'));          // Outputs: 'abc'
console.log(compressString('aabb'));         // Outputs: 'aabb'
```
## Reverse Words in a String
```JavaScript
function reverseWords(s) {
  // Trim the string and split it into words
  const words = s.trim().split(/\s+/);

  // Reverse the array of words
  const reversedWords = words.reverse();

  // Join the reversed array into a single string with spaces
  return reversedWords.join(' ');
}

console.log(reverseWords('  Hello World  ')); // Outputs: 'World Hello'
console.log(reverseWords('The quick brown fox')); // Outputs: 'fox brown quick The'
console.log(reverseWords('  a good example  ')); // Outputs: 'example good a'
```
## Reverse Vowels of a String
```JavaScript
function reverseVowels(s) {
  const vowels = 'aeiouAEIOU';
  const chars = s.split('');
  const vowelIndices = [];
  const vowelChars = [];

  // Collect the vowels and their indices
  for (let i = 0; i < chars.length; i++) {
    if (vowels.includes(chars[i])) {
      vowelIndices.push(i);
      vowelChars.push(chars[i]);
    }
  }

  // Reverse the collected vowels
  vowelChars.reverse();

  // Place the reversed vowels back into their original positions
  for (const index of vowelIndices) {
    chars[index] = vowelChars.shift();
  }

  return chars.join('');
}

console.log(reverseVowels('hello')); // Outputs: 'holle'
console.log(reverseVowels('leetcode')); // Outputs: 'leotcede'
console.log(reverseVowels('aA')); // Outputs: 'Aa'
```
## Rotate String
```JavaScript
function rotateString(s, k) {
  const len = s.length;

  if (len === 0) return s;

  // Normalize the rotation count to handle cases where k is greater than the string length
  k = k % len;

  // Split and concatenate the string
  const part1 = s.slice(0, len - k);
  const part2 = s.slice(len - k);

  return part2 + part1;
}

console.log(rotateString('abcdef', 2)); // Outputs: 'efabcd'
console.log(rotateString('abcdef', 8)); // Outputs: 'efabcd' (8 % 6 = 2)
console.log(rotateString('hello', 0));  // Outputs: 'hello'
console.log(rotateString('hello', 5));  // Outputs: 'hello'
```


