## JavaScript Cheat Sheet :)

[Comments](#comments)
[Variables](#variables)
[Conditional statements](#conditional-statements)
[Loops](#loops)
[Strings](#strings)
[Arrays](#arrays)
[Functions](#functions)

#### Comments
```js
/* mutliline
comment */

// singleline comment
```

#### Variables
```js
var entree = 'Enchiladas'; // pre ES6
let name = 'Eve';
const greetings = 'Hello!';
typeof greetings;      // String
```
#### Comparison
```js
10 < 12 // true
'apples' === 'oranges' // false
10 == '10' // true
10 === '10' // false
```

#### List of falsy values
* 0
* Empty strings like "" or ''
* `null` which represent when there is no value at all
* `undefined` which represent when a declared variable lacks a value
* `NaN`, or Not a Number

#### Short circuit evaluation
```js
if (username) {
  defaultName = username;
} else {
  defaultName = 'Stranger';
}

let defaultName = username || 'Stranger';
```

#### Ternary operator
```js
isNightTime ? console.log('Turn on the lights!') : console.log('Turn off the lights!');
```

#### Conditional statements
```js
if (false) {
  console.log('The code in this block will not run.');
} else {
  console.log('But the code in this block will!');
}
```
```js
let stopLight = 'yellow';

if (stopLight === 'red') {
  console.log('Stop!');
} else if (stopLight === 'yellow') {
  console.log('Slow down.');
} else if (stopLight === 'green') {
  console.log('Go!');
} else {
  console.log('Caution, unknown!');
}
```
```js
let groceryItem = 'papaya';

switch (groceryItem) {
  case 'tomato':
    console.log('Tomatoes are $0.49');
    break;
  case 'lime':
    console.log('Limes are $1.49');
    break;
  case 'papaya':
    console.log('Papayas are $1.29');
    break;
  default:
    console.log('Invalid item');
    break;
}
```

#### Loops
```js
for (let counter =5; counter < 11; counter++) {
  console.log(counter);
}
```

```js

let bobsFollowers = ['Joe', 'Marta', 'Sam', 'Erin'];
let tinasFollowers = ['Sam', 'Marta', 'Elle'];
let mutualFollowers = [];

for (let i = 0; i < bobsFollowers.length; i++) {
  for (let j = 0; j < tinasFollowers.length; j++) {
    if (bobsFollowers[i] === tinasFollowers[j]) {
      mutualFollowers.push(bobsFollowers[i]);
    }
  }
};
```
```js
let counterTwo = 1;
while (counterTwo < 4) {
  console.log(counterTwo);
  counterTwo++;
}
```
```js
let cupsAdded = 0;

do {
 cupsAdded++
} while (cupsAdded < 3);

```

#### Strings
```js
'ahoj'.length;            // 4
'hello'.toUpperCase();    // 'HELLO'
'Miss'.toLowerCase();     // 'miss'
'Hey'.endsWith('i');      // false
'Hey'.startsWith('H');    // true
'   text   '.trim();      // 'text'
```

```js
const myPet = 'armadillo';
console.log(`I own a pet ${myPet}.`);
```

```js
var str = "Apple, Banana, Kiwi";
str.slice(7, 13);         // Banana
str.slice(-12, -6);       // Banana
str.slice(7);             // Banana, Kiwi
str.slice(-12);           // Banana, Kiwi
str.substring(7, 13);     // Banana
str.substr(7, 6);         // Banana
str.substr(7);            // Banana, Kiwi
str.substr(-4);           // Kiwi     
```

```js
var txt = "a,b,c,d,e";   // String
txt.split(",");          // [a,b,c,d,e]
```

```js
str = "Please visit Microsoft and Microsoft!";
str.replace("Microsoft", "W3Schools"); // Please visit W3Schools and Microsoft!
str.replace(/Microsoft/g, "W3Schools"); // Please visit W3Schools and W3Schools!
```


#### Random
```js
Math.random();    // random number between 0 and 1
```
* [Faker.js](https://github.com/marak/Faker.js/)


#### Math
```js
Math.ceil(43.8);     // 44
Math.floor(43.8);    // 43
Math.round(43.8);    // 44

```

```js
parseInt("10");            // returns 10
parseFloat("10.33");       // returns 10.33
Number.isInteger(2017);    // true
(123).toString()           // '123'
```

```js
var x = 9.656;
x.toFixed(0);           // returns 10
x.toFixed(2);           // returns 9.66
x.toFixed(4);           // returns 9.6560
x.toFixed(6);           // returns 9.656000

x.toPrecision();        // returns 9.656
x.toPrecision(2);       // returns 9.7
x.toPrecision(4);       // returns 9.656
x.toPrecision(6);       // returns 9.65600
```
#### Arrays
```js
var fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.length;          // 4
fruits.toString();      // Banana,Orange,Apple,Mango
fruits.join(' * ' );    // Banana * Orange * Apple * Mango
fruits.pop();           // 'Mango', removes last element
fruits.push("Kiwi");    // 5 (returns new array length), add element to array
fruits.shift();         // 'Banana', removes first element
fruits.unshift("Lemon"); // 5 (returns new aray length), add element at the beginning
fruits[0];              // Banana
["Emil", "Tobias", "Linus"];
fruits.concat(['Lemon', 'Kiwi'])  // merging two arrays
fruits.slice(1, 3) // ['Orange', 'Apple']
fruits.slice(3) // ['Mango']
```

```js
var fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.sort();        // First sort the elements of fruits 
fruits.reverse();     // Then reverse the order of the elements
```

#### Iterators
```js
const artists = ['Picasso', 'Kahlo', 'Matisse', 'Utamaro'];

artists.forEach(artist => {
  console.log(artist + ' is one of my favorite artists.');
});
```

```js
const things = ['desk', 'chair', 5, 'backpack', 3.14, 100];

const onlyNumbers = things.filter(thing => {
  return typeof thing === 'number';
});
```

```js
const numbers = [1, 2, 3, 4, 5];

const squareNumbers = numbers.map(number => {
  return number * number;
});
```

```js
const animals = ['hippo', 'tiger', 'lion', 'seal', 'cheetah', 'monkey', 'salamander', 'elephant'];

const foundAnimal = animals.findIndex(animal => animal === 'elephant');
console.log(foundAnimal)
```

```js
const numbers = [1, 2, 4, 10];

const summedNums = numbers.reduce((accumulator, currentValue) => {
  return accumulator + currentValue
})
```

```js
const numbers = [1, 2, 4, 10];

const summedNums = numbers.reduce((accumulator, currentValue) => {
  return accumulator + currentValue
}, 100)  // <- Second argument for .reduce()

console.log(summedNums); // Output: 117
```

```js
var array = [1, 2, 3, 4, 5];

var even = function(element) {
  // checks whether an element is even
  return element % 2 === 0;
};

console.log(array.some(even));
// expected output: true
```

```js
function isBelowThreshold(currentValue) {
  return currentValue < 40;
}

var array1 = [1, 30, 39, 29, 10, 13];

console.log(array1.every(isBelowThreshold));
// expected output: true
```

#### Functions
```js
function greeting (name = 'stranger') {
  console.log(`Hello, ${name}!`)
}

greeting('Nick') // Output: Hello, Nick!
greeting() // Output: Hello, stranger!
```
##### Function expresssions
```js
const plantNeedsWater = function(day) {
  if(day === 'Wednesday'){
    return true;
  } else {
    return false;
  }
};

plantNeedsWater('Tuesday');
```
##### Arrow functions
```js
const rectangleArea = (width, height) => {
  let area = width * height;
  return area
}

const squareNum = num => num * num;

```

```js
const logVisibleLightWaves = () => {
  let lightWaves = 'Moonlight';
	let region = 'The Arctic';
  // Add if statement here:
  if (region === 'The Arctic') {
    let lightWaves = 'Northern Lights'
  	console.log(lightWaves); // 'Northern Lights'
  }
  console.log(lightWaves); // 'Moonlight'
};

logVisibleLightWaves();
```

#### Objects
```js
let spaceship = {
  homePlanet: 'Earth',
  color: 'silver'
};
spaceship.homePlanet; // Returns 'Earth',
spaceship['color']; // Returns 'silver',

spaceship.speed = 'Mach 5';
spaceship['color'] = 'blue';
delete spaceship.mission;  // Removes the mission property
```

```js
const alienShip = {
  retreat () { 
    console.log('We no longer wish to conquer your planet. It is full of dogs, which we do not care for.')
  },
  takeOff() {
    console.log('Spim... Borp... Glix... Blastoff!')
  }
};
```

```js
for (let crewMember in spaceship.crew) {
  console.log(`${crewMember}: ${spaceship.crew[crewMember].name}`)
};
```

```js
function robotFactory(model, mobile){
  return {
    model,
    mobile,
    beep() {
      console.log('Beep Boop');
    }
  }
}

const newRobot = robotFactory('P-501', false)
```
```js
const vampire = {
  name: 'Dracula',
  residence: 'Transylvania',
  preferences: {
    day: 'stay inside',
    night: 'satisfy appetite'
  }
};

const { name } = vampire;
const { day } = vampire.preferences;
```

```js
const robot = {
	model: 'SAL-1000',
  mobile: true,
  sentient: false,
  armor: 'Steel-plated',
  energyLevel: 75
};

// What is missing in the following method call?
const robotKeys = Object.keys(robot);

console.log(robotKeys);

// Declare robotEntries below this line:
const robotEntries = Object.entries(robot)
console.log(robotEntries);

// Declare newRobot below this line:
const newRobot = Object.assign({laserBlaster: true, voiceRecognition: true}, robot);

console.log(newRobot);
```


#### Classes
```js
class Dog {
  constructor(name) {
    this._name = name;
    this._behavior = 0;
  }

  get name() {
    return this._name;
  }
  get behavior() {
    return this._behavior;
  }   

  incrementBehavior() {
    this._behavior ++;
  }
}
const halley = new Dog('Halley');
```

```js
class Animal {
  constructor(name) {
    this._name = name;
    this._behavior = 0;
  }

  get name() {
    return this._name;
  }

  get behavior() {
    return this._behavior;
  }

  incrementBehavior() {
    this._behavior++;
  }
} 


class Cat extends Animal {
  constructor(name, usesLitter) {
    super(name);
    this._usesLitter = usesLitter;
  }
}

const bryceCat = new Cat('Bryce', false);
```

```js
class Animal {
  constructor(name) {
    this._name = name;
    this._behavior = 0;
  }

  static generateName() {
    const names = ['Angel', 'Spike', 'Buffy', 'Willow', 'Tara'];
    const randomNumber = Math.floor(Math.random()*5);
    return names[randomNumber];
  }
}
Animal.generateName(); // returns a name
```


#### Imports
##### airplane.js
```js
let Airplane = {};

Airplane.myAirplane = "StarJet";

module.exports = Airplane;
```

##### missionControl.js
```js
const Airplane = require('./airplane.js');
```
---
##### airplane.js
```js
module.exports = {
  myAirplane: "CloudJet", 
  displayAirplane: function() {
    return this.myAirplane;
  }
};
```

##### missionControl.js
```js
const Airplane = require('./airplane.js');
```
---
##### airplane.js
```js
let Airplane = {};

Airplane.availableAirplanes = [
{
  name: 'AeroJet',
  fuelCapacity: 800
 }, 
 {name: 'SkyJet',
  fuelCapacity: 500
 }
];

export default Airplane;
```

##### missionControl.js
```js
import Airplane from './airplane';
```

---
#### Named export
##### airplane.js
```js
let specialty = '';
function isVegetarian() {
}; 
function isLowSodium() {
}; 

export { specialty, isVegetarian };
```

##### missionControl.js
```js
import { specialty, isVegetarian } from './menu';
```
---
#### Export named export
##### airplane.js
```js
let specialty = '';
function isVegetarian() {
}; 
function isLowSodium() {
}; 

export { specialty, isVegetarian };
```

##### missionControl.js
```js
import { specialty, isVegetarian } from 'menu';
```
---
#### Export as
##### airplane.js
```js
 let specialty = '';
let isVegetarian = function() {
}; 
let isLowSodium = function() {
}; 

export { specialty as chefsSpecial, isVegetarian as isVeg, isLowSodium };
```

##### missionControl.js
```js
import { chefsSpecial, isVeg } from './menu';

// or 
import * as Carte from './menu';

Carte.chefsSpecial;
Carte.isVeg();
Carte.isLowSodium();
```

#### Promises
```js
const inventory = {
  sunglasses: 0
};

const myExecutor = (resolve, reject) => {
  if (inventory.sunglasses > 0) {
      resolve('Sunglasses order processed.');
  } else {
      reject('That item is sold out.'); 
  }
}

const orderSunglasses = () => {
return new Promise(myExecutor);
}
```

```js
let prom = new Promise((resolve, reject) => {
  let num = Math.random();
  if (num < .5 ){
    resolve('Yay!');
  } else {
    reject('Ohhh noooo!');
  }
});

const handleSuccess = (resolvedValue) => {
  console.log(resolvedValue);
};

const handleFailure = (rejectionReason) => {
  console.log(rejectionReason);
};

prom.then(handleSuccess, handleFailure);
```

```js
prom
  .then((resolvedValue) => {
    console.log(resolvedValue);
  })
  .catch((rejectionReason) => {
    console.log(rejectionReason);
  });
```

```js

checkInventory(order)
.then((resolvedValueArray) => {
  return processPayment(resolvedValueArray);
})
.then((resolvedValueArray) => {
  return shipOrder(resolvedValueArray);
})
.then((successMessage) => {
  console.log(successMessage);
});
```

```js
let myPromises = Promise.all([returnsPromOne(), returnsPromTwo(), returnsPromThree()]);

myPromises
  .then((arrayOfValues) => {
    console.log(arrayOfValues);
  })
  .catch((rejectionReason) => {
    console.log(rejectionReason);
  });
```