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
