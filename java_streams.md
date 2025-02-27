## Basic Java Stream Exercises (with Unit Tests - No Solutions Provided)

Here are 5 basic Java Stream exercises with learning goals, starting code snippets (without solutions), and JUnit tests for you to validate your answers:

**Basic Operations (Exercises 1-5):**

### 1. Filtering Strings (Goal: Learn `filter()`)

* **Exercise:** Filter strings with length < 5.
* **Snippet:**

    ```java
    import java.util.Arrays;
    import java.util.List;
    import java.util.stream.Collectors;
    import org.junit.jupiter.api.Test;
    import static org.junit.jupiter.api.Assertions.assertEquals;

    public class StreamExercise1 {
        public static List<String> filterShortWords(List<String> words) {
            // Your code here
            return null;
        }

        @Test
        void testFilterShortWords() {
            List<String> words = Arrays.asList("apple", "banana", "cat", "dog", "elephant");
            List<String> result = filterShortWords(words);
            assertEquals(Arrays.asList("cat", "dog"), result);
        }
    }
    ```

### 2. Mapping Integers (Goal: Learn `map()`)

* **Exercise:** Square each number.
* **Snippet:**

    ```java
    import java.util.Arrays;
    import java.util.List;
    import java.util.stream.Collectors;
    import org.junit.jupiter.api.Test;
    import static org.junit.jupiter.api.Assertions.assertEquals;

    public class StreamExercise2 {
        public static List<Integer> squareNumbers(List<Integer> numbers) {
            // Your code here
            return null;
        }

        @Test
        void testSquareNumbers() {
            List<Integer> numbers = Arrays.asList(1, 2, 3, 4, 5);
            List<Integer> result = squareNumbers(numbers);
            assertEquals(Arrays.asList(1, 4, 9, 16, 25), result);
        }
    }
    ```

### 3. Finding Distinct Values (Goal: Learn `distinct()`)

* **Exercise:** Remove duplicates.
* **Snippet:**

    ```java
    import java.util.Arrays;
    import java.util.List;
    import java.util.stream.Collectors;
    import org.junit.jupiter.api.Test;
    import static org.junit.jupiter.api.Assertions.assertEquals;

    public class StreamExercise3 {
        public static List<Integer> getDistinctNumbers(List<Integer> numbers) {
            // Your code here
            return null;
        }

        @Test
        void testGetDistinctNumbers() {
            List<Integer> numbers = Arrays.asList(1, 2, 2, 3, 4, 4, 5);
            List<Integer> result = getDistinctNumbers(numbers);
            assertEquals(Arrays.asList(1, 2, 3, 4, 5), result);
        }
    }
    ```

### 4. Limiting Results (Goal: Learn `limit()`)

* **Exercise:** Get first 3 numbers > 10.
* **Snippet:**

    ```java
    import java.util.Arrays;
    import java.util.List;
    import java.util.stream.Collectors;
    import org.junit.jupiter.api.Test;
    import static org.junit.jupiter.api.Assertions.assertEquals;

    public class StreamExercise4 {
        public static List<Integer> getFirstThreeGreaterThanTen(List<Integer> numbers) {
            // Your code here
            return null;
        }

        @Test
        void testGetFirstThreeGreaterThanTen() {
            List<Integer> numbers = Arrays.asList(12, 5, 15, 8, 20, 11);
            List<Integer> result = getFirstThreeGreaterThanTen(numbers);
            assertEquals(Arrays.asList(12, 15, 20), result);
        }
    }
    ```

### 5. Skipping Elements (Goal: Learn `skip()`)

* **Exercise:** Skip first 2 strings.
* **Snippet:**

    ```java
    import java.util.Arrays;
    import java.util.List;
    import java.util.stream.Collectors;
    import org.junit.jupiter.api.Test;
    import static org.junit.jupiter.api.Assertions.assertEquals;

    public class StreamExercise5 {
        public static List<String> skipFirstTwo(List<String> words) {
            // Your code here
            return null;
        }

        @Test
        void testSkipFirstTwo() {
            List<String> words = Arrays.asList("one", "two", "three", "four", "five");
            List<String> result = skipFirstTwo(words);
            assertEquals(Arrays.asList("three", "four", "five"), result);
        }
    }
    ```
