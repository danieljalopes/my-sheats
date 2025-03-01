Absolutely! Here are 10 Level 1 exercises with learning goals, code snippets for you to complete (with unit tests), and corresponding solution code snippets, in markdown format.

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

**2. Transforming Strings to Uppercase**

* **Learning Goal:** Understand `map()` for data transformation.
* **Exercise: ** Given a list of strings, convert each string to uppercase.
* **Your Code:
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
