Instructions:

Write a function named first_non_repeating_letter that takes a string input, and returns the first character that is not repeated anywhere in the string.

For example, if given the input 'stress', the function should return 't', since the letter t only occurs once in the string, and occurs first in the string.

As an added challenge, upper- and lowercase letters are considered the same character, but the function should return the correct case for the initial letter. For example, the input 'sTreSS' should return 'T'.

If a string contains all repeating characters, it should return an empty string ("") or None -- see sample tests.



Solutions:

1.
function firstNonRepeatingLetter(s) {
  ch = s.split('').filter(function (c, i) { 
  return s.indexOf(c) == i && s.indexOf(c, i + 1) == -1;
}).join('');

res = ch.lenght == 1 ? ch : ch.charAt(0);
return res;
}


2.
function firstNonRepeatingLetter(s) {
  for (let i = 0; i < s.length; i++) {
    let char = s[i];
        
    if (s.indexOf(char) == i && s.indexOf(char, i + 1) == -1) {
    console.log(char);
      return char;
    }
  }
  return [];
}