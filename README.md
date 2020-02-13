# classExercises
Exercises

'use strict'

// / Write a function capitalize that takes a string and uses .map to return the same string in all caps.
// // ex. capitalize('whoop') // => 'WHOOP'
// // ex. capitalize('oh hey gurl') // => "OH HEY GURL"
// // use .split
// // use .join
// var capitalize = function(string) {
//   //  your code here
// };
// capitalize("hello There");
// ​
// // Now write a new function called swapCase that takes a string of words and uses .map and your newly written capitalize()
// // function to return a string where every other word is in all caps.
// // Hint: look up Array.prototype.map on MDN and see what arguments the .map callback can take.
// // ex: swapCase('hey gurl, lets javascript together sometime') // => "HEY gurl, LETS javascript TOGETHER sometime"
// ​
// var swapCase = function(string){
//   // your code here
// }
// swapCase("hey gurl, lets javascript together sometime")

function stepbystep_capitalize(inputStr) {

    // this step does:
    //      split the inputStr cast as a String
    //      into a new array of single characters
    //
    //      here the resulting lowerCaseArray consists of X elements
    //      where X = inputStr.length
    //      and each element has a single character
    //
   let lowerCaseArray = String(inputStr).split("");

    // this step does:
    //      converts every character of the lowercase array
    //      into an uppercase character
    //      by utilizing the callbaclk function callbackConvertToUppercase
    //      that is passed as an argument to .map
    //
    //      the resulting array upperCaseArray consists of X elements
    //      where X is same as step 1
    //      and each element has a single uppercased string character
    //
   let upperCaseArray = lowerCaseArray.map(callbackConvertToUppercase);

    // this step does:
    //      join all the elements of upperCaseArray into a single string
    //      without any seperators and we return that string
    //
    return upperCaseArray.join('');
};

function also_capitalize(inputStr) {
    return String(inputStr).split("").map(callbackConvertToUppercase).join('');
};

function callbackConvertToUppercase (currentElementValue) {
    return String(currentElementValue).toUpperCase();
};


console.log(stepbystep_capitalize('oh hey gurl'));   // => "OH HEY GURL"
console.log(also_capitalize('oh hey gurl')); // => "OH HEY GURL"
;
//exercises
function swapCase (inputStr) {
    let lowerCaseArray = String(inputStr).split(" ");
    let mixCaseArray = lowerCaseArray.map(callbackConvertEveryOther)
    return mixCaseArray.join(' ');    
}

function callbackConvertEveryOther (currentElementValue, currentElementIndex) {
    //how where do we get the currentElementValue, currentElementIndex etc, if we don't use it dose the code work
    if (currentElementIndex % 2 == 0) {
        return stepbystep_capitalize(currentElementValue)
        //i though here we should use swapCase instead of stepbystep_capitalize
    } else {
        return currentElementValue
    }
};

// => "HEY gurl, LETS javascript TOGETHER sometime"
console.log(swapCase('hey gurl, lets javascript together sometime'));

;


//exercises 1
function capital(stringStr) {
    let lowercase = String(stringStr).split('');
    let uppercase = lowercase.map(callingBackAgain)
    return uppercase.join('');
};

function callingBackAgain(currentElementValue) {
    return String(currentElementValue).toUpperCase()
};
console.log(capital('how did i do it again'));

//exercises 1 / short format
function alsoCapital(stringStr) {
    return String(stringStr).split('').map(callingBackAgain).join('');
};
function callingBackAgain(currentElementValue) {
    return String(currentElementValue).toUpperCase();
};

console.log(alsoCapital('again and again and again...'));


//exercises
function showCase(myStr) {
    let lessCase = String(myStr).split('');
    let topCase = lessCase.map(callMeBack);
    return topCase.join('');
};

function callMeBack(currentElementValue, currentElementIndex) {
    if (currentElementIndex % 2 == 0) {
        return capital(currentElementValue)
    } else {
        return currentElementValue
    };
};

console.log(showCase('i have got to do this again'));



//exercise
function showCase(myStr) {
    return String(myStr).split('').map(callMeBack).join('') 
}

function callMeBack(currentElementValue, currentElementIndex) {
    if (currentElementIndex % 2 == 0) {
        return capital(currentElementValue)
    } else {
        return currentElementValue
    };
};
console.log(swapCase('hey gurl, lets javascript together sometime')) // => "HEY gurl, LETS javascript TOGETHER sometime"


// function showEvenOrOdd(aNumber) {
//     if (aNumber % 2 == 0) {
//         console.log(even)
//     } else {
//         console.log(odd)
//     }
// }
