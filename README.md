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
