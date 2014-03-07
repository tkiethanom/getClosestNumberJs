getClosestNumberJs
==================

Recursive function that takes in an array of numbers and finds the one closest to the entered number

```
function getClosestValue(number_array, value){
	if(number_array.length > 1){
		var left = number_array.slice(0, Math.ceil(number_array.length / 2));
		var right = number_array.slice(Math.ceil(number_array.length / 2), number_array.length);

		var leftVal = getClosestValue(left, value);
		var rightVal = getClosestValue(right, value);

		if(leftVal == null){
			return rightVal;
		}
		if(rightVal == null){
			return leftVal;
		}
		if(Math.abs(value - leftVal) < Math.abs(value - rightVal)){
			return leftVal;
		}
		else{
			return rightVal;
		}
	}
	else if(number_array.length == 1){
		return number_array[0];
	}
	else{
		return null;
	}
}
```
