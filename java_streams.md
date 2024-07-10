# Java Streams
#### Problem
From a list of names, give me the total number of letters in all the names with more than 5 letters
#### Solution
 ```java
 public static int getTotalNumberOfLettersOfNamesLongerThanFive(String... names) {
 	return Stream.of(names)
           .filter(name -> name.length() > 5)  // Filter based on String length
           .mapToInt(String::length)           // Convert to int (length)
           .sum();                             // Sum the lengths
}
```
---
#### Problem
 Flatten this multidimensional collection
 ```java
 public static List<String> transform(List<List<String>> collection) {
	List<String> newCollection = new ArrayList<>();
	for (List<String> subCollection : collection) {
		for (String value : subCollection) {
			newCollection.add(value);
		}
	}
	return newCollection;
}
```
#### Solution
```java
 public static List<String> transform(List<List<String>> collection) {
	List<String> newCollection = new ArrayList<>();
    collection.forEach(l -> l.forEach(newCollection::add));
	return newCollection;
}
```
---
#### Problem
Get the oldest person from the collection
```java
	public static Person getOldestPerson(List<Person> people) {
		Person oldestPerson = new Person("", 0);
		for (Person person : people) {
			if (person.getAge() > oldestPerson.getAge()) {
				oldestPerson = person;
			}
		}
		return oldestPerson;
	}
````
#### Solution
```java
public static Person getOldestPerson(List<Person> people) {
  return people.stream()
          // Use the max method to find the element with the maximum age.
          .max(Comparator.comparingInt(Person::getAge))
          // If a maximum element (oldest person) is found, return it as an Optional<Person>.
          .orElse(new Person("", 0)); // If no person is found (empty list), return an new Person.
}
```
---
#### Problem
Sum all elements of a collection, try to use the reduce operator with identity parameter instead of an IntStream
```java
public static int calculate(List<Integer> numbers) {
		int total = 0;
		for (int number : numbers) {
			total += number;
		}
		return total;
	}
```

#### Solution
```java
public static int calculate(List<Integer> numbers) {
  // Use reduce with an identity parameter of 0 (initial sum).
  return numbers.stream()
      .reduce(0, (sum, number) -> sum + number);
}
}
```
Explanation:
1. Stream Creation: numbers.stream() converts the List to a Stream for processing with Java Stream operations.
2. reduce Operator: .reduce(0, (sum, number) -> sum + number) uses the reduce method to accumulate the sum of all elements.
  - The first argument (0) is the identity parameter. It represents the initial value used for the accumulation (starting sum in this case).
  - The second argument is a lambda expression that defines the accumulation logic.
    - sum: Represents the current accumulated sum.
    - number: Represents the current element from the stream (integer in this case).
    - The lambda expression returns the updated sum (sum + number).

Benefits of using reduce with identity:
- More concise and functional approach compared to a loop.
- Can be easily adapted to handle different collection types (e.g., List<Long> for summing long values).
- Provides flexibility for more complex accumulation logic within the lambda expression.

---
#### Problem
Get the names of all kids under the age of 18
```java
public static Set<String> getKidNames(List<Person> people) {
		Set<String> kids = new HashSet<>();
		for (Person person : people) {
			if (person.getAge() < 18) {
				kids.add(person.getName());
			}
		}
		return kids;
	}
```

#### Solution
```java
public static Set<String> getKidNames(List<Person> people) {
         return people.stream()
      // Filter the stream to include only people under 18 (kids).
      .filter(person -> person.getAge() < 18)
      // Extract the names (String) of each kid (Person) using the getName method reference.
      .map(Person::getName)
      // Collect the extracted names into a Set to avoid duplicates.
      .collect(Collectors.toSet());
	}
}
```
---
#### Problem
Write a method that returns a comma-separated string based on a given list of integers. Each element should be preceded by the letter 'e' if the number is even, and preceded by the letter 'o' if the number is odd. For example, if the input list is (3,44), the output should be 'o3,e44'.

#### Solution
```java
	public String getString(List<Integer> list) {
		return list.stream()
  .map(i -> i % 2 == 0 ? "e" + i : "o" + i)
  .collect(joining(","));
	}
```

