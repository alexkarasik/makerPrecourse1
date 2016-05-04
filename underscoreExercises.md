##Underscore exercises

1. Use _.reduce to multiply all the values in an array.


var arr = [5, 10];
var multiply = _.reduce(arr, function (x, y) { return x * y; });

console.log(multiply);

2. Use _.reduce to concatenate all strings in an array.

 		input: ['x','y','z']
 		output: 'xyz'

  var str = ['This', 'Is', 'Sparta'];


  var output = _.reduce(str, function(word1, word2) { return word1 + ' ' + word2; });


  console.log(output);


3. Write a function that takes an array of names and congratulates them. Make sure to use _.reduce as part of the function.

		input: ['Steve', 'Sally', 'George', 'Gina']
		output: 'Congratulations Steve, Sally, George, Gina!'


    var input = ['Steve', 'Sally', 'George', 'Gina'];

  var congrats =  'Congratulations ' +  _.reduce(input, function(x, y) { return  x + ', ' + y; }) + '!';
  //tests
  console.log(congrats);

4. _.pluck takes an object and a property name and returns the property name's value. Write your own version called myPluck.

var bears = [{name: 'papaBear', poridge: 'too hot'}, {name: 'mamaBear', poridge: 'too cold'}, {name: 'babyBear', poridge:'just right'}];

var myPluck = function(obj, propName) {
    var arr = [];
    for (var i = 0; i < obj.length; i++) {
        for (var prop in obj[i]) {
            if (prop === propName)
                arr.push(obj[i][prop]);
        }
    }
    return arr;
};

//tests
console.log(myPluck(bears, 'name'));
console.log(myPluck(bears, 'poridge'));



6. Use _.filter to return all strings in an array that start with the letter 'Z'.

var str = ['zenu', 'jake', 'Zoroastra', 'shh', 'Zap'];

var zeeWord = _.filter(str, function(str) { return  str.charAt(0) === 'Z'; } );

console.log(zeeWord);

7. Use _.where on your farm animals from the lecture slides to return all animals who contain the value 3 at the property name space.

 		input: [ {speak: function(){console.log('My name is ' + name);}, name: "Tiger", space: 7},  
 				{speak: function(){console.log('My name is ' + name);}, name: "Tiger2", space: 1},  
 				{speak: function(){console.log('My name is ' + name);}, name: "Tiger3", space: 3},  
 				{speak: function(){console.log('My name is ' + name);}, name: "Tiger4", space: 3} ]

 		output: [{speak: function, name: "Tiger3", space: 3},  
 				{speak: function(){}, name: "Tiger4", space: 3}]

var input = [ { name: 'Tiger', space: 7}, { name: 'Tiger2', space: 1}, { name: 'Tiger3', space: 3}, { name: 'Tiger4', space: 3} ];

var output = _.where(input, { space: 3 });

console.log(output);
