function DNAStrand(dna){
  var DNAOtherSide = [];
  for (var i = 0; i < dna.length; i++) {
    if (dna[i] === "A") {
      DNAOtherSide.push("T");
    } else if (dna[i] === T) {
      DNAOtherSide.push("A");
    } else if (dna[i] === C) {
      DNAOtherSide.push("G");
    } else if (dna[i] === G) {
      DNAOtherSide.push("C");
    }
  }
 return DNAOtherSide; 
};  
_________________________________________

/*The new "Avengers" movie has just been released! There are a lot of people at the cinema box office standing in a huge line. Each of them has a single 100, 50 or 25 dollars bill. A "Avengers" ticket costs 25 dollars.

Vasya is currently working as a clerk. He wants to sell a ticket to every single person in this line.

Can Vasya sell a ticket to each person and give the change if he initially has no money and sells the tickets strictly in the order people follow in the line?

Return YES, if Vasya can sell a ticket to each person and give the change. Otherwise return NO. */

function tickets(peopleInLine){
  var cashInRegister = {
    numOf25s: 0,
    numOf50s: 0,
    numOf100s: 0
  }
  var twentyFives = cashInRegister.numOf25s;
  var fifties = cashInRegister.numOf50s;
  var hundreds = cashInRegister.numOf100s;
  var doesItWork = '';
  for (var i = 0; i < peopleInLine.length; i++) {
    if (peopleInLine[i] === 25) {
      twentyFives += 1;
      if (twentyFives < 0 || fifties < 0 || hundreds < 0) {
        return doesItWork = "NO";
        break;
      } else if (twentyFives >= 0 && fifties >= 0 && hundreds >= 0) {
        return doesItWork = "YES";
      }  
    } else if (peopleInLine[i] === 50) {
      fifties += 1;
      twentyFives -= 1;
      if (twentyFives < 0 || fifties < 0 || hundreds < 0) {
        return doesItWork = "NO";
        break;
      } else if (twentyFives >= 0 && fifties >= 0 && hundreds >= 0) {
        return doesItWork = "YES";
      }   
    } else if (peopleInLine[i] === 100) {
      hundreds += 1;
      fifties -= 1;
      twentyFives -= 1;
      if (twentyFives < 0 || fifties < 0 || hundreds < 0) {
        return doesItWork = "NO";
        break;
      } else if (twentyFives >= 0 && fifties >= 0 && hundreds >= 0) {
        return doesItWork = "YES";
      } 
    }    
  }
}

_______________________________

/*Well met with Fibonacci bigger brother, AKA Tribonacci.

As the name may already reveal, it works basically like a Fibonacci, but summing the last 3 (instead of 2) numbers of the sequence to generate the next. And, worse part of it, regrettably I won't get to hear non-native Italian speakers trying to pronounce it :(

So, if we are to start our Tribonacci sequence with [1,1,1] as a starting input (AKA signature), we have this sequence:

[1,1,1,3,5,9,17,31,...]
But what if we started with [0,0,1] as a signature? As starting with [0,1] instead of [1,1] basically shifts the common Fibonacci sequence by once place, you may be tempted to think that we would get the same sequence shifted by 2 places, but that is not the case and we would get:

[0,0,1,1,2,4,7,13,24,...]
Well, you may have guessed it by now, but to be clear: you need to create a fibonacci function that given a signature array/list, returns the first n elements - signature included of the so seeded sequence.

Signature will always contain 3 numbers; n will always be a non-negative number; if n==0, then return an empty array and be ready for anything else which is not clearly specified ;)

If you enjoyed this kata more advanced and generalized version of it can be found in the Xbonacci kata

[Personal thanks to Professor Jim Fowler on Coursera for his awesome classes that I really recommend to any math enthusiast and for showing me this mathematical curiosity too with his usual contagious passion :)]*/

function tribonacci(signature,n){
  var sumPreviousThreeNums;
  var tribonacciSequence = [];
  if (n > 3) {
  tribonacciSequence.push(signature[0], signature[1], signature[2]);
  for (var i = 2; i < n-1; i++) {
    sumPreviousThreeNums = tribonacciSequence[i] + tribonacciSequence[i-1] + tribonacciSequence[i-2];
    tribonacciSequence.push(sumPreviousThreeNums);
    }
    return tribonacciSequence;
  } else if (n <= 3) {
      for (var i = 0; i <= n-1; i++) {
      tribonacciSequence.push(signature[i]);
      }
      return tribonacciSequence;
    }
};  
_________________________________
/*In this kata you will create a function that takes a list of non-negative integers and strings and returns a new list with the strings filtered out.

Example

filter_list([1,2,'a','b']) == [1,2]
filter_list([1,'a','b',0,15]) == [1,0,15]
filter_list([1,2,'aasf','1','123',123]) == [1,2,123]*/

function filter_list(l) {
var nums = [];
var strings = [];
  for (var i = 0; i < l.length; i++) {
    if (typeof l[i] === "number") {
    nums.push (l[i]);
    } else if (typeof l[i]) {
    strings.push (l[i]);
    }
  }
  return nums;
}

__________________________________________
/*You like building blocks. You especially like building blocks that are squares. And what you even like more, is to arrange them into a square of square building blocks!

However, sometimes, you can't arrange them into a square. Instead, you end up with an ordinary rectangle! Those blasted things! If you just had a way to know, whether you're currently working in vain… Wait! That's it! You just have to check if your number of building blocks is a perfect square.

Task

Given an integral number, determine if it's a square number:

In mathematics, a square number or perfect square is an integer that is the square of an integer; in other words, it is the product of some integer with itself.
The tests will always use some integral number, so don't worry about that in dynamic typed languages.

Examples

isSquare(-1) // => false
isSquare( 3) // => false
isSquare( 4) // => true
isSquare(25) // => true
isSquare(26) // => false */

var isSquare = function(n){
  var  x = Math.sqrt (n);
    if (n < 0) {
      return false;
    } else if (Math.abs(Math.floor(x) - x) > 0) {
      return false;
    } else if (Math.abs(Math.floor(x)) === x) {
      return true;
    }
};

___________________________
/* Mr. Scrooge has a sum of money 'P' that wants to invest, and he wants to know how many years 'Y' this sum has to be kept in the bank in order for this sum of money to amount to 'D'.

The sum is kept for 'Y' years in the bank where interest 'I' is paid yearly, and the new sum is re-invested yearly after paying tax 'T'

Note that the principal is not taxed but only the year's accrued interest

Example:

  Let P be the Principal = 1000.00      
  Let I be the Interest Rate = 0.05      
  Let T be the Tax Rate = 0.18      
  Let D be the Desired Sum = 1100.00


After 1st Year -->
  P = 1041.00
After 2nd Year -->
  P = 1083.86
After 3rd Year -->
  P = 1128.30
Thus Mr. Scrooge has to wait for 3 years for the initial pricipal to ammount to the desired sum.

Your task is to complete the method provided and return the number of years 'Y' as a whole in order for Mr. Scrooge to get the desired sum.

Assumptions : Assume that Desired Principal 'D' is always greater than the initial principal, however it is best to take into consideration that if the Desired Principal 'D' is equal to Principal 'P' this should return 0 Years.*/

function calculateYears(principal, interest, tax, desired) {
  var newTotal = principal;
  var yearCount = 0;
  while (newTotal < desired) {
    newTotal = newTotal + (newTotal * interest) * (1 - tax);
    yearCount++;
  }
  return yearCount; 
}


________________________________
/*This kata is to practice simple string output. Jamie is a programmer, and James' girlfriend. She likes diamonds, and wants a diamond string from James. Since James doesn't know how to make this happen, he needs your help.

Task:

You need to return a string that displays a diamond shape on the screen using asterisk ("*") characters. Please see provided test cases for exact output format.

The shape that will be returned from print method resembles a diamond, where the number provided as input represents the number of *’s printed on the middle line. The line above and below will be centered and will have 2 less *’s than the middle line. This reduction by 2 *’s for each line continues until a line with a single * is printed at the top and bottom of the figure.

Return null if input is even number or negative (as it is not possible to print diamond with even number or negative number).

Please see provided test case(s) for examples.

Python Note

Since print is a reserved word in Python, Python students must implement the diamond(n) method instead, and return None for invalid input.

JS Note

JS students, like Python ones, must implement the diamond(n) method, and return null for invalid input.


Test.describe( "diamond()", function(){

  Test.assertEquals(diamond(3), " *\n***\n *\n")
  Test.assertEquals(diamond(2), null)
  Test.assertEquals(diamond(-3), null)
  Test.assertEquals(diamond(0), null)
});
*/


function diamond(n){
  var diam = "";
  var star = "*";
  var space = " ";
  if (n < 0 || n % 2 === 0 ) {
    return null;
  } else {
    for (var i = 1; i <= n; i = i + 2) {
      diam += space.repeat((n/2)-(i/2)) + star.repeat (i) + '\n';
    } 
    for (var j = n-2; j >= 1; j = j - 2) {
      diam += space.repeat ((n/2)-(j/2)) + star.repeat(j) + '\n';
    }
    return diam;
  }
}
