Absolutely! Here are 10 Level 1 exercises with learning goals, code snippets for you to complete (with unit tests), and corresponding solution code snippets

**Level 1: Foundations - Basic Stream Operations**

**1. Filtering Even Numbers**

* **Learning Goal:** Understand `stream()`, `filter()`, and `forEach()`.
* **Exercise:** Given a list of integers, filter out and return only the even numbers.
* **Your Code (Complete the `filterEvenNumbers` method):**

    ```java
    import java.util.List;
    import java.util.stream.Collectors;
    import org.junit.jupiter.api.Test;
    import static org.junit.jupiter.api.Assertions.assertEquals;

    class StreamExercisesLevel1 {

        public static List<Integer> filterEvenNumbers(List<Integer> numbers) {
            // Your code here
            return null; // Replace with your implementation
        }

        @Test
        void testFilterEvenNumbers() {
            List<Integer> input = List.of(1, 2, 3, 4, 5, 6);
            List<Integer> expected = List.of(2, 4, 6);
            assertEquals(expected, filterEvenNumbers(input));
        }
    }
    ```

* **Solution Code:**

    ```java
    public static List<Integer> filterEvenNumbers(List<Integer> numbers) {
        return numbers.stream()
                .filter(n -> n % 2 == 0)
                .collect(Collectors.toList());
    }
    ```

**2. Transforming Strings to Uppercase**

* **Learning Goal:** Understand `map()` for data transformation.
* **Exercise:** Given a list of strings, convert each string to uppercase.
* **Your Code:**

    ```java
    public static List<String> transformToUppercase(List<String> strings) {
        // Your code here
        return null; // Replace with your implementation
    }

    @Test
    void testTransformToUppercase() {
        List<String> input = List.of("apple", "banana", "cherry");
        List<String> expected = List.of("APPLE", "BANANA", "CHERRY");
        assertEquals(expected, transformToUppercase(input));
    }
    ```

* **Solution Code:**

    ```java
    public static List<String> transformToUppercase(List<String> strings) {
        return strings.stream()
                .map(String::toUpperCase)
                .collect(Collectors.toList());
    }
    ```

**3. Counting Elements**

* **Learning Goal:** Understand the `count()` terminal operation.
* **Exercise:** Given a list of strings, count the number of strings.
* **Your Code:**

    ```java
    public static long countStrings(List<String> strings) {
        // Your code here
        return 0; // Replace with your implementation
    }

    @Test
    void testCountStrings() {
        List<String> input = List.of("apple", "banana", "cherry");
        assertEquals(3, countStrings(input));
    }
    ```

* **Solution Code:**

    ```java
    public static long countStrings(List<String> strings) {
        return strings.stream().count();
    }
    ```

**4. Filtering Strings by Length**

* **Learning Goal:** Combine `filter()` with a condition based on string length.
* **Exercise:** Given a list of strings, filter out and return strings with length greater than 5.
* **Your Code:**

    ```java
    public static List<String> filterStringsByLength(List<String> strings) {
        // Your code here
        return null; // Replace with your implementation
    }

    @Test
    void testFilterStringsByLength() {
        List<String> input = List.of("apple", "banana", "kiwi", "grape");
        List<String> expected = List.of("banana", "grape");
        assertEquals(expected, filterStringsByLength(input));
    }
    ```

* **Solution Code:**

    ```java
    public static List<String> filterStringsByLength(List<String> strings) {
        return strings.stream()
                .filter(s -> s.length() > 5)
                .collect(Collectors.toList());
    }
    ```

**5. Extracting First Characters**

* **Learning Goal:** Use `map()` to extract specific information from objects (strings).
* **Exercise:** Given a list of strings, extract the first character of each string.
* **Your Code:**

    ```java
    public static List<Character> extractFirstCharacters(List<String> strings) {
        // Your code here
        return null; // Replace with your implementation
    }

    @Test
    void testExtractFirstCharacters() {
        List<String> input = List.of("apple", "banana", "cherry");
        List<Character> expected = List.of('a', 'b', 'c');
        assertEquals(expected, extractFirstCharacters(input));
    }
    ```

* **Solution Code:**

    ```java
    public static List<Character> extractFirstCharacters(List<String> strings) {
        return strings.stream()
                .map(s -> s.charAt(0))
                .collect(Collectors.toList());
    }
    ```

    **6. Filtering Numbers Greater Than a Value**

* **Learning Goal:** Use `filter()` with a numerical comparison.
* **Exercise:** Given a list of integers, filter out and return numbers greater than 10.
* **Your Code:**

    ```java
    public static List<Integer> filterNumbersGreaterThanTen(List<Integer> numbers) {
        // Your code here
        return null; // Replace with your implementation
    }

    @Test
    void testFilterNumbersGreaterThanTen() {
        List<Integer> input = List.of(5, 12, 8, 15, 9);
        List<Integer> expected = List.of(12, 15);
        assertEquals(expected, filterNumbersGreaterThanTen(input));
    }
    ```

* **Solution Code:**

    ```java
    public static List<Integer> filterNumbersGreaterThanTen(List<Integer> numbers) {
        return numbers.stream()
                .filter(n -> n > 10)
                .collect(Collectors.toList());
    }
    ```

**7. Mapping Numbers to Their Doubles**

* **Learning Goal:** Simple numerical mapping using `map()`.
* **Exercise:** Given a list of integers, map each number to its double.
* **Your Code:**

    ```java
    public static List<Integer> doubleNumbers(List<Integer> numbers) {
        // Your code here
        return null; // Replace with your implementation
    }

    @Test
    void testDoubleNumbers() {
        List<Integer> input = List.of(1, 2, 3);
        List<Integer> expected = List.of(2, 4, 6);
        assertEquals(expected, doubleNumbers(input));
    }
    ```

* **Solution Code:**

    ```java
    public static List<Integer> doubleNumbers(List<Integer> numbers) {
        return numbers.stream()
                .map(n -> n * 2)
                .collect(Collectors.toList());
    }
    ```

**8. Filtering Strings that Contain a Character**

* **Learning Goal:** Using `filter()` with `String.contains()`.
* **Exercise:** Given a list of strings, filter out and return strings that contain the letter 'a'.
* **Your Code:**

    ```java
    public static List<String> filterStringsContainingA(List<String> strings) {
        // Your code here
        return null; // Replace with your implementation
    }

    @Test
    void testFilterStringsContainingA() {
        List<String> input = List.of("apple", "banana", "kiwi", "grape");
        List<String> expected = List.of("apple", "banana", "grape");
        assertEquals(expected, filterStringsContainingA(input));
    }
    ```

* **Solution Code:**

    ```java
    public static List<String> filterStringsContainingA(List<String> strings) {
        return strings.stream()
                .filter(s -> s.contains("a"))
                .collect(Collectors.toList());
    }
    ```

**9. Filtering Distinct Numbers**

* **Learning Goal:** Using `distinct()`.
* **Exercise:** Given a list of Integers, return a list of only the distinct Integers.
* **Your Code:**

```java
    public static List<Integer> distinctNumbers(List<Integer> numbers){
        //your code here
        return null;
    }

    @Test
    public void testDistinctNumbers(){
        List<Integer> input = List.of(1,1,2,3,4,4,5);
        List<Integer> expected = List.of(1,2,3,4,5);
        assertEquals(expected, distinctNumbers(input));
    }
```

```java
public static List<Integer> distinctNumbers(List<Integer> numbers){
        return numbers.stream().distinct().collect(Collectors.toList());
    }
```

**10. Finding Strings Starting with a Specific Letter**

* **Learning Goal:** Combining `filter()` with `String.startsWith()`.
* **Exercise:** Given a list of strings and a letter, filter out and return strings that start with the given letter (case-sensitive).
* **Your Code:**

```java
    public static List<String> findStringsStartingWith(List<String> strings, String letter) {
        // Your code here
        return null; // Replace with your implementation
    }

    @Test
    void testFindStringsStartingWith() {
        List<String> input = List.of("apple", "banana", "ant", "cherry", "apricot");
        List<String> expected = List.of("apple", "ant", "apricot");
        assertEquals(expected, findStringsStartingWith(input, "a"));
    }
```

* **Solution Code:**
```java

public static List<String> findStringsStartingWith(List<String> strings, String letter) {
        return strings.stream()
                .filter(s -> s.startsWith(letter))
                .collect(Collectors.toList());
    }
```
