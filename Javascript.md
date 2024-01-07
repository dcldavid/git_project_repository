# Key Learnings From My JavaScript Journey

## Table of Contents

### Array Methods

#### `.filter()` and `.test()` methods

1. On [This Codewars Kata](https://www.codewars.com/kata/583203e6eb35d7980400002a/train/javascript) I learned:

- The `.filter()` method is a way to be able to select a series of specific array items
- The `.test()` method is used specifically for **strings**. You need to pass the filter output (using your REGEX function) into the test with the parameters of the call-back function or you won't be able to test for the strings. It's output is true / false boolean type and it will be applied to each instance of the array. ChatGPT had a really nice description of this:

For the code: ``

> The .test() method in JavaScript is indeed supposed to return a boolean value indicating whether the pattern matches the provided string. It returns true if there's a match and false otherwise.
>
> In your function, .test() is used within the filter() method. The filter() method creates a new array with all elements that pass the test implemented by the provided function.
>
> The confusion might arise from how .test() is being used in conjunction with .filter() and .length.
>
> Let's break it down:
>
> .filter(x => /^[:;][-~]?[)D]$/.test(x)) applies the regex pattern ^[:;][-~]?[)D]$ to each element (x) in the array (arr). It returns a new array containing only those elements that match the pattern.
> .length is then applied to this filtered array, giving the count of elements that matched the pattern.
> .test() returns true or false, but when used within .filter(), it works to filter the elements of the array based on whether the regex pattern matches each individual element. The resulting array contains only those elements that match the pattern, and .length gives the count of those matching elements.
>
> So, the .test() method returns a boolean value (true or false) for each element in the array, and .filter() creates a new array with only the elements that return true from the .test() method, which is then used to find the length of the filtered array.
>
> If you're still having trouble understanding or if there's something specific you'd like to clarify, feel free to ask!
>
> User
> So when you run the .test() method the array is mutated to only include true and false values prior to it being passed to the .length method?
> ChatGPT
> Actually, the original array (arr) remains unchanged throughout this process. Let me clarify the sequence of operations:
>
> Filtering using .filter():
>
> The .filter() method creates a new array by iterating over each element of the original arr and applying the regex test (/^[:;][-~]?[)D]$/) using .test().
> The .test() method returns true or false for each element in arr based on whether it matches the pattern.
> Elements that match the pattern (true from .test()) are included in the new array returned by .filter().
> Calculating the length:
>
> The .length property is used on the array resulting from .filter().
> This gives the count of elements that matched the regex pattern in the original arr.
> The original arr is not mutated; rather, the .filter() method creates a new array based on the condition specified (/^[:;][-~]?[)D]$/) without changing the original array.
>
> So, .test() doesn't mutate the original array; instead, it filters the elements of the array and then .length calculates the number of elements that passed the test (matched the pattern) in the new array created by .filter().

2. I did another really interesting [codewars Kata](https://www.codewars.com/kata/523f5d21c841566fde000009/solutions/javascript) that compared two arrays to each other and asked to remove any values found in the second array from the first array. I was able to use the `.filter()` method along with the `.includes()` method to search for all of the values that matched inside the arrays.

### String Methods

#### `.replace()`

The `.replace()` method allows you to search a particular string for a regex or other combination of search terms and then can provide a callback function that allows you to mutate or change the particular replaced value. It was really powerful in this example here: [Codewars Kata](https://www.codewars.com/kata/5208f99aee097e6552000148/solutions/javascript).
