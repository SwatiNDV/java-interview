# java-interview
1) How to reverse a string in Java?

 This question is one of them. You have to write a Java program to reverse a given string using recursive method. [Solution]
```java 
import java.util.stream.Stream;
import java.util.stream.Collectors;

class HelloWorld {
    public static void main(String[] args) {
        String str = "Try programiz.pro";
       /* StringBuilder sb = new StringBuilder(str);
        sb.reverse();
        System.out.println(sb);*/
        
        char[] carr = str.toCharArray();
        for(int i=carr.length-1;i>=0;i--)
        
           System.out.print(carr[i]);
        
    }
}
```

4) How to find duplicate characters in a string in Java?

Write a Java program to find duplicate characters and their count in a given string. For example, in a string “Better Butter”, duplicate characters and their count is t : 4, e : 3, r : 2 and B : 2. [Solution]
```java
import java.util.stream.Stream;
import java.util.stream.Collectors;
import java.util.function.Function;
import java.util.*;

class HelloWorld {
    public static void main(String[] args) {
        String str = "Butter Better";
        
        Map<Character,Long> map = str.chars().
        mapToObj(c->(char)c).
        collect(Collectors.groupingBy(Function.identity(),
        Collectors.counting()));
        
        System.out.println(map);
   }
}

```java
import java.util.*;
class HelloWorld {
    public static void main(String[] args) {
        String str = "Butter Better";
        
        char[] car = str.toCharArray();
        HashMap<Character,Integer> map = new HashMap<>();
        for(char c:car){
            if(map.containsKey(c))
            {
             map.put(c,map.get(c)+1);   
            }
            else
                map.put(c,1);
        }
        System.out.println(map.entrySet());
        
        Set<Character> keySet = map.keySet();
        for(char c:keySet){
            if(map.get(c)>1)
                System.out.print(c+" : "+map.get(c)+"\n");
        }
   }
}
```

3) How do you remove all white spaces from a string in Java?

The bundle of Java programming interview questions is incomplete without the questions on strings. You will face many questions on string handling in your interview. I have listed some of them in this post. It is one of them. [Solution]
```java
import java.util.stream.Stream;
import java.util.stream.Collectors;

class HelloWorld {
    public static void main(String[] args) {
        String str = "Try programiz.pro";
      
       //str = str.replaceAll(" ","");
       StringBuilder sb = new StringBuilder();
       char[] arr = str.toCharArray();
       for(int i=0;i<arr.length;i++)
            if(arr[i]!= ' ')
            {
                str = str + arr[i];
            }
               
       System.out.print(str);
        
    }
}
5) How do you check the equality of two arrays in Java?

One more favorite topic of many interviewers is array. You will face many Java coding interview questions related to array. In this program, you will learn how to check the equality of two arrays using different methods. [Solution
```java
#Iterative method
import java.util.*;
class HelloWorld {
    public static void main(String[] args) {
       
        int[] arrayOne = {2, 5, 1, 7, 4};
        int[] arrayTwo = {2, 5, 1, 7, 4};
        
        boolean equal = true;
        
        for(int i=0;i<arrayOne.length;i++)
        {
              if(arrayOne[i]!=arrayTwo[i])
                equal = false;
        }
        if(equal)
            System.out.println("Arrays are equal");
        else
            System.out.println("Arrays are not equal");
   }
}

#Using Arrays.equals()

import java.util.*;
class HelloWorld {
    public static void main(String[] args) {
       
        int[] arrayOne = {2, 6, 1, 7, 4};
        int[] arrayTwo = {2, 5, 1, 7, 4};
        
        if(Arrays.equals(arrayOne,arrayTwo))
            System.out.println("Arrays are equal");
        else
            System.out.println("Arrays are not equal");
   }
}
```
6) Anagram program in Java

Write a Java program to check whether two given strings are anagram or not. Two strings are said to be anagram if they contain same set of characters but in different order. For example, “Mother In Law” and “Hitler Woman” are anagrams. This type of Java programming questions test the coding skills of a candidate. [Solution]

```java
#using sort() and equals()

import java.util.*;
class HelloWorld {
    public static void main(String[] args) {
       
        String s1 = "Keep";
        String s2 = "peek";
        
        char[] car1 = s1.toUpperCase().toCharArray();
        char[] car2 = s2.toUpperCase().toCharArray();
        
        Arrays.sort(car1);
        Arrays.sort(car2);
        
        if(car1.length == car2.length && Arrays.equals(car1,car2))
            System.out.println("Anagram");
        else
            System.out.println("Not an Anagram");
   }
}

#java 8

import java.util.*;
import java.util.stream.Collectors;
import java.util.function.Function;
class HelloWorld {
    public static void main(String[] args) {
       
        String str1 = "Keep";
        String str2 = "peek";
        
       if (str1 == null || str2 == null || str1.length() != str2.length()) {
            System.out.println("Strings are not equal");
        }
        str1 = str1.toLowerCase();
        str2 = str2.toLowerCase();

        Map<Character,Long> charCountMap1 = str1.chars().
        mapToObj(c->(char)c).
        collect(Collectors.groupingBy(Function.identity(),Collectors.counting()));

        Map<Character, Long> charCountMap2 = str2.chars()
        .mapToObj(c -> (char)c)
        .collect(Collectors.groupingBy(Function.identity(), Collectors.counting()));


     if(charCountMap1.equals(charCountMap2))
        System.out.println("Anagram");
     else
        System.out.println("Not an Anagram");
        
   }
}

```
8) How to find duplicate elements in an array?

I think array related programs along with string handling programs are the most asked Java programs in interview. In this program, I have discussed five methods to find duplicate elements in the given array. [Solution]
```java
import java.util.*;

class HelloWorld {
    public static void main(String[] args) {
       
        int[] arr = {1,2,3,4,5,6};
        
        Set<Integer> uniqueSet = new HashSet<>();
        
        for(int i : arr){
            if(!uniqueSet.add(i))
            System.out.println("Array contains duplicate elements");
            else
                System.out.println("Array doesnt not contains duplicate");
        }
      
   }
}
#Brute force

import java.util.*;

class HelloWorld {
    public static void main(String[] args) {
       
        int[] arr = {1,2,2,3,4,5,6};
        
        for(int i=0;i<arr.length;i++){
            for(int j=i+1;j<arr.length;j++)
            {
                if(arr[i]==arr[j])
                    System.out.println("Array contains duplicate elements");
                    break;
            }
        }
    }
}

#java 8

import java.util.*;
import java.util.Arrays;
import java.util.HashMap;
import java.util.HashSet;
import java.util.Map.Entry;
import java.util.Set;
import java.util.stream.Collectors;

class HelloWorld {
    public static void main(String[] args) {
       
        int[] arr = {1,2,2,3,4,5,6,6};
        
        Set<Integer> uniqueSet = new HashSet<>();
        
       
     Set<Integer>  duplicateElements = Arrays.stream(arr).filter(i->!uniqueSet.add(i)).boxed().collect(Collectors.toSet());
     
     System.out.println(duplicateElements);
   
    }
}
```

9) How to find sum of all digits of a number in Java?

```java
    class HelloWorld {
    public static void main(String[] args) {
       
       int number = 4201;
       int sum = 0;
       while(number>0){
           int digit = number % 10;
           sum+=digit;
           number = number / 10;
           
       }
       System.out.println("Sum of all the digits :"+sum);
   
    }
}
```

10) How to find second largest number in an integer array?

```java
class HelloWorld {
    public static void main(String[] args) {
       
        int[] arr = {1,3,2,5,4};
        int arr_size = arr.length;
        
        if (arr_size < 2) {
            System.out.printf(" Invalid Input ");
            return;
        }
        
        int largest  = Integer.MIN_VALUE;
        int second   = Integer.MIN_VALUE;
        
        for (int i = 0; i < arr_size; i++) {
            largest = Math.max(largest, arr[i]);
        }
        
        for (int i = 0; i < arr_size; i++) {
            if (arr[i] != largest)
                second = Math.max(second, arr[i]);
        }
        
        if (second == Integer.MIN_VALUE)
            System.out.printf("There is no second "
                              + "largest element\n");
        else
            System.out.printf("The second largest "
                                  + "element is %d\n",
                              second);
    
     
    }
}
```

16) How to remove duplicate elements from ArrayList in Java?
    
```java
    
class HelloWorld {
    public static void main(String[] args) {
    
    ArrayList<String> listD = new ArrayList<>();
    listD.add("java");
    listD.add("c");
    listD.add("python");
    listD.add("java");
    listD.add("ruby");
    listD.add("ruby");
    System.out.println(listD);
    
    Set<String> set = new LinkedHashSet<>(listD);
    System.out.println(set);
    
    ArrayList<String> listUnique = new ArrayList<>(set);
    System.out.println(listUnique);
    }
}
```
17) How to check whether given number is binary or not?

```java
class HelloWorld {
    public static void main(String[] args) {
    
    int num = 1010 ;
    boolean isBinary = true;
    while(num>0){
        int digit = num % 10;
        if(digit > 1)
        {
            isBinary = false;
            break;
        }
        else
            num = num /10;
  }
  if(isBinary)
    System.out.println("Binary");
  else
    System.out.println("Not a Binary");
    
    }
}
```
18) How to check whether one string is a rotation of another in Java?

```java
class HelloWorld {
    public static void main(String[] args) {
    
   String str1 = "StrutsHibernateJavaJ2ee";
   String str2 = "2eeStrutsHibernateJava";
   String str3 = "";
   
   boolean isRotated = true;
   
   if(str1.length()!=str2.length()){
     System.out.println("Strings are of different length");
       
   }
   else{
        str3 = str1+str2;
    if(str3.contains(str2))
         System.out.println("Str2 is a rotated version of Str1");
    else
        System.out.println("Not a rotated version");
   }
    }
}
```
