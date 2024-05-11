# java-interview
4) How to find duplicate characters in a string in Java?

Write a Java program to find duplicate characters and their count in a given string. For example, in a string “Better Butter”, duplicate characters and their count is t : 4, e : 3, r : 2 and B : 2. [Solution]
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
