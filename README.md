# -JavaScript-Notes


function telephoneCheck(str) {
  // regex that matches a phone number with no spaces,
  // with spaces, with dashes, and with or without country code
  let regex = /^[1]*[\s|-]*\d{3}[\s|-]*\d{3}[\s|-]*\d{4}$/;

  // regex that matches parentheses
  // with no spaces, with spaces, with dashes,
  // and with or without country code
  let regexParentheses = /^[1]*[\s]*[(]\d{3}[)][\s]*\d{3}[\s|-]*\d{4}$/;

  if (!regex.test(str)) {
    return regexParentheses.test(str);
  } else {
    return true;
  }

}

telephoneCheck("1 (555) 555-5555"); // returns true
telephoneCheck("1 555)555-5555") // returns false


function palindrome(str) {
    var splitted = str.split("");
 var reversed = splitted.reverse("");
 var joined = reversed.join("");
 return joined.toLowerCase().replace(/[^0-9a-z]/gi, '') == str.toLowerCase().replace(/[^0-9a-z]/gi, '')
}

palindrome('eye')

function convertToRoman(num) {
  var roman = {
    M: 1000,
    CM: 900,
    D: 500,
    CD: 400,
    C: 100,
    XC: 90,
    L: 50,
    XL: 40,
    X: 10,
    IX: 9,
    V: 5,
    IV: 4,
    I: 1
  };
  var str = '';

  for (var i of Object.keys(roman)) {
    var q = Math.floor(num / roman[i]);
    num -= q * roman[i];
    str += i.repeat(q);
  }

  return str;
}
