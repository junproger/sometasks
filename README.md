# sometasks

A some tasks for JavaScript

1. Write a method / function that accepts an array of cities as input. As a result, it returns a string where cities are separated by commas, and there is a period at the end.
Example:
"Moscow, St. Petersburg, Voronezh."
1.      Написать метод/функцию, который/которая на вход принимает массив городов. В качестве результата возвращает строку, где города разделены запятыми, а в конце стоит точка. 
Пример:
«Москва, Санкт-Петербург, Воронеж.» 

The solution: 

function listofCities(input) {
	let output = input.join(', ') + '.';
	return output;
	}

2. Write a method / function, which / which takes a number (float) as input, and at the output receives a number rounded to fives.
Example:
27 => 25, 27.8 => 30, 41.7 => 40.
2.      Написать метод/функцию, который/которая на вход принимает число (float), а на выходе получает число, округленное до пятерок.

The solution: 

function toFive(input) {
	let output = 0;
	let five = (input/5).toFixed();
		output = (five*5);
	return output;
	}

3. Write a method / function that accepts a number (int) as input, and outputs the word "computer" in the case corresponding to the specified number. For example, "25 computers", "41 computers", "1048 computers" (in russian).
3.      Написать метод/функцию, который/которая на вход принимает число (int), а на выходе выдает слово “компьютер” в падеже, соответствующем указанному количеству. Например, «25 компьютеров», «41 компьютер», «1048 компьютеров». 

The solution: 

function computer(input) {
	let output = "компьютер";
	let end = input.toString().slice(-1);
		if (input>10&&input<15) {
				output += "ов";
				return output;
				}
		else if (end === '1') {
			output;
			}
		else if (end>'1'&&end<'5') {
			output += "а";
			} 
		else {
			output += "ов";
			}
	return output;
	}

4. Write a method / function, which / which takes an integer as input, and at the output returns whether the number is prime (has no divisors except 1 and itself).
4.      Написать метод/функцию, который/которая на вход принимает целое число, а на выходе возвращает то, является ли число простым (не имеет делителей кроме 1 и самого себя). 

The solution: 

function checkPrime(num) {
let prime = "Число простое";
	if (num <= 1|| num === undefined) {
	return false;
	}
	else if (num === 2) {
		return prime;
		} else {
		for (let i = 2; i < num; i++) {
			if (num % i === 0) {
			return false;
			}
		}
		return prime;
		}
	}

5. Write a method that determines which elements are present in duplicate in each of the arrays (= in two or more, and in each). Two arrays are fed into the input. The output is an array with the required matches.
Example:
[7, 17, 1, 9, 1, 17, 56, 56, 23], [56, 17, 17, 1, 23, 34, 23, 1, 8, 1]
Outlet [1, 17]
5.      Написать метод, который определяет, какие элементы присутствуют в двух экземплярах в каждом из массивов (= в двух и более, причем в каждом). На вход подаются два массива. На выходе массив с необходимыми совпадениями.
Пример:
[7, 17, 1, 9, 1, 17, 56, 56, 23], [56, 17, 17, 1, 23, 34, 23, 1, 8, 1]
На выходе [1, 17] 

The solution: 

function compareItems(arrayA, arrayB) {
	let counter = 0;
	let starter = 0;
	let sameItems = [];
	let arrayC = arrayA;
	let runner = (arrayC.length-1);
			function execute() {
				while (starter < runner) {
					if (arrayC[starter] === arrayC[runner]) {
							sameItems.push(arrayC[starter]);
							counter +=1;
					}
					runner -=1;
					}
				starter +=1;
				runner = (arrayC.length-1)
			}
			arrayC.forEach(execute);
	starter = 0;
	arrayC = arrayB;
	runner = (arrayC.length-1);
			arrayC.forEach(execute);
	starter = 0;
	arrayC = sameItems;
	sameItems = [];
	runner = (arrayC.length-1);
	counter = 0;
			arrayC.forEach(function() {
					while (starter < runner) {
						if (arrayC[starter] === arrayC[runner]) {
							if (sameItems.includes(arrayC[starter]) === false) {
								sameItems.push(arrayC[starter]);
								counter +=1;
								}
							}
					runner -=1;	
						}
				starter +=1;
				runner = (arrayC.length-1)
			});
			console.log(counter + ' - ' + sameItems);
	return sameItems;
	}

The full JS code for this solution is here: https://github.com/PythonProger/twotwice
