**Level 4: Advanced Stream Operations - Complex Scenarios**

**1. Flattening Nested Lists**

* **Learning Goal:** Understand `flatMap()` for flattening nested collections.
* **Exercise:** Given a list of lists of integers, flatten it into a single list.
* **Your Code:**

    ```java
    import java.util.Arrays;
    import java.util.List;
    import java.util.stream.Collectors;
    import org.junit.jupiter.api.Test;
    import static org.junit.jupiter.api.Assertions.assertEquals;

    class StreamExercisesLevel4 {
        public static List<Integer> flattenNestedList(List<List<Integer>> nestedList) {
            // Your code here
            return null; // Replace with your implementation
        }

        @Test
        void testFlattenNestedList() {
            List<List<Integer>> input = Arrays.asList(Arrays.asList(1, 2), Arrays.asList(3, 4, 5), Arrays.asList(6));
            List<Integer> expected = Arrays.asList(1, 2, 3, 4, 5, 6);
            assertEquals(expected, flattenNestedList(input));
        }
    }
    ```

* **Solution:**

    ```java
    public static List<Integer> flattenNestedList(List<List<Integer>> nestedList) {
        return nestedList.stream()
                .flatMap(List::stream)
                .collect(Collectors.toList());
    }
    ```

**2. Finding the Second Highest Number**

* **Learning Goal:** Combine `sorted()`, `distinct()`, and `skip()` for complex ordering.
* **Exercise:** Given a list of integers, find the second highest number.
* **Your Code:**

    ```java
    import java.util.Arrays;
    import java.util.List;
    import java.util.OptionalInt;
    import org.junit.jupiter.api.Test;
    import static org.junit.jupiter.api.Assertions.assertEquals;

    class StreamExercisesLevel4 {
        public static OptionalInt findSecondHighest(List<Integer> numbers) {
            // Your code here
            return OptionalInt.empty(); // Replace with your implementation
        }

        @Test
        void testFindSecondHighest() {
            List<Integer> input = Arrays.asList(1, 5, 2, 9, 3, 9);
            assertEquals(OptionalInt.of(5), findSecondHighest(input));
        }
    }
    ```

* **Solution:**

    ```java
    import java.util.Comparator;
    public static OptionalInt findSecondHighest(List<Integer> numbers) {
        return numbers.stream()
                .distinct()
                .sorted(Comparator.reverseOrder())
                .skip(1)
                .findFirst();
    }
    ```

**3. Grouping by Multiple Properties**

* **Learning Goal:** Use `groupingBy()` with multiple classifiers.
* **Exercise:** Given a list of `Person` objects (with city and age), group them by city and then by age.
* **Your Code:**

    ```java
    import java.util.Arrays;
    import java.util.List;
    import java.util.Map;
    import java.util.stream.Collectors;
    import org.junit.jupiter.api.Test;
    import static org.junit.jupiter.api.Assertions.assertEquals;

    class StreamExercisesLevel4 {
        static class Person {
            String city;
            int age;

            Person(String city, int age) {
                this.city = city;
                this.age = age;
            }
        }

        public static Map<String, Map<Integer, List<Person>>> groupPeopleByCityAndAge(List<Person> people) {
            // Your code here
            return null; // Replace with your implementation
        }

        @Test
        void testGroupPeopleByCityAndAge() {
            List<Person> input = Arrays.asList(new Person("London", 30), new Person("Paris", 25), new Person("London", 25));
            // Define expected result here
            assertEquals(true, groupPeopleByCityAndAge(input).size() > 0); // basic test
        }
    }
    ```

* **Solution:**

    ```java
    public static Map<String, Map<Integer, List<Person>>> groupPeopleByCityAndAge(List<Person> people) {
        return people.stream()
                .collect(Collectors.groupingBy(person -> person.city, Collectors.groupingBy(person -> person.age)));
    }
    ```

**4. Finding the Longest Word in Each Group**

* **Learning Goal:** Combine `groupingBy()` with `max()` and `Comparator`.
* **Exercise:** Given a list of strings, group them by their first letter and find the longest word in each group.
* **Your Code:**

    ```java
    import java.util.Arrays;
    import java.util.List;
    import java.util.Map;
    import java.util.Optional;
    import java.util.stream.Collectors;
    import org.junit.jupiter.api.Test;
    import static org.junit.jupiter.api.Assertions.assertEquals;

    class StreamExercisesLevel4 {
        public static Map<Character, Optional<String>> findLongestWordInGroups(List<String> words) {
            // Your code here
            return null; // Replace with your implementation
        }

        @Test
        void testFindLongestWordInGroups() {
            List<String> input = Arrays.asList("apple", "banana", "ant", "cherry", "cat");
            // define expected result here.
            assertEquals(true, findLongestWordInGroups(input).size() > 0); // basic test
        }
    }
    ```

* **Solution:**

    ```java
    import java.util.Comparator;
    public static Map<Character, Optional<String>> findLongestWordInGroups(List<String> words) {
        return words.stream()
                .collect(Collectors.groupingBy(word -> word.charAt(0),
                        Collectors.maxBy(Comparator.comparingInt(String::length))));
    }
    ```

**5. Calculating the Average of Each Group**

* **Learning Goal:** Combine `groupingBy()` with `averagingInt()`.
* **Exercise:** Given a list of `Person` objects (with city and age), calculate the average age for each city.
* **Your Code:**

    ```java
    import java.util.Arrays;
    import java.util.List;
    import java.util.Map;
    import java.util.stream.Collectors;
    import org.junit.jupiter.api.Test;
    import static org.junit.jupiter.api.Assertions.assertEquals;

    class StreamExercisesLevel4 {
        static class Person {
            String city;
            int age;

            Person(String city, int age) {
                this.city = city;
                this.age = age;
            }
        }

        public static Map<String, Double> calculateAverageAgeByCity(List<Person> people) {
            // Your code here
            return null; // Replace with your implementation
        }

        @Test
        void testCalculateAverageAgeByCity() {
            List<Person> input = Arrays.asList(new Person("London", 30), new Person("Paris", 25), new Person("London", 25));
            // define expected result here.
            assertEquals(true, calculateAverageAgeByCity(input).size() > 0); // basic test.
        }
    }
    ```

* **Solution:**

    ```java
    public static Map<String, Double> calculateAverageAgeByCity(List<Person> people) {
        return people.stream()
                .collect(Collectors.groupingBy(person -> person.city, Collectors.averagingInt(person -> person.age)));
    }
    ```

**6. Partitioning by a Complex Condition**

* **Learning Goal:** Use `partitioningBy()` with a complex predicate.
* **Exercise:** Given a list of strings, partition them into two lists: one with palindromes and one with non-palindromes.
* **Your Code:**

    ```java
    import java.util.Arrays;
    import java.util.List;
    import java.util.Map;
    import java.util.stream.Collectors;
    import org.junit.jupiter.api.Test;
    import static org.junit.jupiter.api.Assertions.assertEquals;

    class StreamExercisesLevel4 {
        public static Map<Boolean, List<String>> partitionPalindromes(List<String> words) {
            // Your code here
            return null; // Replace with your implementation
    }

        @Test
        void testPartitionPalindromes() {
            List<String> input = Arrays.asList("level", "hello", "madam", "world");
            // define expected result here.
            assertEquals(true, partitionPalindromes(input).size() > 0); // basic test.
        }
        private static boolean isPalindrome(String s) {
            return new StringBuilder(s).reverse().toString().equals(s);
        }
    }
    ```

* **Solution:**

    ```java
    public static Map<Boolean, List<String>> partitionPalindromes(List<String> words) {
        return words.stream()
                .collect(Collectors.partitioningBy(StreamExercisesLevel4::isPalindrome));
    }
    ```

**7. Grouping with Custom Reduction**

* **Learning Goal:** Use `groupingBy()` with a custom `reducing()` collector.
* **Exercise:** Given a list of `Person` objects (with name and age), group them by age and find the oldest person in each age group.
* **Your Code:**

    ```java
    import java.util.Arrays;
    import java.util.List;
    import java.util.Map;
    import java.util.Optional;
    import java.util.stream.Collectors;
    import org.junit.jupiter.api.Test;
    import static org.junit.jupiter.api.Assertions.assertEquals;

    class StreamExercisesLevel4 {
        static class Person {
            String name;
            int age;

            Person(String name, int age) {
                this.name = name;
                this.age = age;
            }
        }

        public static Map<Integer, Optional<Person>> findOldestPersonByAge(List<Person> people) {
            // Your code here
            return null; // Replace with your implementation
        }

        @Test
        void testFindOldestPersonByAge() {
            List<Person> input = Arrays.asList(new Person("Alice", 30), new Person("Bob", 25), new Person("Charlie", 30));
            // define expected result here.
            assertEquals(true, findOldestPersonByAge(input).size() > 0); // basic test.
        }
    }
    ```

* **Solution:**

    ```java
    import java.util.Comparator;
    public static Map<Integer, Optional<Person>> findOldestPersonByAge(List<Person> people) {
        return people.stream()
                .collect(Collectors.groupingBy(person -> person.age,
                        Collectors.reducing(Collectors.maxBy(Comparator.comparingInt(person -> person.age)))));
    }
    ```

**8. Finding the Most Frequent Element**

* **Learning Goal:** Combine `groupingBy()`, `counting()`, and `max()` for frequency analysis.
* **Exercise:** Given a list of integers, find the most frequent element.
* **Your Code:**

    ```java
    import java.util.Arrays;
    import java.util.List;
    import java.util.OptionalInt;
    import java.util.stream.Collectors;
    import org.junit.jupiter.api.Test;
    import static org.junit.jupiter.api.Assertions.assertEquals;

    class StreamExercisesLevel4 {
        public static OptionalInt findMostFrequentElement(List<Integer> numbers) {
            // Your code here
            return OptionalInt.empty(); // Replace with your implementation
        }

        @Test
        void testFindMostFrequentElement() {
            List<Integer> input = Arrays.asList(1, 2, 2, 3, 3, 3, 4, 4);
            assertEquals(OptionalInt.of(3), findMostFrequentElement(input));
        }
    }
    ```

* **Solution:**

    ```java
    import java.util.Map;
    public static OptionalInt findMostFrequentElement(List<Integer> numbers) {
        return numbers.stream()
                .collect(Collectors.groupingBy(n -> n, Collectors.counting()))
                .entrySet().stream()
                .max(Map.Entry.comparingByValue())
                .map(Map.Entry::getKey)
                .mapToInt(Integer::intValue)
                .findFirst();
    }
    ```

**9. Calculating the Cumulative Sum**

* **Learning Goal:** Use `reduce()` for cumulative calculations.
* **Exercise:** Given a list of integers, calculate the cumulative sum of the list.
* **Your Code:**

    ```java
    import java.util.Arrays;
    import java.util.List;
    import java.util.stream.Collectors;
    import org.junit.jupiter.api.Test;
    import static org.junit.jupiter.api.Assertions.assertEquals;

    class StreamExercisesLevel4 {
        public static List<Integer> calculateCumulativeSum(List<Integer> numbers) {
            // Your code here
            return null; // Replace with your implementation
        }

        @Test
        void testCalculateCumulativeSum() {
            List<Integer> input = Arrays.asList(1, 2, 3, 4, 5);
            List<Integer> expected = Arrays.asList(1, 3, 6, 10, 15);
            assertEquals(expected, calculateCumulativeSum(input));
        }
    }
    ```

* **Solution:**

    ```java
    import java.util.ArrayList;
    public static List<Integer> calculateCumulativeSum(List<Integer> numbers) {
        List<Integer> cumulativeSum = new ArrayList<>();
        numbers.stream().reduce(0, (a, b) -> {
            cumulativeSum.add(a + b);
            return a + b;
        });
        return cumulativeSum;
    }
    ```

**10. Grouping by a Range**

* **Learning Goal:** Use `groupingBy()` with a custom range classifier.
* **Exercise:** Given a list of integers, group them into ranges: 0-10, 11-20, 21-30, etc.
* **Your Code:**

    ```java
    import java.util.Arrays;
    import java.util.List;
    import java.util.Map;
    import java.util.stream.Collectors;
    import org.junit.jupiter.api.Test;
    import static org.junit.jupiter.api.Assertions.assertEquals;

    class StreamExercisesLevel4 {
        public static Map<String, List<Integer>> groupNumbersByRange(List<Integer> numbers) {
            // Your code here
            return null; // Replace with your implementation
        }

        @Test
        void testGroupNumbersByRange() {
            List<Integer> input = Arrays.asList(5, 12, 25, 8, 18, 32);
            // define expected result here.
            assertEquals(true, groupNumbersByRange(input).size() > 0); // basic test.
        }
    }
    ```

* **Solution:**

    ```java
    public static Map<String, List<Integer>> groupNumbersByRange(List<Integer> numbers) {
        return numbers.stream()
                .collect(Collectors.groupingBy(n -> {
                    int range = (n / 10) * 10;
                    return range + "-" + (range + 9);
                }));
    }
    ```
