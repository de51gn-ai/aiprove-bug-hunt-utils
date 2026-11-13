# bug-hunt-utils
`reports.json` lists 4 verified bugs in utils.js, each with a failing input
and the correct output:
- factorial(5) returns 24, should be 120 (loop `i<n` drops n)
- countVowels("AEIOU") returns 0, should be 5 (regex misses uppercase)
- titleCase("don't stop") returns "Don'T Stop" (apostrophe creates a word boundary)
- reverse("😀a") returns garbled surrogates (split("") breaks astral characters)
All four reproduced by running utils.js under Node before writing this file.
