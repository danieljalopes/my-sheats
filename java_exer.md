Got it! Here are the 20 Java Stream exercises, each with a clear learning goal:

Basic Operations (Exercises 1-5):

Filtering Strings (Goal: Learn filter()):

Exercise: Given a list of strings, filter out the strings with a length less than 5 and print the results.
Goal: Understand how to use the filter() operation to selectively process elements based on a condition.
Mapping Integers (Goal: Learn map()):

Exercise: Given a list of integers, square each number and print the results.
Goal: Learn how to use the map() operation to transform elements from one type to another.
Finding Distinct Values (Goal: Learn distinct()):

Exercise: Given a list of integers with duplicates, print only the distinct (unique) values.
Goal: Learn how to remove duplicate elements from a stream using distinct().
Limiting Results (Goal: Learn limit()):

Exercise: Given a list of integers, print the first 3 numbers that are greater than 10.
Goal: Understand how to use limit() to restrict the number of elements processed by a stream.
Skipping Elements (Goal: Learn skip()):

Exercise: Given a list of strings, skip the first 2 strings and print the remaining ones.
Goal: Learn how to use skip() to discard a specified number of elements from the beginning of a stream.
Intermediate Operations (Exercises 6-12):

Combining Filters (Goal: Learn combining predicates):

Exercise: Given a list of integers, filter out the even numbers that are also greater than 10.
Goal: Learn how to combine multiple filter conditions using logical operators within a stream pipeline.
Mapping and Filtering (Goal: Learn chaining operations):

Exercise: Given a list of strings, convert them to lowercase, then filter out the strings that contain the letter "e".
Goal: Understand how to chain multiple stream operations together in a pipeline.
Finding Any Match (Goal: Learn anyMatch()):

Exercise: Given a list of strings, check if any string contains the substring "test".
Goal: Learn how to use anyMatch() to check if at least one element in a stream satisfies a given condition.
Checking All Matches (Goal: Learn allMatch()):

Exercise: Given a list of integers, check if all numbers are positive.
Goal: Learn how to use allMatch() to check if all elements in a stream satisfy a given condition.
Finding the First Element (Goal: Learn findFirst()):

Exercise: Given a list of strings, find and print the first string that starts with the letter "b".
Goal: Learn how to use findFirst() to retrieve the first element that matches a given condition.
Sorting in Reverse (Goal: Learn sorted() with comparators):

Exercise: Given a list of integers, sort them in descending order and print the results.
Goal: Learn how to use sorted() with a custom comparator to sort elements in a specific order.
Joining Strings (Goal: Learn Collectors.joining()):

Exercise: Given a list of strings, concatenate them into a single string, separated by commas.
Goal: Learn how to use Collectors.joining() to combine string elements into a single string.
Advanced Operations (Exercises 13-20):

Grouping by Length (Goal: Learn Collectors.groupingBy()):

Exercise: Given a list of strings, group them by their length and print the groups.
Goal: Learn how to use Collectors.groupingBy() to group elements based on a classification function.
Partitioning by Condition (Goal: Learn Collectors.partitioningBy()):

Exercise: Given a list of integers, partition them into two lists: one containing even numbers and the other containing odd numbers.
Goal: Learn how to use Collectors.partitioningBy() to divide elements into two groups based on a predicate.
Calculating Sum of Squares (Goal: Learn mapToInt() and sum()):

Exercise: Given a list of integers, calculate the sum of the squares of all the numbers.
Goal: Learn how to use mapToInt() to convert a stream to an IntStream and then use sum() to calculate the sum.
Finding the Longest String (Goal: Learn reduce() with custom logic):

Exercise: Given a list of strings, find and print the longest string.
Goal: Learn how to use reduce() with a custom accumulator to find the maximum or minimum element based on a specific criteria.
Flat Mapping (Goal: Learn flatMap()):

Exercise: Given a list of lists of strings, flatten the list and print all the individual strings.
Goal: Learn how to use flatMap() to flatten a stream of collections into a single stream.
Custom Collector (Goal: Learn Collector.of()):

Exercise: Create a custom collector that calculates the product of all integers in a stream.
Goal: Learn how to create custom collectors using Collector.of() to perform specific aggregation operations.
Stream of Objects (Goal: Learn stream operations on custom objects):

Exercise: Given a list of Employee objects (with name and salary attributes), find the employees with the highest salary.
Goal: Learn how to use stream operations on custom objects and extract specific attributes.
Parallel Streams (Goal: Learn parallel streams and performance considerations):

Exercise: Given a large list of integers, calculate the sum of all numbers using a parallel stream and compare its performance with a sequential stream.
Goal: Understand how to use parallel streams to improve performance and learn about the factors that affect parallel stream performance.
