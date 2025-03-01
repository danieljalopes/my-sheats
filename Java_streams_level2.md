**Level 2: Transformations and Reductions - Intermediate Operations**

**1. Sum of Squares**

* **Learning Goal:** Understand `map()` and `reduce()` for calculations.
* **Exercise:** Given a list of integers, calculate the sum of their squares.
* **Your Code:**

    ```java
    import java.util.List;
    import org.junit.jupiter.api.Test;
    import static org.junit.jupiter.api.Assertions.assertEquals;

    class StreamExercisesLevel2 {

        public static int sumOfSquares(List<Integer> numbers) {
            // Your code here
            return 0; // Replace with your implementation
        }

        @Test
        void testSumOfSquares() {
            List<Integer> input = List.of(1, 2, 3);
            assertEquals(14, sumOfSquares(input));
        }
    }
    ```

* **Solution:**

    ```java
    public static int sumOfSquares(List<Integer> numbers) {
        return numbers.stream()
                .map(n -> n * n)
                .reduce(0, Integer::sum);
    }
    ```

**2. Finding the Maximum Value**

* **Learning Goal:** Understand `max()` and `Optional` handling.
* **Exercise:** Given a list of integers, find the maximum value.
* **Your Code:**

    ```java
    import java.util.List;
    import java.util.OptionalInt;
    import org.junit.jupiter.api.Test;
    import static org.junit.jupiter.api.Assertions.assertEquals;

    class StreamExercisesLevel2 {

        public static OptionalInt findMaxValue(List<Integer> numbers) {
            // Your code here
            return OptionalInt.empty(); // Replace with your implementation
        }

        @Test
        void testFindMaxValue() {
            List<Integer> input = List.of(10, 5, 20, 15);
            assertEquals(OptionalInt.of(20), findMaxValue(input));
        }
    }
    ```

* **Solution:**

    ```java
    public static OptionalInt findMaxValue(List<Integer> numbers) {
        return numbers.stream().mapToInt(Integer::intValue).max();
    }
    ```

**3. Sorting and Limiting**

* **Learning Goal:** Understand `sorted()` and `limit()`.
* **Exercise:** Given a list of integers, sort them in descending order and take the top 3 values.
* **Your Code:**

    ```java
    import java.util.Collections;
    import java.util.List;
    import java.util.stream.Collectors;
    import org.junit.jupiter.api.Test;
    import static org.junit.jupiter.api.Assertions.assertEquals;

    class StreamExercisesLevel2 {

        public static List<Integer> sortAndLimit(List<Integer> numbers) {
            // Your code here
            return null; // Replace with your implementation
        }

        @Test
        void testSortAndLimit() {
            List<Integer> input = List.of(5, 1, 9, 3, 7, 2);
            List<Integer> expected = List.of(9, 7, 5);
            assertEquals(expected, sortAndLimit(input));
        }
    }
    ```

* **Solution:**

    ```java
    public static List<Integer> sortAndLimit(List<Integer> numbers) {
        return numbers.stream()
                .sorted(Collections.reverseOrder())
                .limit(3)
                .collect(Collectors.toList());
    }
    ```

**4. Calculating Average**

* **Learning Goal:** Understand `average()` and `OptionalDouble` handling.
* **Exercise:** Given a list of integers, calculate the average.
* **Your Code:**

    ```java
    import java.util.List;
    import java.util.OptionalDouble;
    import org.junit.jupiter.api.Test;
    import static org.junit.jupiter.api.Assertions.assertEquals;

    class StreamExercisesLevel2 {

        public static OptionalDouble calculateAverage(List<Integer> numbers) {
            // Your code here
            return OptionalDouble.empty(); // Replace with your implementation
        }

        @Test
        void testCalculateAverage() {
            List<Integer> input = List.of(1, 2, 3, 4, 5);
            assertEquals(OptionalDouble.of(3.0), calculateAverage(input));
        }
    }
    ```

* **Solution:**

    ```java
    public static OptionalDouble calculateAverage(List<Integer> numbers) {
        return numbers.stream().mapToInt(Integer::intValue).average();
    }
    ```

**5. Finding the Longest String**

* **Learning Goal:** Understand `max()` with `Comparator`.
* **Exercise:** Given a list of strings, find the longest string.
* **Your Code:**

    ```java
    import java.util.List;
    import java.util.Optional;
    import org.junit.jupiter.api.Test;
    import static org.junit.jupiter.api.Assertions.assertEquals;

    class StreamExercisesLevel2 {

        public static Optional<String> findLongestString(List<String> strings) {
            // Your code here
            return Optional.empty(); // Replace with your implementation
        }

        @Test
        void testFindLongestString() {
            List<String> input = List.of("apple", "banana", "kiwi", "strawberry");
            assertEquals(Optional.of("strawberry"), findLongestString(input));
        }
    }
    ```

* **Solution:**

    ```java
    public static Optional<String> findLongestString(List<String> strings) {
        return strings.stream().max((s1, s2) -> Integer.compare(s1.length(), s2.length()));
    }
    ```

    **6. Skip and Limit**

* **Learning goal:** Understand how to use `skip` and `limit` together.
* **Exercise:** Given a list of numbers, skip the first 2, and then limit the result to the next 3.
* **Your code:**

    ```java
    import java.util.List;
    import java.util.stream.Collectors;
    import org.junit.jupiter.api.Test;
    import static org.junit.jupiter.api.Assertions.assertEquals;

    class StreamExercisesLevel2 {
        public static List<Integer> skipAndLimit(List<Integer> numbers) {
            return null;
        }

        @Test
        void testSkipAndLimit(){
            List<Integer> input = List.of(1,2,3,4,5,6,7,8);
            List<Integer> expected = List.of(3,4,5);
            assertEquals(expected, skipAndLimit(input));
        }
    }
    ```

* **Solution:**

    ```java
    public static List<Integer> skipAndLimit(List<Integer> numbers) {
        return numbers.stream().skip(2).limit(3).collect(Collectors.toList());
    }
    ```

**7. Distinct Sorted**

* **Learning goal:** Use `distinct` and `sorted`.
* **Exercise:** given a list of integers, return a sorted list containing only the distinct integers.
* **Your Code:**

    ```java
    import java.util.List;
    import java.util.stream.Collectors;
    import org.junit.jupiter.api.Test;
    import static org.junit.jupiter.api.Assertions.assertEquals;

    class StreamExercisesLevel2 {
        public static List<Integer> distinctSorted(List<Integer> numbers){
            return null;
        }

        @Test
        public void testDistinctSorted(){
            List<Integer> input = List.of(5,1,3,1,2,5,4);
            List<Integer> expected = List.of(1,2,3,4,5);
            assertEquals(expected, distinctSorted(input));
        }
    }
    ```

* **Solution:**

    ```java
    public static List<Integer> distinctSorted(List<Integer> numbers){
        return numbers.stream().distinct().sorted().collect(Collectors.toList());
    }
    ```

**8. Joining Strings with a Delimiter**

* **Learning Goal:** Understand `Collectors.joining()` for string concatenation.
* **Exercise:** Given a list of strings, join them into a single string with a comma as a delimiter.
* **Your Code:**

    ```java
    import java.util.List;
    import java.util.stream.Collectors;
    import org.junit.jupiter.api.Test;
    import static org.junit.jupiter.api.Assertions.assertEquals;

    class StreamExercisesLevel2 {

        public static String joinStrings(List<String> strings) {
            // Your code here
            return null; // Replace with your implementation
        }

        @Test
        void testJoinStrings() {
            List<String> input = List.of("apple", "banana", "cherry");
            assertEquals("apple,banana,cherry", joinStrings(input));
        }
    }
    ```

* **Solution:**

    ```java
    public static String joinStrings(List<String> strings) {
        return strings.stream().collect(Collectors.joining(","));
    }
    ```

**9. Finding the Product of Numbers**

* **Learning Goal:** Use `reduce()` to perform multiplication.
* **Exercise:** Given a list of integers, find the product of all the numbers.
* **Your Code:**

    ```java
    import java.util.List;
    import org.junit.jupiter.api.Test;
    import static org.junit.jupiter.api.Assertions.assertEquals;

    class StreamExercisesLevel2 {

        public static int productOfNumbers(List<Integer> numbers) {
            // Your code here
            return 0; // Replace with your implementation
        }

        @Test
        void testProductOfNumbers() {
            List<Integer> input = List.of(2, 3, 4);
            assertEquals(24, productOfNumbers(input));
        }
    }
    ```

* **Solution:**

    ```java
    public static int productOfNumbers(List<Integer> numbers) {
        return numbers.stream().reduce(1, (a, b) -> a * b);
    }
    ```

**10. Finding the Shortest String**

* **Learning Goal:** Use `min()` with `Comparator`.
* **Exercise:** Given a list of strings, find the shortest string.
* **Your Code:**

    ```java
    import java.util.List;
    import java.util.Optional;
    import org.junit.jupiter.api.Test;
    import static org.junit.jupiter.api.Assertions.assertEquals;

    class StreamExercisesLevel2 {

        public static Optional<String> findShortestString(List<String> strings) {
            // Your code here
            return Optional.empty(); // Replace with your implementation
        }

        @Test
        void testFindShortestString() {
            List<String> input = List.of("apple", "banana", "kiwi", "a");
            assertEquals(Optional.of("a"), findShortestString(input));
        }
    }
    ```

* **Solution:**

    ```java
    public static Optional<String> findShortestString(List<String> strings) {
        return strings.stream().min((s1, s2) -> Integer.compare(s1.length(), s2.length()));
    }
    ```
