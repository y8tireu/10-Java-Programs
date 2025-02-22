# 10 Java Programs

---

## Program 1: Hello World
```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
}
```

---

## Program 2: Sum of Two Numbers
```java
import java.util.Scanner;

public class SumTwoNumbers {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter first number: ");
        int a = scanner.nextInt();
        System.out.print("Enter second number: ");
        int b = scanner.nextInt();
        System.out.println("Sum: " + (a + b));
        scanner.close();
    }
}
```

---

## Program 3: Factorial (Recursive)
```java
public class Factorial {
    public static long factorial(int n) {
        return (n == 0) ? 1 : n * factorial(n - 1);
    }

    public static void main(String[] args) {
        int num = 5;
        System.out.println("Factorial of " + num + " is " + factorial(num));
    }
}
```

---

## Program 4: Fibonacci Series
```java
public class Fibonacci {
    public static void printFibonacci(int count) {
        int a = 0, b = 1;
        System.out.print("Fibonacci series: ");
        for (int i = 0; i < count; i++) {
            System.out.print(a + " ");
            int temp = a + b;
            a = b;
            b = temp;
        }
        System.out.println();
    }

    public static void main(String[] args) {
        printFibonacci(10);
    }
}
```

---

## Program 5: Prime Number Checker
```java
public class PrimeChecker {
    public static boolean isPrime(int n) {
        if (n < 2) return false;
        for (int i = 2; i <= Math.sqrt(n); i++) {
            if (n % i == 0) return false;
        }
        return true;
    }

    public static void main(String[] args) {
        int number = 29;
        System.out.println(number + " is prime? " + isPrime(number));
    }
}
```

---

## Program 6: Palindrome Checker
```java
public class Palindrome {
    public static boolean isPalindrome(String s) {
        String reversed = new StringBuilder(s).reverse().toString();
        return s.equals(reversed);
    }

    public static void main(String[] args) {
        String word = "radar";
        System.out.println(word + " is a palindrome? " + isPalindrome(word));
    }
}
```

---

## Program 7: Bubble Sort
```java
import java.util.Arrays;

public class BubbleSort {
    public static void bubbleSort(int[] arr) {
        int n = arr.length;
        for (int i = 0; i < n; i++) {
            for (int j = 0; j < n - i - 1; j++) {
                if (arr[j] > arr[j + 1]) {
                    // Swap arr[j] and arr[j+1]
                    int temp = arr[j];
                    arr[j] = arr[j + 1];
                    arr[j + 1] = temp;
                }
            }
        }
    }

    public static void main(String[] args) {
        int[] numbers = {64, 34, 25, 12, 22, 11, 90};
        bubbleSort(numbers);
        System.out.println("Sorted array: " + Arrays.toString(numbers));
    }
}
```

---

## Program 8: Array Manipulation Using ArrayList
```java
import java.util.ArrayList;
import java.util.Collections;

public class ArrayListDemo {
    public static void main(String[] args) {
        ArrayList<String> fruits = new ArrayList<>();
        fruits.add("Apple");
        fruits.add("Banana");
        fruits.add("Cherry");
        
        // Print the list
        System.out.println("Fruits: " + fruits);
        
        // Sort the list
        Collections.sort(fruits);
        System.out.println("Sorted Fruits: " + fruits);
        
        // Remove an element
        fruits.remove("Banana");
        System.out.println("After removal: " + fruits);
    }
}
```

---

## Program 9: Object-Oriented Example (Class and Inheritance)
```java
class Animal {
    public void speak() {
        System.out.println("Animal sound");
    }
}

class Dog extends Animal {
    @Override
    public void speak() {
        System.out.println("Woof!");
    }
}

public class InheritanceDemo {
    public static void main(String[] args) {
        Animal genericAnimal = new Animal();
        Dog dog = new Dog();
        
        genericAnimal.speak();
        dog.speak();
    }
}
```

---

## Program 10: File Reading with Exception Handling
```java
import java.io.BufferedReader;
import java.io.FileReader;
import java.io.IOException;

public class FileReadDemo {
    public static void main(String[] args) {
        String filename = "example.txt";
        try (BufferedReader br = new BufferedReader(new FileReader(filename))) {
            String line;
            System.out.println("File content:");
            while ((line = br.readLine()) != null) {
                System.out.println(line);
            }
        } catch (IOException e) {
            System.err.println("Error reading file: " + e.getMessage());
        }
    }
}
```
