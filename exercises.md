# `100 Javascript Exercises`

Adapted from the [Python Exercises of Jeffrey Hu](https://github.com/zhiwehu/Python-programming-exercises).
[Github: Jeffrey Hu](https://github.com/zhiwehu)

Adapted by: [Joseph Anthony Debono](https://github.com/jadebono).
[Email Joseph](joe@jadebono.com)

These are the exercises with the standard solutions. Class-based (OOP) solutions are kept at a minimum and only as the exercise at that point.

1. The README file: [README.md](./README.md);
1. Object Oriented Programming solutions: [OOP exercises and solutions](./OOP.md)

---

## Question 1

**Level 1**

Write a program which will find all such numbers which are divisible by 7 but are not a multiple of 5, between 2000 and 3200 (both included). The numbers obtained should be printed in a comma-separated sequence on a single line.

Solution:

```js
function comp(start, end) {
  let arr = [];
  a = parseInt(start);
  b = parseInt(end);
  for (let i = a; i <= b; i++) {
    if (i % 7 === 0 && i % 5 !== 0) arr.push(i);
  }
  return arr.join(",");
}

function main() {
  let a = "2000",
    b = "3200",
    c = comp(a, b);
  console.log(c);
}

main();
```

---

## Question 2

**Level 1**

Write a program which can compute the factorial of a given numbers.
Suppose the following input is supplied to the program: 8
Then, the output should be: 40320

Hints:
In case of input data being supplied to the question, it should be assumed to be through a web page (using prompt()).

Solution:

```js
function factorial(n) {
  return n === 0 ? 1 : n * factorial(n - 1);
}

function main() {
  let a = 8;
  console.log(factorial(8));
}

main();
```

---

## Question 3

**Level 1**

With a given integral number n, write a program to generate an object that contains (i, i\*i) such that is an integral number between 1 and n (both included). and then the program should print the object.
Suppose the following input is supplied to the program: 8
Then, the output should be: {1: 1, 2: 4, 3: 9, 4: 16, 5: 25, 6: 36, 7: 49, 8: 64}

Hints:
If the input data is to be supplied, let it supplied from a prompt() from a webpage

Solution:

```js
function obj(n) {
  let newObj = {};
  for (let i = 1; i <= n; i++) {
    newObj[i] = i * i;
  }
  return newObj;
}

function main() {
  let a = 8;
  console.log(obj(a));
}

main();
```

---

## Question 4

**Level 1**

Write a program which accepts a sequence of comma-separated numbers from a webpage and generate an array and an object which contains every number.
Suppose the following input is supplied to the program:
34,67,55,33,12,98

Then, the output should be:
['34', '67', '55', '33', '12', '98']
{'34':34, '67':67, '55':55, '33':33, '12':12, '98':98}

Hints:
If the input data is to be supplied, let it supplied from a prompt() from a webpage

Solution:

```js
function obj(n) {
  let newObj = {};
  let newArr = n.split(",");
  newArr.forEach((el) => {
    newObj[el] = parseInt(el);
  });
  return [newArr, newObj];
}

function main() {
  let a = "34,67,55,33,12,98";
  let [x, y] = obj(a);
  console.log(x, y);
}

main();
```

---

## Question 5

**Level 1**

Define an object which has two methods and no (initial) properties:

- setString: sets a new property called string to the object
- getString: to print the string in upper case.
  Also please include simple function to run the object methods.

Hints:
Do not use Class syntax for this.

Solution:

```js
const myObj = {
  setString(text) {
    this.string = text;
  },
  getString() {
    console.log(this.string.toUpperCase());
  },
};

function main() {
  myObj.setString("hello new string");
  myObj.getString();
}

main();
```

---

## Question 6

**Level 2**

Write a program that calculates and prints the value according to the given formula:
Q = Square root of [(2 * c * d)/h]

- The fixed values of c and h: c is 50, h is 30.
- d is the variable whose values should be input to your program in a comma-separated sequence.

Example:
Let us assume the following comma separated input sequence is given to the program: 100,150,180
The output of the program should be: 18,22,24

Hints:
If the output received is in decimal form, it should be rounded off to its nearest value for example, if the output received is 26.0, it should be printed as 26)

Solution:

```js
function formula(nArr) {
  formArr = nArr.map((el) => {
    return Math.round(Math.sqrt((2 * 50 * el) / 30));
  });
  return formArr.join(",");
}

function main() {
  let nums = "100,150,180".split(",").map((el) => {
    return parseInt(el);
  });
  console.log(formula(nums));
}

main();
```

---

## Question 7

**Level 2**

Write a program which takes 2 digits, X,Y as input and generates a 2-dimensional array. The element value in the i-th row and j-th column of the array should be i\*j.
Note: i=0,1.., X-1; j=0,1,¡­Y-1.

Example:
Suppose the following inputs are given to the program: 3,5
Then, the output of the program should be: [[0, 0, 0, 0, 0], [0, 1, 2, 3, 4], [0, 2, 4, 6, 8]]

Hints:

1. Create an array,
1. The external loop (rows) should create an empty array for each of its iterations and push each array into the parent array.
1. The inner loop should multiply the current value of row with each of the values of cols and push each product into the current iteration of array[rows].

Solution:

```js
function digitArr(n) {
  let [rows, cols] = n;
  let arr = [];
  for (let i = 0; i < rows; i++) {
    arr.push([]);
    for (let j = 0; j < cols; j++) {
      arr[i].push(i * j);
    }
  }
  return arr;
}

function main() {
  let x = "3,5".split(",").map((el) => parseInt(el));
  console.log(digitArr(x));
}

main();
```

---

## Question 8

**Level 2**

Write a program that accepts a comma separated sequence of words as input and prints the words in a comma-separated sequence after sorting them alphabetically.
Suppose the following input is supplied to the program: without,hello,bag,world
Then, the output should be: bag,hello,without,world

Hints:
In case of input data being supplied to the question, it should be assumed to be a prompt input from a webpage.

Solution:

```JS
function sortWords(str) {
    return str.split(",").sort().join(",");
}

function main() {
    let a = "without,hello,bag,world";
    console.log(sortWords(a));
}

main();
```

---

## Question 9

**Level 2**

Write a program that accepts sequence of lines as input and prints the lines after making all characters in the sentence capitalized.
Suppose the following input is supplied to the program:

- Hello world
- Practice makes perfect
  Then, the output should be:
- HELLO WORLD
- PRACTICE MAKES PERFECT

Hints:
In case of input data being supplied to the question, it should be assumed to be a prompt input from a webpage.

Solution:

```js
function capz(str) {
  return str.toUpperCase();
}

function main() {
  let str = "Hello world";
  let capt = capz(str);
  console.log(capt);
}

main();
```

---

## Question 10

**Level 2**

Write a program that accepts a sequence of whitespace separated words in a single string as input and prints the words in ascending order after removing all duplicate words and sorting them alphanumerically. Output them once more as whitespace separated string.

Suppose the following input is supplied to the program: hello world and practice makes perfect and hello world again
Then, the output should be: again and hello makes perfect practice world

Hints:
In case of input data being supplied to the question, it should be assumed to be a prompt input from a webpage.

Solution:

```js
function cleanSort(arr) {
  let newArr = [];
  arr.forEach((element) => {
    if (!newArr.includes(element)) newArr.push(element);
  });
  return newArr.sort().join(" ");
}

function main() {
  str = "hello world and practice makes perfect and hello world again";
  let prss = cleanSort(str.split(" "));
  console.log(prss);
}

main();
```

---

## Question 11

**Level 2**

Write a program which accepts a sequence of comma separated 4 digit binary numbers as its input and then check whether they are divisible by 5 or not. The numbers that are divisible by 5 are to be printed in a comma separated sequence.

Suppose the following input: 0100,0011,1010,1001
Then the output should be: 1010

Notes: Assume the data is input by console.

Hints:
In case of input data being supplied to the question, it should be assumed to be a prompt input from a webpage.

Solution:

```js
function binCalc(nStr) {
  return nStr
    .split(",")
    .filter((el) => {
      if (parseInt(el, 2) % 5 === 0) return el;
    })
    .join(",");
}

function main() {
  let a = "0100,0011,1010,1001";
  console.log(binCalc(a));
}

main();
```

---

## Question 12

**Level 2**

Write a program, which will take two numbers (such as 1000 and 3000) and find all such numbers between those two numbers (both included) such that each digit of the number is an even number. The numbers obtained should be printed in a comma-separated sequence on a single line.

Hints:
In case of input data being supplied to the question, it should be assumed to be a prompt input from a webpage.

Solution:

```js
function findEvens(n) {
  let [a, b] = n.split(",");
  let newArr = [];
  for (let i = parseInt(a); i <= parseInt(b); i++) {
    newArr.push(i);
  }

  return newArr
    .filter((el) => {
      if (el % 2 === 0) return el;
    })
    .join(",");
}

function main() {
  let x = "1000,3000";
  console.log(findEvens(x));
}

main();
```

---

## Question 13

**Level 2**

Write a program that accepts a sentence and calculate the number of letters and digits.
Suppose the following input is supplied to the program: hello world! 123
Then, the output should be:

- LETTERS 10
- DIGITS 3

Hints:
In case of input data being supplied to the question, it should be assumed to be a prompt input from a webpage.

Solution:

```js
function countChars(phr) {
  datObj = { LETTERS: 0, DIGITS: 0 };
  for (let item of phr) {
    if (item.match(/[a-z]/i)) datObj.LETTERS += 1;
    if (item.match(/[0-9]/)) datObj.DIGITS += 1;
  }
  return datObj;
}

function main() {
  let str = "hello world! 123";
  console.log(countChars(str));
}

main();
```

---

## Question 14

**Level 2**

Write a program that accepts a sentence and calculate the number of upper case letters and lower case letters.
Suppose the following input is supplied to the program: Hello world!
Then, the output should be:

- UPPER CASE 1
- LOWER CASE 9

Hints:
In case of input data being supplied to the question, it should be assumed to be a prompt input from a webpage.

Solution:

```js
function countCase(phr) {
  let datObj = { UPPERCASE: 0, LOWERCASE: 0 };
  phr.split("").forEach((ele) => {
    if (ele.match(/[A-Z]/)) datObj.UPPERCASE += 1;
    if (ele.match(/[a-z]/)) datObj.LOWERCASE += 1;
  });
  return datObj;
}

function main() {
  let str = "Hello world!";
  console.log(countCase(str));
}

main();
```

---

## Question 15

**Level 2**

Write a program that computes the value of a+aa+aaa+aaaa with a given digit as the value of a. Suppose the following input is supplied to the program: 9
Then, the output should be: 11106

Hints:
In case of input data being supplied to the question, it should be assumed to be a prompt input from a webpage.

Solution:

```js
function compChars(str, n = 1) {
  return str
    .split("+")
    .map((ele) => {
      return parseInt(String(n).repeat(ele.length));
    })
    .reduce((accum, counter) => {
      return accum + counter;
    });
}

function main() {
  let str = "a+aa+aaa+aaaa";
  let n = 9;
  console.log(compChars(str, n));
}

main();
```

---

## Question 16

**Level 2**

use map to return an array containing the square of each odd number in another array. The array is input by a sequence of comma-separated numbers.
Suppose the following input is supplied to the program: 1,2,3,4,5,6,7,8,9
Then, the output should be: 1,9,25,49,81

Hints:
In case of input data being supplied to the question, it should be assumed to be a prompt input from a webpage.

Solution:

```js
function newArr(numStr) {
  return numStr
    .split(",")
    .filter((ele) => {
      if (parseInt(ele) % 2 !== 0) return ele;
    })
    .map((ele) => {
      return parseInt(ele) ** 2;
    });
}

function main() {
  let nums = "1,2,3,4,5,6,7,8,9";
  console.log(newArr(nums));
}

main();
```

---

## Question 17

**Level 2**

Write a program that computes the net amount of a bank account based a transaction log from console input. The transaction log format is shown as following:
D 100
W 200
D means deposit while W means withdrawal.
Suppose the following input is supplied to the program:
D 300
D 300
W 200
D 100
Then, the output should be:
500

Hints:
In case of input data being supplied to the question, it should be assumed to be a prompt input from a webpage.

Solution:

```js
function transLog(datArr) {
  return datArr
    .split("\n")
    .map((elem) => {
      return elem[0] === "D"
        ? parseInt(elem.slice(2))
        : -parseInt(elem.slice(2));
    })
    .reduce((accum, counter) => {
      return accum + counter;
    });
}

function main() {
  let trans = "D 300\nD 300\nW 200\nD 100";
  console.log(transLog(trans));
}

main();
```

---

## Question 18

**Level 3**

A website requires the users to input username and password to register. Write a program to check the validity of password input by users. Following are the criteria for checking the password:

1. At least 1 letter between [a-z]
1. At least 1 number between [0-9]
1. At least 1 letter between [A-Z]
1. At least 1 character from [$#@]
1. Minimum length of transaction password: 6
1. Maximum length of transaction password: 12

Your program should accept a sequence of comma separated passwords and will check them according to the above criteria. Passwords that match the criteria are to be printed, each separated by a comma.

Example:
If the following passwords are given as input to the program: ABd1234@1,a F1#,2w3E\*,2We3345,4Jr4#175
Then, the output of the program should be: ABd1234@1,4Jr4#175

Hints:
In case of input data being supplied to the question, it should be assumed to be a prompt input from a webpage.

Solution:

```js
function validPass(pwd) {
  return pwd.split(",").filter((ele) => {
    if (ele.match(/\w[$#@]/) && ele.length >= 6 && ele.length <= 12) return ele;
  });
}

function main() {
  let pwds = "ABd1234@1,a F1#,2w3E*,DDD2222,2We3345,4Jr4#175";
  console.log(validPass(pwds));
}

main();
```

---

## Question 19

**Level 3**

You are required to write a program to sort the (name, age, height) arrays by ascending order where name is string, age and height are numbers. The arrays are input by console.

The sort criteria are:

1. Sort based on name;
1. Then sort based on age;
1. Then sort by score.

The priority is that name > age > score.
If the following arrays are given as input to the program:
Tom,19,80
John,20,90
Jony,17,91
Jony,16,91
Jony,17,93
Jason,21,85

Then, the output of the program should be:
[ [ 'Jason', '21', '85' ],[ 'John', '20', '90' ],[ 'Jony', '16', '91' ],[ 'Jony', '17', '91' ],[ 'Jony', '17', '93' ],[ 'Tom', '19', '80' ]]

Hints:
In case of input data being supplied to the question, it should be assumed to be a prompt input from a webpage.

Solution:

```js
function sortArr(arr) {
  return arr
    .split("\n")
    .map((ele) => {
      return ele.split(",");
    })
    .sort();
}

function main() {
  let arrs =
    "Tom,19,80\nJohn,20,90\nJony,17,91\nJony,16,91\nJony,17,93\nJason,21,85";
  console.log(sortArr(arrs));
}

main();
```

---

## Question 20

**Level 3**

Define a class with a generator which can iterate the numbers, which are divisible by 7, between a given range 0 and n.

Hints:

1. Within a class, the generator function may be created by an asterisk before the function name ex: \*myGen()
1. when the generator object is created, the next iteration can be called by genObj.next()
1. the .next() method returns an object with two properties:
   1. value - which contains the value yielded by the generator
   1. done - which is true or false according to whether there are any more iterations left.

Solution:

```js
class GenSeven {
  *genSeven(n) {
    for (let i = 0; i <= n; i++) {
      if (i % 7 === 0) {
        yield `${i} is divisible by 7`;
      } else {
        yield `${i} is not divisible by 7`;
      }
    }
  }
}

function main() {
  const new7 = new GenSeven();
  let n = 14;
  // create generator object
  const my7 = new7.genSeven(n);
  // set the flag for the while loop
  let flag = false;
  // while flag is false:
  while (!flag) {
    // call .next() method on my7 and store the resultant object containing
    // the value property (which contains the yield) and the done property
    // containing the current status of the iteration (true/false)
    let get7 = my7.next();
    // if done property is false, there are still values yielded so print them out
    // otherwise there are no more values left and the while loop can be stopped.
    !get7.done ? console.log(get7.value) : (flag = get7.done);
  }
}

main();
```

---

## Question 21

**Level 3**

A robot moves on a 2D (Cartesian) plane starting from the original point (0,0). The robot can move toward UP, DOWN, LEFT and RIGHT with a given steps. The trace of robot movement is shown as the following:
UP 5
DOWN 3
LEFT 3
RIGHT 2

The numbers after the direction are steps. Please write a program to compute the distance from current position after a sequence of movement to the original point. If the distance is a float, then just print the nearest integer.

Example:
If the following instructions are given as input to the program:
UP 5
DOWN 3
LEFT 3
RIGHT 2
Then, the output of the program should be:
2

Hints:

1. In case of input data being supplied to the question, it should be assumed to be a prompt input from a webpage.
1. to find the distance between (x1, y1) and (x2, y2) Use this formula: d= √((x2−x1)**2+(y2−y1)**2)
1. Don't forget to round it to the nearest integer

Solution:

```js
function computeDist(data) {
  let dataArr = data.split("\n");
  let pos = [0, 0];
  for (let i = 0; i < dataArr.length; i++) {
    let idx = dataArr[i].length - 1;
    if (dataArr[i].includes("UP")) pos[1] += parseInt(dataArr[i][idx]);
    if (dataArr[i].includes("DOWN")) pos[1] -= parseInt(dataArr[i][idx]);
    if (dataArr[i].includes("LEFT")) pos[0] -= parseInt(dataArr[i][idx]);
    if (dataArr[i].includes("RIGHT")) pos[0] += parseInt(dataArr[i][idx]);
  }
  return Math.round(Math.sqrt((pos[0] - 0) ** 2 + (pos[1] - 0) ** 2));
}

function main() {
  let data = "UP 5\nDOWN 3\nLEFT 3\nRIGHT 2";
  let sol = computeDist(data);
  console.log(sol);
}

main();
```

---

## Question 22

**Level 3**

Write a program to compute the frequency of the words from the input. The output should be sorted by the key alphanumerically in ascending order.
Suppose the following input is supplied to the program: "New to Python or choosing between Python 2 and Python 3? Read Python 2 or Python 3."
Then, the output should be:
2:2
3.:1
3?:1
New:1
Python:5
Read:1
and:1
between:1
choosing:1
or:2
to:1

Hints:

1. In case of input data being supplied to the question, it should be assumed to be a prompt input from a webpage.
1. Sort in ascending order
1. Output as an object
1. Use Object.keys(datObj) to return an array of all keys in the datObj and then check that array for the key, or use datObj.hasOwnProperty(key).

Solution:

```js
function compItems(itemArr) {
  let datObj = {};
  for (let item of itemArr) {
    Object.keys(datObj).includes(item)
      ? (datObj[item] += 1)
      : (datObj[item] = 1);
  }
  return datObj;
}

function main() {
  let str =
    "New to Python or choosing between Python 2 and Python 3? Read Python 2 or Python 3."
      .split(" ")
      .sort();
  console.log(compItems(str));
}

main();
```

---

## Question 23

**level 1**

Write a function that can calculate square value of number

Hints:

1. Use the \*\* operator
1. In case of input data being supplied to the question, it should be assumed to be a prompt input from a webpage.

Solution:

```js
function sq(n) {
  return n ** 2;
}

function main() {
  console.log(sq(4));
}

main();
```

---

## Question 24

**Level 1**

Define a class, with both a class parameter and instance parameter/s.

Hints:

1. Define a instance parameter, and add it to the constructor method
1. In case of input data being supplied to the question, it should be assumed to be a prompt input from a webpage.

Solution:

```js
class Person {
  constructor(name = "John", surname = "Doe") {
    this.species = "Homo Sapiens";
    this.name = name;
    this.surname = surname;
  }

  read() {
    console.log(`${this.name} is reading`);
  }
}

let jack = new Person("Jack", "Marshall");
console.log(jack);
jack.read();
```

---

## Question 25

**Level 1**

Define a function that can compute and return the sum of two numbers.

Hints:
In case of input data being supplied to the question, it should be assumed to be a prompt input from a webpage.

Solution:

```js
function computeSum(a, b) {
  return a + b;
}

function main() {
  console.log(computeSum(3, 4));
}

main();
```

---

## Question 26

**Level 1**

Define a function that can convert a string into an integer and print it in console.

Hints:

1. Add error checking to allow for the possibility that the input is not an integer in the type of a string
1. typeof NaN is in fact a number, while parseInt(n) when n is not a string of an integer or a float can very often output NaN, immensely complicating error checking. A solution could be to wrap parseInt(n) in Number.isNaN() which checks whether the output of parseInt(n) is NaN or any number not N. Remember to output the number as an integer
1. In case of input data being supplied to the question, it should be assumed to be a prompt input from a webpage.

Solution:

```js
function convInt(n) {
  if (!Number.isNaN(parseInt(n))) return Math.round(Number(n));
  return "Not a valid target for conversion to integer!";
}

function main() {
  let args = ["5", 5, "4.3", 4.3, "Hello!", NaN, false, true];
  for (let item of args) {
    console.log(convInt(item));
  }
}

main();
```

---

## Question 28

**Level 1**

Define a function that can receive two integral numbers in string form and compute their sum and then print it in console.

Hints:

1. Add error checking to allow for the possibility that the inputs are not integer in the type of a string
1. Add functionality to check if the number is a float and if so convert it to an integer
1. In case of input data being supplied to the question, it should be assumed to be a prompt input from a webpage.

Solution:

```js
function convSumInt(vars) {
  if (!Number.isNaN(parseInt(vars[0])) && !Number.isNaN(parseInt(vars[1])))
    return Math.round(parseInt(vars[0]) + parseInt(vars[1]));
  return "not a valid target for finding the sum of the integers!";
}

function main() {
  let args = [
    ["5", "8"],
    [5, 4],
    ["4.3", "3.1"],
    [4.3, 7.1],
    ["Hello!", "Twiggy"],
    [7, "Hwaet"],
    [3, NaN],
    [NaN, NaN],
    [false, false],
    [true, true],
  ];
  for (let item of args) {
    console.log(`(${item[0]} + ${item[1]}) is ${convSumInt(item)}`);
  }
}

main();
```

---

## Question 29

**Level 1**

Define a function that can accept two strings as input and concatenate them and then print it in console.

Hints:
In case of input data being supplied to the question, it should be assumed to be a prompt input from a webpage.

Solution:

```js
function addStr(valArr) {
  return String(valArr[0]) + String(valArr[1]);
}

function main() {
  let args = [
    ["5", "8"],
    [5, 4],
    ["4.3", "3.1"],
    [4.3, 7.1],
    ["Hello!", "Twiggy"],
    [7, "Hwaet"],
    [3, NaN],
    [NaN, NaN],
    [false, false],
    [true, true],
  ];
  for (item of args) {
    console.log(
      `Adding item ${item[0]} and item ${item[1]} produces: ${addStr(item)}`
    );
  }
}

main();
```

---

## Question 30

**Level 1**

Define a function that can accept two strings as input and print the string with maximum length in console. If two strings have the same length, then the function should print al l strings line by line.

Example:
"hey" "world" returns "world"
"hello" "world" returns
"hello"
"world"

Hints:

1. In case of input data being supplied to the question, it should be assumed to be a prompt input from a webpage.
1. Assume that the input data can be of any type, so add functionality to convert to string any received input
1. If using (item in arr) to iterate through an array, remember that item will be the index in the type of string.

Solution:

```js
function longestStr(valArr) {
  let a = String(valArr[0]),
    b = String(valArr[1]);
  return a.length === b.length
    ? `${a}\n${b}`
    : a.length > b.length
    ? `${a}`
    : `${b}`;
}

function main() {
  let args = [
    ["5", "8"],
    [5, 4],
    ["4.3", "3.156"],
    [4.3, 7.1],
    ["elementary", 45],
    ["Hello!", "Twiggy"],
    [7, "Hwaet"],
    [3, NaN],
    [NaN, NaN],
    [false, false],
    [true, true],
  ];
  for (item in args) {
    console.log(`Item no ${parseInt(item) + 1}:\n${longestStr(args[item])}\n`);
  }
}

main();
```

---

## Question 31

**Level 1**

Define a function that can accept an integer number as input and print the "It is an even number" if the number is even, otherwise print "It is an odd number".

Hints:

1. Use % operator to check if a number is even or odd.
1. Assume that the input can be of any type. Add functionality to check for this and reject all invalid types, but if the input is the string of an integer or float, turn it into an integer and process it accordingly
1. In case of input data being supplied to the question, it should be assumed to be a prompt input from a webpage.

Solution:

```js
function evenOdd(n) {
  return Number.isNaN(parseInt(n))
    ? `${n} cannot be converted to an integer so it cannot be assessed`
    : Math.round(parseInt(n)) % 2 === 0
    ? `${n} is Even!`
    : `${n} is odd!`;
}

function main() {
  let args = ["5", 4, "3.1", 4.3, "Hello!", NaN, false, true];
  for (let item of args) console.log(evenOdd(item));
}

main();
```

---

## Question 32

**Level 1**

Define a function which can print an object where the keys are 1... n (supplied) and the values are squares of n. For example, if createObj(3), then the created object would be:
{ 1: 1, 2: 4, 3: 9, 4: 16 }. The supplied n should be an integer due to the need to ensure that the keys are in a predictably ascending range.

Hints:

1. Assume that the input can be of any type. Add functionality to check for this and reject all invalid types, but if the input is the string of an integer or float, turn it into an integer and process it accordingly
1. In case of input data being supplied to the question, it should be assumed to be a prompt input from a webpage.

Solution:

```js
function createObj(n) {
  let sqrObj = {};
  for (let i = 1; i <= n; i++) {
    sqrObj[i] = i ** 2;
  }
  return sqrObj;
}

function testArgs(args) {
  let filteredArgs = args.filter((elem) => {
    if (!Number.isNaN(parseInt(elem))) return Math.round(parseFloat(elem));
  });
  return filteredArgs;
}

function main() {
  let args = ["5", 4, "3.1", 4.3, "Hello!", NaN, false, true];
  let filteredArgs = testArgs(args);
  for (item of filteredArgs) {
    console.log(createObj(item));
  }
}

main();
```

---

## Question 33

**Level 1**

Define a function which can create an object where the keys are numbers between 1 and 20 (both included) and the values are square of keys.

Hints:
No input or error checking. The function should have no parameters either. It just returns the required object when called.

Solution:

```js
function newXXObj() {
  let twenty = {};
  for (let i = 1; i <= 20; i++) {
    twenty[i] = i ** 2;
  }

  return twenty;
}

function main() {
  let xxObj = newXXObj();
  console.log(xxObj);
}

main();
```

---

## Question 34

**Level 1**

Define a function which can generate an object where the keys are numbers between 1 and 20 (both included) and the values are the square of the keys. Then print the values ONLY.

Hints:
No input or error checking. The function should have no parameters either. You can export the printing of the values to another function.
A helpful method is Object.values(myObj) which returns an array of all values in myObj. Related methods are Object.keys(myObj) for keys, and Object.entries(myObj) for an array containing arrays of each key:value pair - [[key:value], [key:value]]

Solution:

```js
function xxObj() {
  twenty = {};
  for (let i = 1; i <= 20; i++) {
    twenty[i] = i ** 2;
  }
  return twenty;
}

function main() {
  let tw = Object.values(xxObj());
  console.log(tw);
}

main();
```

---

## Question 35

**Level 1**

Define a function which can generate an object where the keys are numbers between 1 and 20 (both included) and the values are square of keys. The function should just print the keys only. You can export the printing to another function.

Solution:

```js
function xxObj() {
  let twenty = {};
  for (let i = 0; i <= 20; i++) {
    twenty[i] = i ** 2;
  }
  return twenty;
}

function main() {
  let twenty = Object.keys(xxObj());
  console.log(twenty);
}

main();
```

---

## Question 36

**Level 1**

Define a function which can generate a array where the values are square of numbers between 1 and 20 (both included). Then the function needs to print an array with the first 5 elements in the array. You can export the array to another function and print it there.

Solution:

```js
function xxObj() {
  let xx = {};
  for (let i = 1; i <= 20; i++) {
    xx[i] = i ** 2;
  }
  return Object.values(xx).slice(0, 5);
}

function main() {
  console.log(xxObj());
}

main();
```

---

## Question 37

**Level 1**

Define a function which can generate an array where the values are square of numbers between 1 and 20 (both included). Then the function needs to print an array with the last 5 elements in the array. You can export the array to another function and print it there.

Solution:

```js
function xxObj() {
  let twenty = {};
  for (let i = 0; i <= 20; i++) {
    twenty[i] = i ** 2;
  }
  return Object.entries(twenty);
}

function main() {
  let xx = xxObj();
  console.log(xx.slice(xx.length - 5));
}

main();
```

---

## Question 38

**Level 1**

Define a function which can generate an array where the values are square of numbers between 1 and 20 (both included). Then the function needs to print an array with all values except the first 5 elements in the list. You can export the array to another function and print it there.

Solution:

```js
function xxObj() {
  let twenty = {};
  for (let i = 0; i <= 20; i++) {
    twenty[i] = i ** 2;
  }
  return Object.values(twenty).slice(6);
}

function main() {
  console.log(xxObj());
}

main();
```

---

## Question 39

**Level 1**

With a given array [1,2,3,4,5,6,7,8,9,10] write a program to print the first half values in one line and the last half values in one line.

Hints:

1. You can either create two new arrays and print one under the other
1. Or you turn the array into a string and print one half over the other one both halves as strings

Solution:

```js
function splitArr(arr) {
  return [arr.slice(0, 5), arr.slice(5)];
}

function splitStr(arr) {
  return `${arr.slice(0, 5)}\n${arr.slice(5)}`;
}

function main() {
  let arr = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
  console.log(splitArr(arr));
  console.log(splitStr(arr));
}

main();
```

---

## Question 40

**Level 1**

Write a program to generate and print another array whose values are even numbers in the given array [1,2,3,4,5,6,7,8,9,10] => [2,3,6,8,10]. If you like add functionality to do the same if the numbers are supplied as a comma separated string "1,2,3,4,5,6,7,8,9,10". In this case,the output should be a comma separated string.

Solution:

```js
function evenArr(arr) {
  return arr.filter((el) => {
    if (el % 2 === 0) return el;
  });
}

function evenStr(str) {
  return str
    .split(",")
    .filter((el) => {
      if (parseInt(el) % 2 === 0) return parseInt(el);
    })
    .join(",");
}

function main() {
  let arr = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
  let str = "1,2,3,4,5,6,7,8,9,10";
  console.log(evenArr(arr));
  console.log(evenStr(str));
}

main();
```

---

## Question 41

**Level 1**

Write a program which accepts a string as input and prints "Yes" if the string is "yes" or "YES" or "Yes", otherwise print "No".

Hints:
In case of input data being supplied to the question, it should be assumed to be a prompt input from a webpage.

Solution:

```js
function parse(str) {
  if (typeof str !== "string") return `${str}: no`;
  return str.toLowerCase() === "yes" ? `${str}: yes` : `${str}: no`;
}

function affirm(str) {
  return typeof str !== "string"
    ? "No"
    : str.toLowerCase() === "yes"
    ? "Yes"
    : "No";
}

function main() {
  let x = [
    "Yes",
    "yEs",
    "yeS",
    "YEs",
    "yES",
    "YES",
    "yes",
    "no",
    "en arche ho logos",
    3,
    5.6,
    "3.5",
    NaN,
    true,
    false,
    { 1: 1 },
  ];
  for (let item of x) {
    console.log(`${item} is ${affirm(item)}`);
  }
}

main();
```

---

## Question 42

**Level 1**

Write a program which can filter even numbers in an array by using filter function. The array is: [1,2,3,4,5,6,7,8,9,10]. For this exercise, the numbers should be type of integer number

Solution:

```js
function filterEvens(arr) {
  return arr.filter((elem) => {
    return elem % 2 === 0;
  });
}

function main() {
  let ints = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
  console.log(filterEvens(ints));
}

main();
```

---

## Question 43

**Level 1**

Write a program which can map() to make an array whose elements are square of elements in [1,2,3,4,5,6,7,8,9,10]. For this exercise, the array should consist of types of integer numbers.

Solution:

```js
function mapEvens(arr) {
  return arr.map((elem) => {
  return elem ** 2;
  }));
}

function main() {
  let nums = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
  console.log(mapEvens(nums));
}

main();
```

---

## Question 44

**Level 1**

Write a program which can map() and filter() to make an array whose elements are square of even number in [1,2,3,4,5,6,7,8,9,10]. For this exercise, the array should consist of types of integer numbers.

Solution:

```js
function sqrEvens(arr) {
  return arr.filter((ele) => ele % 2 === 0).map((ele) => ele ** 2);
}

function main() {
  let arr = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
  console.log(sqrEvens(arr));
}

main();
```

---

## Question 45

**Level 1**

Write a program that can generate an array containing integers between 1... and n and then filter() that array to return an array whose elements are the even numbers in the original array.

Hints:
In case of input data being supplied to the question, it should be assumed to be a prompt input from a webpage.

Solution:

```js
function evensN(n) {
  let arr = [];
  for (let i = 1; i <= n; i++) {
    arr.push(i);
  }
  return arr.filter((ele) => ele % 2 === 0);
}

function main() {
  console.log(evensN(10));
}

main();
```

---

## Question 46

**Level 1**

Write a program that uses map() to create an array whose elements are square of numbers between 1 and 20 (both included).

Solution:

```js
function squareEv() {
  let arr = [];
  for (let i = 1; i <= 20; i++) {
    arr.push(i);
  }
  return arr.map((elem) => elem ** 2);
}

function main() {
  let squareArr = squareEv();
  console.log(squareArr);
}

main();
```

---

## Question 47

**Level 1**

Define a class named human which has a static method called printEthnicity. Extend it with a class called nationality.

Hints:
static is a keyword used to define static properties and static methods in a class. These are properties and methods that cannot be called on instances of the class, only on the class itself.

Solution:

---

## Question 48

**Level 1**

Add a simple property and method to the prototype of String object.

Hints:

1. Prototypes are the template of an object and contain properties and methods defined for the object template at the point of definition. It provides an easy way of sharing properties and methods for an object.
1. use the .prototype property to do so, and then add a property or method: String.prototype.quality (new property prototype); String.prototype.yell = () {} (new prototype method)
1. If you use an already existent prototype method/property name, you will overwrite the original one

Solution:

```js
String.prototype.quality = "This is a string";
String.prototype.yell = function () {
  return this.toUpperCase();
};

let a = "Menin Aeide";
let b = "Arma virumque";

console.log(a.quality);
console.log(b.quality);

console.log(a.yell());
console.log(b.yell());
```

---

## Question 49

**Level 1**

Use a constructor function as a class to create an object called Colour. The constructor parameters should include r, g, b. Add a method to the object using the prototype. Initialize two instances of this object.

Solution:

```js
function Colour(r, g, b) {
  this.r = r;
  this.g = g;
  this.b = b;
}

Colour.prototype.rgb = function () {
  return `rgb(${this.r}, ${this.g}, ${this.b})`;
};

const red = new Colour(255, 0, 0);
const blue = new Colour(0, 0, 255);
let redRgb = red.rgb();
let blueRgb = blue.rgb();
console.log(red);
console.log(redRgb);
console.log(blue);
console.log(blueRgb);
```

---

## Question 50

**Level 1**

Recreate the object above using the class keyword. Add a method in the constructor to execute automatically

Hints:

1. to execute a method upon instantiation, put it in the constructor method.
1. do not use arrow function syntax in classes or you will not be able to use this
1. For a constructor method, use this syntax: this.method = function () {}
1. For a class method outside the constructor, use method() {}
1. Alternatively for the constructor method, just add the method outside the constructor and then call it within the constructor thus: this.method();

Solution:

```js
class Colour {
  constructor(r, g, b, name) {
    this.r = r;
    this.g = g;
    this.b = b;
    this.name = name;
    this.log = function () {
      console.log(`Colour name: ${this.name}`);
    };
  }

  rgb() {
    return `rgb(${this.r}, ${this.g}, ${this.b})`;
  }
}

const red = new Colour(223, 41, 53, "Rose Madder");
const blue = new Colour(55, 114, 255, "Blue Crayola");

red.log();
blue.log();

redStr = red.rgb();
blueStr = blue.rgb();

console.log(redStr);
console.log(blueStr);
```

---

## Question 51

**Level 1**

Define a class that has a static method and a static property, as well as a public method and a public property.

Note: You can ignore static properties because since ES6, static properties have been deprecated though one can add suport for them through an NPM module or ENV.

Hints:

1. Static methods and static properties belong to the Class ONLY and not to any instance of it.
1. Use the keyword static to create these methods and properties

Solution:

```js
class Food {
  static report() {
    console.log("This is a class that creates classes of type 'Food'");
  }

  constructor(type, weight) {
    this.type = type;
    this.weight = weight;
  }

  sell() {
    console.log(`${this.type} is sold to a hungry client!`);
  }
}

const steak = new Food("meat", 300);

console.log(steak);
steak.sell();

// these work because these are static method & property used on the class
Food.report();

// This does not work because you cannot call a static method on a class instance.
steak.report();
```

---

## Question 52

**Level 1**

Define a Superclass named European and two subclasses, one German, one Italian.
On the superclass, add a constructor, and a class method.
On the German class, add a constructor property called worldWarsStarted. Use super() to extend the constructor of the European Class to the German subclass with its own constructor.
To the Italian subclass add a method that overrides the Superclass method.

Hints:
In super() you need to repeat the parameters you defined in the constructor of the super class because it won't assume them otherwise.

Solution:

```js
class European {
  constructor(name, city) {
    this.name = name;
    this.city = city;
  }

  drink() {
    console.log(`${this.name} drinks alcohol`);
  }
}

class Italian extends European {
  drink() {
    console.log(`${this.name} drinks wine`);
  }
}

class German extends European {
  constructor(name, age, worldWarsStarted = 2) {
    super(name, age);
    this.worldWarsStarted = worldWarsStarted;
  }
  eats() {
    console.log(`${this.name} eats sausage`);
  }
}

let keziah = new European("Keziah", "Hamrun");
console.log(keziah.name);
console.log(keziah.city);
keziah.drink();

let fabio = new Italian("Fabio", "Roma");
console.log(fabio.name);
console.log(fabio.city);
fabio.drink();

let gunther = new German("Gunther", "Berlin");
console.log(gunther.name);
console.log(gunther.city);
console.log(gunther.worldWarsStarted);
gunther.drink();
gunther.eats();
```

---

## Question 53

**Level 1**

Define a class named Circle which can be constructed by a radius. The Circle class has a method which can compute the area.

Solution:

```js
class Circle {
  constructor(radius) {
    this.radius = radius;
  }
  area() {
    return `${Math.PI * this.radius ** 2}`;
  }
}

let circleA = new Circle(5);
let circleARadius = circleA.area();
console.log(circleARadius);
```

---

## Question 54

**Level 1**

Define a class named Rectangle which can be constructed by a length and width. The Rectangle class has a method which can compute the area.

Solution:

```js
class Rectangle {
  constructor(length, breadth) {
    this.length = length;
    this.breadth = breadth;
  }
  area() {
    return `${this.length * this.breadth}`;
  }
}

let rectA = new Rectangle(5, 10);
let rectAArea = rectA.area();
console.log(rectAArea);
```

---

## Question 55

**Level 1**

Define a class named Shape and its subclass Square. The Square class has a constructor function which takes a length and breadth as argument. Both classes have a area function which can print the area of the shape where Shape's area is 0 by default.

Hints:
To override a method in super class, we can define a method with the same name in the subclass.

Solution:

```js
class Shape {
  area() {
    return 0;
  }
}

class Square extends Shape {
  constructor(length, breadth) {
    super();
    this.length = length;
    this.breadth = breadth;
  }
  area() {
    return `${this.length * this.breadth}`;
  }
}

let shap = new Shape();
let sq = new Square(5, 10);

console.log(shap.area());
console.log(sq.area());
```

---

## Question 56

**Level 1**

Create a new promise and chain .then() and .catch() methods to it. The new promise should call some other function and resolve or reject on the basis of the returned value from that function.

Hint:

1. The promise does not need parentheses to be called.
1. resolve(parameter) works like the return of a function except that the value it returns (if any) will be returned if the promise is resolved. You can only pass one argument to resolve(). To pass multiple values, pass an object as an argument
1. reject(parameter) works like the return of a function except that the value it returns (if any) will be returned if the promise is rejected
1. Regardless of whatever you want returned by resolve(parameter) or reject(parameter) (if any), this parameter must be defined in then() and catch() IF YOU WANT TO USE THAT RETURNED VALUE IN THEN AND CATCH:

```js
let x = new Promise((resolve, reject) => {
  if (itRains === true) {
    resolve(true);
  } else {
    reject(false);
  }
});

x.then((buul) => {
  console.log(`It is ${buul} that it is raining`);
}).catch((buul) => {
  console.log(`It is ${buul} that it is raining`);
});
```

Solution:

```js
testEvens = new Promise((resolve, reject) => {
  let n = Math.round(Math.random() * 10);
  let isItEven = assEvens(n);
  if (isItEven) {
    resObj = { val: true, n: n };
    resolve(resObj);
  } else {
    resObj = { val: false, n: n };
    reject(resObj);
  }
})
  .then((resObj) => console.log(`It is ${resObj.val} that ${resObj.n} is even`))
  .catch((resObj) =>
    console.log(`It is ${resObj.val} that ${resObj.n} is even`)
  );

function assEvens(n) {
  return n % 2 === 0;
}

function main() {
  testEvens;
}

main();
```

---

## Question 57

**Level 1**

Refactor the Promise in the previous question so that it is returned to a function. Then execute the function with .then() and .catch() methods appended to it.

Solution:

```js
function testEvens() {
  return new Promise((resolve, reject) => {
    let n = Math.round(Math.random() * 10);
    let isItEven = assEvens(n);
    if (isItEven) {
      resObj = { val: true, n: n };
      resolve(resObj);
    } else {
      resObj = { val: false, n: n };
      reject(resObj);
    }
  });
}

function assEvens(n) {
  return n % 2 === 0;
}

function main() {
  testEvens()
    .then((resObj) =>
      console.log(`It is ${resObj.val} that ${resObj.n} is even`)
    )
    .catch((resObj) =>
      console.log(`It is ${resObj.val} that ${resObj.n} is even`)
    );
}

main();
```

---

## Question 58

**Level 1**

Create a promise that resolves or rejects depending on a random value. Return the value to the promise as an argument in resolve() or reject() and pass it to the then() and catch() methods and output it as part of the callback function of then() or catch().

Hints:
Pass the value as an argument to the resolve() and reject() functions, which will then return it to then() or catch() as the case may be (don't forget to specify the returned value as a parameter in then() and catch()). Example: resolve(x) reject(x) and .then(x) .catch(x);

Solution:

```js
function randProm() {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      let x = Math.random();
      x <= 0.5 ? resolve(x) : reject(x);
    }, 1000);
  });
}

function main() {
  randProm()
    .then((x) => {
      console.log(`Success! ${x}`);
    })
    .catch((x) => {
      console.log(`Fail! ${x}`);
    });
}

main();
```

---

## Question 59

**Level 1**

Raise a TypeError exception. use a try-catch block to catch it.

Hints:

1. Use throw new TypeError() to raise the exception. You can pass a message as an argument if you wish: throw new TypeError("Incorrect type of variable")
1. errors are objects that come with their own properties and methods. In this case, you can these properties: TypeError.name, TypeError.message;
1. When the new instance of the error is thrown, it is returned to catch-block but you should pass it as an argument to catch(error) if you want to use it in that block
1. You can use console.log() or console.error() to print out the Exception properties in the catch-block

Solution:

```js
function add2(a, b) {
  if (typeof a !== "number" || typeof b !== "number") {
    throw new TypeError("Incorrect type of variable");
  }
  return a + b;
}

function main() {
  let a = "hello",
    b = 10;
  try {
    console.log(add2(a, b));
  } catch (err) {
    console.error(`${err.name}: ${err.message}`);
  } finally {
    console.log("function is executed");
  }
}

main();
```

---

## Question 60

**Level 1**

Create your own exception. Define own properties and methods for it. Pass it to the catch-block and use those properties and methods in the catch-block

Solution:

```js
function sqrNum(n) {
  if (isNaN(n)) {
    throw new MyException(n);
  }
  return n ** 2;
}

function MyException(n) {
  this.message = `${n} is not a number`;
  this.value = n;
  this.sqrError = function () {
    console.log(`Squaring this value gives us ${n}${n}`);
  };
}

function main() {
  let y = 4 * "hello";
  let testArr = [1, "name", 3, 4, y];
  for (let item of testArr) {
    try {
      console.log(sqrNum(item));
    } catch (err) {
      console.log(
        `Exception message is: ${err.message} and the value is: ${err.value}`
      );
      err.sqrError();
    } finally {
      console.log(`${item} has been tested`);
    }
  }
}

main();
```

---

## Question 61

Write a function to return something that causes an exception and use try/except to catch the exception.

Solution:

```js
function divvyUp() {
  return 5 / "Hello"();
}

function main() {
  try {
    console.log(divvyUp());
  } catch (err) {
    console.log(
      `Value returned from divvyUp() is ${err.value}, and ${err.message}`
    );
  } finally {
    console.log("function complete");
  }
}

main();
```

---

## Question 62

**Level 1**

Define a custom exception class which takes a string message as property.

Hints:
To define a custom exception, we need to define a class extending Error.

Solution:

```js
class PermissionError extends Error {
  constructor(message = `Concessu tibi caret!`) {
    super(message);
    this.name = "CONCESSU_CARET";
    this.message = message;
  }
}

function foundResPublica(nomen) {
  if (nomen !== "Lucius Iunius Brutus") {
    throw new PermissionError(
      "Nisi a Patre Libertatem Res Publica non orienda!"
    );
  }
  governState(nomen);
}

function governState(nomen) {
  console.log(`Tu, ${nomen}, Pater Patriae Rei Publicae iam orta`);
}

function main() {
  let statesmen = ["Lucius Tarquinius Superbus", "Lucius Iunius Brutus"];
  for (let statesman of statesmen) {
    try {
      foundResPublica(statesman);
    } catch (err) {
      console.log(err.message);
    } finally {
      console.log("Sic condita est Roma");
    }
  }
}

main();
```

---

## Question 63

**Level 1**

Assuming that we have some email addresses in the "username@companyname.com" format, please write program to print the user name of a given email address. Both user names and company names are composed of letters only.

Example:
If the following email address is given as input to the program: john@google.com
Then, the output of the program should be: john

Solution:

```js
function returnUserName(email) {
  return email.match(/^(.+)@.+$/)[1];
}

function main() {
  let userOne = "d!rp_r1@google.com";
  console.log(returnUserName(userOne));
}

main();
```

---

## Question 64

**Level 1**

Assuming that we have some email addresses in the "username@companyname.com" format, please write program to print the company name of a given email address. Both user names and company names are composed of letters only.

Example:
If the following email address is given as input to the program: john@google.com
Then, the output of the program should be: google

Solution:

```js
function returnUserName(email) {
  return email.match(/^.+@(\w+).+$/)[1];
}

function main() {
  let userOne = "d!rp_r1@google.com";
  console.log(returnUserName(userOne));
}

main();
```

---

## Question 65

**Level 1**

Write a program which accepts a sequence of words separated by whitespace as input to print the words composed of digits only.

Example:
If the following words is given as input to the program: 2 cats and 3 dogs.
Then, the output of the program should be: ['2', '3']

Solution:

```js
function returnDigits(str) {
  return str.match(/\d/g);
}

function main() {
  let phrase = "2 cats and 3 dogs.";
  console.log(returnDigits(phrase));
}

main();
```

---

## Question 66

**Level 1**

Create an async function.

Hints:
An async function returns a promise without the need to use resolve and reject. The value returned is resolved, while errors are rejected. Use then() and catch() to consume the promise.

Solution:

```js
async function testEvens(n) {
  if (n % 2 !== 0) throw new Error(`Error! ${n} is odd!`);
  return `${n} is even`;
}

function main() {
  let x = Math.round(Math.random() * 100);
  testEvens(x)
    .then((res) => console.log(res))
    .catch((err) => console.log(err.message));
}

main();
```

---

## Question 67

**Level 1**

Create a RegEx pattern dynamically from a supplied variable

Hints:

1. create the pattern using a string literal and put it into a variable
1. Then create a RegExp() object using that variable. These use as a normal RegExp.
1. The new RegExp() object will supply the / / so do not put themn in the string literal.

```js
function confirmEnding(str, target) {
  let tarRegx = new RegExp(`${target}$`);
  return tarRegx.test(str);
}

let x = confirmEnding("Bastian", "n");
console.log(x);
```

---

## Question 68

**Level 1**

A mixin is a function that contains properties and methods that objects, even of a different class, inherit. Define a mixin function from which two objects inherit a common method.

Hints:

1. pass the object as an argument to the mixin function and define obj.function() in the mixin.
1. You can define both properties and methods in a mixin function. That object that is passed into the mixin function will inherit all these properties and methods.

Solution:

```js
class Aeroplane {
  constructor(nomen, role) {
    this.nomen = nomen;
    this.role = role;
  }
  travel() {
    console.log(`${this.nomen}, which is a ${this.role}, roars into the sky`);
  }
}

class Ship {
  constructor(nomen, role) {
    this.nomen = nomen;
    this.role = role;
  }
  travel() {
    console.log(
      `${this.nomen}, which is a ${this.role}, sails out into the sea`
    );
  }
}

function vehicleMixin(obj) {
  obj.color = "grey";
  obj.attack = () => {
    console.log(`${obj.nomen} opens fire with all its weapons`);
  };
  obj.scan = () => {
    console.log(
      `${obj.nomen} scans the environment for enemies with its radar`
    );
  };
}

f16 = new Aeroplane("F-16 Fighting Falcon", "multirole fighter");
arleighBurke = new Ship("Destroyer", "guided missile destroyer");

console.log(f16.nomen);
console.log(f16.role);
console.log(arleighBurke.nomen);
console.log(arleighBurke.role);
f16.travel();
arleighBurke.travel();
vehicleMixin(f16);
vehicleMixin(arleighBurke);
console.log(f16.color);
console.log(arleighBurke.color);
f16.attack();
arleighBurke.attack();
f16.scan();
arleighBurke.scan();
```

---

## Question 69

**Level 1**

Write a program which accepts a sequence of words separated by whitespace as input to print the words composed of digits only.

Example:
If the following words is given as input to the program: 2 cats and 3 dogs.

Then, the output of the program should be: ['2', '3']

Solution:

```js
function pickDigits(arr) {
  let fnd = new RegExp(/\d/g);
  let x = arr.split(" ").filter((ele) => {
    if (fnd.test(ele)) return ele;
  });
  return x;
}

function main() {
  let myArr = "2 cats and 3 dogs.";
  let out = pickDigits(myArr);
  console.log(out);
  return;
}

main();
```

---

## Question 70

**Level 1**

f(n)=f(n-1)+100 when n>0 and f(0)=0 with a given n input by console (n>0).

Example:
If the following n is given as input to the program: 5

Hint:
This is a recursive function with the base case of 0 returning 0

Solution:

```js
function f(n) {
  return n === 0 ? 0 : f(n - 1) + 100;
}

function main() {
  let recF = f(5);
  console.log(recF);
}

main();
```

---

## Question 71

**Level 1**

The Fibonacci Sequence is computed based on the following formula:

1. Base case 1: f(n)=0 if n=0
1. Base case 2: f(n)=1 if n=1
1. Otherwise: f(n)=f(n-1)+f(n-2) if n>1

Write a program to compute the value of f(n) with a given n input by console.

Example: If 7 is given as input to the program, the output should be 13

Hint:
Another recursive function but with two base cases

Solution:

```js
function fib(n) {
  return n === 0 ? 0 : n === 1 ? 1 : fib(n - 1) + fib(n - 2);
}

function main() {
  let recF = fib(7);
  console.log(recF);
}

main();
```

---

## Question 72

**Level 1**

The Fibonacci Sequence is computed based on the following formula:

1. Base case 1: f(n)=0 if n=0
1. Base case 2: f(n)=1 if n=1
1. Otherwise: f(n)=f(n-1)+f(n-2) if n>1

Write a program to compute the value of f(n) with a given n input by console.

Example: If the following 7 is given as the input, the output of the program should be: [0, 1, 1, 2, 3, 5, 8, 13]

Solution:

```js
function fib(n) {
  return n === 0 ? 0 : n === 1 ? 1 : fib(n - 1) + fib(n - 2);
}

function main() {
  let n = 7;
  let fibArr = [];
  for (let i = 0; i <= n; i++) {
    fibArr.push(fib(i));
  }
  console.log(fibArr);
}

main();
```

---

## Question 73

**Level 1**

Write a program using generator to print the even numbers between 0 and n in comma. N is to be delivered as an argument to the generator.

Example:
If the following n is given as input to the program: 10
Then, the output of the program should be: 0,2,4,6,8,10

Hints:
Use yield to produce the next value in generator.

Solution:

```js
function* evenGen(n) {
  for (let i = 0; i <= n; i++) {
    if (i % 2 === 0) {
      yield `${i} is divisible by 2`;
    } else {
      yield `${i} is not divisible by 2`;
    }
  }
}

function main() {
  let n = 10;
  const myGen = evenGen(n);
  let flag = false;
  while (!flag) {
    let getEven = myGen.next();
    !getEven.done ? console.log(getEven.value) : (flag = getEven.done);
  }
}

main();
```

---

## Question 74

**Level 1**

Please write a program using generator to print the numbers which can be divisible by 5 and 7 between 0 and n in comma separated form while n is input by console.

Example:
If the following n is given as input to the program: 100
Then, the output of the program should be: 0,35,70

Solution:

```js
function* gen57(n) {
  for (let i = 0; i <= n; i++) {
    if (i % 5 === 0 && i % 7 === 0) yield i;
  }
}

function main() {
  let n = 100;
  let genObj = gen57(n);
  let arr57 = [];
  let flag = false;
  while (!flag) {
    let get57 = genObj.next();
    !get57.done ? arr57.push(get57.value) : (flag = get57.done);
  }
  console.log(arr57.join(","));
}

main();
```

---

## Question 75

**Level 1**

Please write assert statements to verify that every number in the list [2,4,6,8] is even.

Hints:
use console.assert() which prints "Assertion failed" if it fails, but nothing if it passes

Solution:

```js
function assertArr(arr) {
  arr.forEach((ele) => {
    console.log(`${ele}:`);
    console.assert(ele % 2 === 0);
  });
}

function main() {
  let myArr = [2, 4, 5, 8];
  assertArr(myArr);
}

main();
```

---

## Question 76

**Level 1**

Please write a program that evaluates a basic mathematic expression and prints the evaluation result.

Example:
If the following string is given as input to the program: 35+3
Then, the output of the program should be: 38

Hints:

1. use eval(). Returns the completion value of evaluating the given code. If the completion value is empty, undefined is returned.
1. Warning: Executing JavaScript from a string is an enormous security risk. It is far too easy for a bad actor to run arbitrary code when you use eval(). NEVER use eval()

Solution:

```js
function myEva(n) {
  return eval(n);
}

function main() {
  let evaString = myEva("35 + 3");
  console.log(evaString);
}

main();
```

---
