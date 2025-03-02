**Level 3: Grouping and Partitioning - Advanced Collections**

**1. Grouping Strings by Length**

* **Learning Goal:** Understand `Collectors.groupingBy()`.
* **Exercise:** Given a list of strings, group them by their length into a `Map<Integer, List<String>>`.
* **Your Code:**

    ```java
    import java.util.List;
    import java.util.Map;
    import org.junit.jupiter.api.Test;
    import static org.junit.jupiter.api.Assertions.assertEquals;
    import java.util.stream.Collectors;
    class StreamExercisesLevel3 {

        public static Map<Integer, List<String>> groupStringsByLength(List<String> strings) {
            // Your code here
            return null; // Replace with your implementation
        }

        @Test
        void testGroupStringsByLength() {
            List<String> input = List.of("apple", "banana", "cat", "dog", "kiwi");
            Map<Integer, List<String>> expected = Map.of(3, List.of("cat", "dog"), 5, List.of("apple", "kiwi"), 6, List.of("banana"));
            assertEquals(expected, groupStringsByLength(input));
        }
    }
    ```

* **Solution:**

    ```java
    public static Map<Integer, List<String>> groupStringsByLength(List<String> strings) {
        return strings.stream().collect(Collectors.groupingBy(String::length));
    }
    ```

**2. Partitioning Numbers by Even/Odd**

* **Learning Goal:** Understand `Collectors.partitioningBy()`.
* **Exercise:** Given a list of integers, partition them into even and odd lists using `partitioningBy()`.
* **Your Code:**

    ```java
    import java.util.List;
    import java.util.Map;
    import org.junit.jupiter.api.Test;
    import static org.junit.jupiter.api.Assertions.assertEquals;
    import java.util.stream.Collectors;
    class StreamExercisesLevel3 {

        public static Map<Boolean, List<Integer>> partitionEvenOdd(List<Integer> numbers) {
            // Your code here
            return null; // Replace with your implementation
        }

        @Test
        void testPartitionEvenOdd() {
            List<Integer> input = List.of(1, 2, 3, 4, 5, 6);
            Map<Boolean, List<Integer>> expected = Map.of(false, List.of(1, 3, 5), true, List.of(2, 4, 6));
            assertEquals(expected, partitionEvenOdd(input));
        }
    }
    ```

* **Solution:**

    ```java
    public static Map<Boolean, List<Integer>> partitionEvenOdd(List<Integer> numbers) {
        return numbers.stream().collect(Collectors.partitioningBy(n -> n % 2 == 0));
    }
    ```

**3. Counting Word Frequencies**

* **Learning Goal:** Combine `groupingBy()` with `counting()`.
* **Exercise:** Given a list of words, count the frequency of each word.
* **Your Code:**

    ```java
    import java.util.List;
    import java.util.Map;
    import org.junit.jupiter.api.Test;
    import static org.junit.jupiter.api.Assertions.assertEquals;
    import java.util.stream.Collectors;
    class StreamExercisesLevel3 {

        public static Map<String, Long> countWordFrequencies(List<String> words) {
            // Your code here
            return null; // Replace with your implementation
        }

        @Test
        void testCountWordFrequencies() {
            List<String> input = List.of("apple", "banana", "apple", "cherry", "banana", "apple");
            Map<String, Long> expected = Map.of("apple", 3L, "banana", 2L, "cherry", 1L);
            assertEquals(expected, countWordFrequencies(input));
        }
    }
    ```

* **Solution:**

    ```java
    public static Map<String, Long> countWordFrequencies(List<String> words) {
        return words.stream().collect(Collectors.groupingBy(s -> s, Collectors.counting()));
    }
    ```

**4. Grouping by First Letter**

* **Learning goal:** Use grouping by with a string function.
* **Your code:**

    ```java
    import java.util.List;
    import java.util.Map;
    import java.util.stream.Collectors;
    import org.junit.jupiter.api.Test;
    import static org.junit.jupiter.api.Assertions.assertEquals;
    class StreamExercisesLevel3 {
        public static Map<Character, List<String>> groupStringsByFirstLetter(List<String> strings){
            return null;
        }
        @Test
        public void testGroupStringsByFirstLetter(){
            List<String> input = List.of("apple","ant","banana","cherry","cat");
            Map<Character, List<String>> expected = Map.of('a',List.of("apple","ant"),'b',List.of("banana"),'c',List.of("cherry","cat"));
            assertEquals(expected, groupStringsByFirstLetter(input));
        }
    }
    ```

* **Solution:**

    ```java
    public static Map<Character, List<String>> groupStringsByFirstLetter(List<String> strings){
        return strings.stream().collect(Collectors.groupingBy(s -> s.charAt(0)));
    }
    ```

**5. Partitioning Numbers by Prime**

* **Learning goal:** Use partitioning by with a custom condition.
* **Your code:**

    ```java
    import java.util.List;
    import java.util.Map;
    import java.util.stream.Collectors;
    import org.junit.jupiter.api.Test;
    import static org.junit.jupiter.api.Assertions.assertEquals;
    class StreamExercisesLevel3 {
        public static Map<Boolean, List<Integer>> partitionPrimes(List<Integer> numbers){
            return null;
        }
        private static boolean isPrime(int number){
            if (number <= 1) return false;
            for (int i = 2; i <= Math.sqrt(number); i++){
                if (number % i == 0) return false;
            }
            return true;
        }
        @Test
        public void testPartitionPrimes(){
            List<Integer> input = List.of(1,2,3,4,5,6,7,8,9);
            Map<Boolean, List<Integer>> expected = Map.of(true, List.of(2,3,5,7), false, List.of(1,4,6,8,9));
            assertEquals(expected, partitionPrimes(input));
        }
    }
    ```

* **Solution:**

    ```java
    public static Map<Boolean, List<Integer>> partitionPrimes(List<Integer> numbers){
        return numbers.stream().collect(Collectors.partitioningBy(StreamExercisesLevel3::isPrime));
    }
    ```


**6. Grouping by Custom Object Property**

* **Learning Goal:** Grouping by a property of a custom object.
* **Exercise:** Given a list of `Person` objects (with name and age), group them by their age.
* **Your Code:**

    ```java
    import java.util.List;
    import java.util.Map;
    import java.util.stream.Collectors;
    import org.junit.jupiter.api.Test;
    import static org.junit.jupiter.api.Assertions.assertEquals;
    class StreamExercisesLevel3 {

        static class Person {
            String name;
            int age;

            Person(String name, int age) {
                this.name = name;
                this.age = age;
            }
        }

        public static Map<Integer, List<Person>> groupPeopleByAge(List<Person> people) {
            // Your code here
            return null; // Replace with your implementation
        }

        @Test
        void testGroupPeopleByAge() {
            List<Person> input = List.of(new Person("Alice", 30), new Person("Bob", 25), new Person("Charlie", 30));
            Map<Integer, List<Person>> expected = Map.of(25, List.of(new Person("Bob", 25)), 30, List.of(new Person("Alice", 30), new Person("Charlie", 30)));
            assertEquals(expected, groupPeopleByAge(input));
        }
    }
    ```

* **Solution:**

    ```java
    public static Map<Integer, List<Person>> groupPeopleByAge(List<Person> people) {
        return people.stream().collect(Collectors.groupingBy(person -> person.age));
    }
    ```

**7. Grouping by Boolean Condition**

* **Learning Goal:** Grouping based on a boolean result of a condition.
* **Exercise:** Given a list of strings, group them into two lists: one with strings that have length greater than 4, and one with strings that have length less than or equal to 4.
* **Your Code:**

    ```java
    import java.util.List;
    import java.util.Map;
    import java.util.stream.Collectors;
    import org.junit.jupiter.api.Test;
    import static org.junit.jupiter.api.Assertions.assertEquals;
    class StreamExercisesLevel3 {

        public static Map<Boolean, List<String>> groupStringsByLengthCondition(List<String> strings) {
            // Your code here
            return null; // Replace with your implementation
        }

        @Test
        void testGroupStringsByLengthCondition() {
            List<String> input = List.of("apple", "cat", "banana", "dog", "kiwi");
            Map<Boolean, List<String>> expected = Map.of(true, List.of("apple", "banana", "kiwi"), false, List.of("cat", "dog"));
            assertEquals(expected, groupStringsByLengthCondition(input));
        }
    }
    ```

* **Solution:**

    ```java
    public static Map<Boolean, List<String>> groupStringsByLengthCondition(List<String> strings) {
        return strings.stream().collect(Collectors.groupingBy(s -> s.length() > 4));
    }
    ```

**8. Grouping and Counting by Object Property**

* **Learning Goal:** Grouping objects by property and counting within groups.
* **Exercise:** Given a list of `Person` objects, group them by age and count the number of people in each age group.
* **Your Code:**

    ```java
    import java.util.List;
    import java.util.Map;
    import java.util.stream.Collectors;
    import org.junit.jupiter.api.Test;
    import static org.junit.jupiter.api.Assertions.assertEquals;
    class StreamExercisesLevel3 {

        static class Person {
            String name;
            int age;

            Person(String name, int age) {
                this.name = name;
                this.age = age;
            }
        }

        public static Map<Integer, Long> countPeopleByAge(List<Person> people) {
            // Your code here
            return null; // Replace with your implementation
        }

        @Test
        void testCountPeopleByAge() {
            List<Person> input = List.of(new Person("Alice", 30), new Person("Bob", 25), new Person("Charlie", 30));
            Map<Integer, Long> expected = Map.of(25, 1L, 30, 2L);
            assertEquals(expected, countPeopleByAge(input));
        }
    }
    ```

* **Solution:**

    ```java
    public static Map<Integer, Long> countPeopleByAge(List<Person> people) {
        return people.stream().collect(Collectors.groupingBy(person -> person.age, Collectors.counting()));
    }
    ```

**9. Partitioning Strings by Starting Character**

* **Learning Goal:** Partitioning based on a string prefix.
* **Exercise:** Given a list of strings, partition them into two lists: one with strings that start with "a", and one with strings that do not.
* **Your Code:**

    ```java
    import java.util.List;
    import java.util.Map;
    import java.util.stream.Collectors;
    import org.junit.jupiter.api.Test;
    import static org.junit.jupiter.api.Assertions.assertEquals;
    class StreamExercisesLevel3 {

        public static Map<Boolean, List<String>> partitionStringsByStartingA(List<String> strings) {
            // Your code here
            return null; // Replace with your implementation
        }

        @Test
        void testPartitionStringsByStartingA() {
            List<String> input = List.of("apple", "banana", "ant", "cherry");
            Map<Boolean, List<String>> expected = Map.of(true, List.of("apple", "ant"), false, List.of("banana", "cherry"));
            assertEquals(expected, partitionStringsByStartingA(input));
        }
    }
    ```

* **Solution:**

    ```java
    public static Map<Boolean, List<String>> partitionStringsByStartingA(List<String> strings) {
        return strings.stream().collect(Collectors.partitioningBy(s -> s.startsWith("a")));
    }
    ```

**10. Grouping and Transforming Values**

* **Learning Goal:** Grouping and transforming the values within the groups.
* **Exercise:** Given a list of `Person` objects, group them by age and get a list of names for each age group.
* **Your Code:**

    ```java
    import java.util.List;
    import java.util.Map;
    import java.util.stream.Collectors;
    import org.junit.jupiter.api.Test;
    import static org.junit.jupiter.api.Assertions.assertEquals;
    class StreamExercisesLevel3 {

        static class Person {
            String name;
            int age;

            Person(String name, int age) {
                this.name = name;
                this.age = age;
            }
        }

        public static Map<Integer, List<String>> getNamesByAge(List<Person> people) {
            // Your code here
            return null; // Replace with your implementation
        }

        @Test
        void testGetNamesByAge() {
            List<Person> input = List.of(new Person("Alice", 30), new Person("Bob", 25), new Person("Charlie", 30));
            Map<Integer, List<String>> expected = Map.of(25, List.of("Bob"), 30, List.of("Alice", "Charlie"));
            assertEquals(expected, getNamesByAge(input));
        }
    }
    ```

* **Solution:**

    ```java
    public static Map<Integer, List<String>> getNamesByAge(List<Person> people) {
        return people.stream().collect(Collectors.groupingBy(person -> person.age, Collectors.mapping(person -> person.name, Collectors.toList())));
    }
    ```
