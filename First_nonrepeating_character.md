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
  slc = s.toLowerCase();
  for (let i = 0; i < slc.length; i++) {
    let char = slc[i];
    let baseChar = s[i];
    if (slc.indexOf(char) == i && slc.indexOf(char, i + 1) == -1) {
      return baseChar;
    }
  }
    return ''; 
}


3.
function firstNonRepeatingLetter(s){
  return s.split('').find(e => s.match(new RegExp(`${e}`, 'gi')).length === 1) || ''
}
