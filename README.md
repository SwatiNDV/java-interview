# java-interview
1) How to reverse a string in Java?

Any technical interview is not complete without a question on recursive concept. This question is one of them. You have to write a Java program to reverse a given string using recursive method. [Solution]
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
```java 8
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
