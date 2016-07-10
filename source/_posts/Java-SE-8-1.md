---
title: Java SE 8 (1)
date: 2016-07-01 13:28:47
toc: false   #是否开启文章内目录导航
original: false  #是否显示文末版权信息
categories: JavaSE
tags: OCAJ
---
New feature in Java SE 8.
Pass the OCAJ test and become a Certified Associate Java SE 8 Programmer! 
<!-- more -->
![可以去oracle官网下载logo哟(^o^)/](/img/oracle.png)
---
# 概述：
今年5月在家等日本签证的时候干了很多奇怪的事，比如考了这个OCAJ…且不说鸡肋与否，准备的过程中还是学到了很多东西，对Java也是更加爱得深沉（嗯但我有空还是会写python博客），想着那就记录一下，温（qiang）故（xing）知（zhung）新（bi）嘛。所以这个分类中将持续纪录一些关于Java的比较tricky的问题以及脑洞总结。

OCAJ就是原来Sun公司的SCJA认证考试。由于sun公司被甲骨文收购，原来的SCJA & SCJP 考试也相应地变成了Oracle 旗下的OCAJ & OCAP 考试。 OCAJ考试相对来说还是比较容易的，但是与Oracle的经典数据库认证不同， 其Java认证必须从OCAJ开始考，通过了之后才能继续考OCAP以及Java EE的高级认证（数据库认证可从OCP开始考，通过之后才有资格考OCM）。

更多信息见：http://education.oracle.com/pls/web_prod-plq-dad/db_pages.getpage?page_id=39

此处小吐槽一下此类考试信息不要搜某度，国内数据库认证盛行但很少有Java认证信息。兔同学貌似就是长沙某考试中心有史以来第一个参加OCAJ考试的（手动微笑）。

废话完结，以上。

# 参考书：
1. Head first Java, O’Reilly.（画风清奇，已收藏纸质版…另外废话一句，O’Reilly家的Head first系列都好棒呀！）
2. Core Java, Pearson
3. OCA: Oracle Certified Associate Java SE 8 Programmer I Study Guide, Jeanne Boyarsky & Scott Selikoff
4. Thinking in Java, Bruce Eckel

# 正文：
放一个Assessment Test镇楼。来源：OCA Study Guide
1, What is the result of the following class? (Choose all that apply)
```java
public class _C {
    private static int $;
    public static void main(String[] main) {
        String a_b;
        System.out.print($);
        System.out.print(a_b);
    } 
}```
A. Compiler error on line 1.
B. Compiler error on line 2.
C. Compiler error on line 4.
D. Compiler error on line 5.
E. Compiler error on line 6.
F. 0null
G. nullnull

2, What is the result of the following code?
```java
String s1 = "Java";
String s2 = "Java";
StringBuilder sb1 = new StringBuilder();
sb1.append("Ja").append("va");
System.out.println(s1 == s2);
System.out.println(s1.equals(s2));
System.out.println(sb1.toString() == s1);
System.out.println(sb1.toString().equals(s1));
```
A. true is printed out exactly once.
B. true is printed out exactly twice.
C. true is printed out exactly three times.
D. true is printed out exactly four times.
E. The code does not compile.

3, What is the output of the following code? (Choose all that apply)
```java
interface HasTail { 
    int getTailLength(); 
}

abstract class Puma implements HasTail {
    protected int getTailLength() {
        return 4;
    }
}

public class Cougar extends Puma {
    public static void main(String[] args) {
        Puma puma = new Puma();
        System.out.println(puma.getTailLength());
    }

    public int getTailLength(int length) {
        return 2;
    }
}
```
A. 2
B. 4
C. The code will not compile because of line 3.
D. The code will not compile because of line 5.
E. The code will not compile because of line 7.
F. The code will not compile because of line 11.
G. The output cannot be determined from the code provided.

4, What is the output of the following program?
```java
public class FeedingSchedule {
    public static void main(String[] args) {
        boolean keepGoing = true;
        int count = 0;
        int x = 3;
        while(count++ < 3) {
            int y = (1 + 2 * count) % 3;
            switch(y) {
                default:
                case 0: x -= 1; break;
                case 1: x += 5;
            }
        }
        System.out.println(x);
    } 
}
```
A. 4
B. 5
C. 6
D. 7
E. 13
F. The code will not compile because of line 7.

5, What is the output of the following code snippet?
```java
System.out.print("a");
try {
    System.out.print("b");
    throw new IllegalArgumentException();
} catch (RuntimeException e) {
    System.out.print("c");
} finally {
    System.out.print("d");
}
System.out.print("e");
```
A. abe
B. abce
C. abde
D. abcde
E. The code does not compile.
F. An uncaught exception is thrown.

6, What is the result of the following program?
```java
public class MathFunctions {
    public static void addToInt(int x, int amountToAdd) {
        x = x + amountToAdd;
    }
    public static void main(String[] args) {
        int a = 15;
        int b = 10;
        MathFunctions.addToInt(a, b);
        System.out.println(a); 
    } 
}
```
A. 10
B. 15
C. 25
D. Compiler error on line 3.
E. Compiler error on line 8.
F. None of the above.

7, What is the result of the following code?
```java
int[] array = {6,9,8};
List<Integer> list = new ArrayList<>();
list.add(array[0]);
list.add(array[2]);
list.set(1, array[1]);
list.remove(0);
System.out.println(list);
```
A. [8]
B. [9]
C. Something like [Ljava.lang.String;@160bc7c0
D. An exception is thrown.
E. The code does not compile.

8, What is the output of the following code?
```java
public class Deer {
    public Deer() { 
        System.out.print("Deer"); 
    }
    public Deer(int age) { 
        System.out.print("DeerAge"); 
    }
    private boolean hasHorns() { 
        return false; 
    }
    public static void main(String[] args) {
        Deer deer = new Reindeer(5);
        System.out.println(","+deer.hasHorns());
    }
}

class Reindeer extends Deer {
    public Reindeer(int age) { 
        System.out.print("Reindeer"); 
    }
    public boolean hasHorns() { 
        return true; 
    }
}
```
A. DeerReindeer,false
B. DeerReindeer,true
C. ReindeerDeer,false
D. ReindeerDeer,true
E. DeerAgeReindeer,false
F. DeerAgeReindeer,true
G. The code will not compile because of line 7.
H. The code will not compile because of line 12.

9, Which of the following statements are true? (Choose all that apply)
A. Checked exceptions are intended to be thrown by the JVM (and not the programmer).
B. Checked exceptions are required to be caught or declared.
C. Errors are intended to be thrown by the JVM (and not the programmer).
D. Errors are required to be caught or declared.
E. Runtime exceptions are intended to be thrown by the JVM (and not the programmer).
F. Runtime exceptions are required to be caught or declared.

10, Which are true of the following code? (Choose all that apply)
```java
import java.util.*;
public class Grasshopper {
    public Grasshopper(String n) {
        name = n;
    }
    public static void main(String[] args) {
        Grasshopper one = new Grasshopper("g1");
        Grasshopper two = new Grasshopper("g2");
        one = two;
        two = null;
        one = null;
    }
    private String name; 
}
```
A. Immediately after line 9, no grasshopper objects are eligible for garbage collection.
B. Immediately after line 10, no grasshopper objects are eligible for garbage collection.
C. Immediately after line 9, only one grasshopper object is eligible for garbage collection.
D. Immediately after line 10, only one grasshopper object is eligible for garbage collection.
E. Immediately after line 11, only one grasshopper object is eligible for garbage collection.
F. The code compiles.
G. The code does not compile.

11, What is the output of the following program?
```java
public class FeedingSchedule {
    public static void main(String[] args) {
        int x = 5, j = 0;
        OUTER: for(int i=0; i<3; )
            INNER: do {
                    i++; x++;
                    if(x > 10) break INNER;
                    x += 4;
                    j++;
                } while(j <= 2);
            System.out.println(x);
    } 
}
```
A. 10
B. 12
C. 13
D. 17
E. The code will not compile because of line 4.
F. The code will not compile because of line 6.

12, What is the result of the following program?
```java
public class Egret {
    private String color;
    public Egret() {
        this("white");
    }
    public Egret(String color) {
        color = color;
    }
    public static void main(String[] args) {
        Egret e = new Egret();
        System.out.println("Color:" + e.color);
    }
}
```
A. Color:
B. Color:null
C. Color:White
D. Compiler error on line 4.
E. Compiler error on line 10.
F. Compiler error on line 11.

13, What is the output of the following program?
```java
public class BearOrShark {
    public static void main(String[] args) {
        int luck = 10;
        if((luck>10 ? luck++: --luck)<10) {
            System.out.print("Bear");
        } 
        if(luck<10) 
            System.out.print("Shark");
    } 
}
```
A. Bear
B. Shark
C. BearShark
D. The code will not compile because of line 4.
E. The code will not compile because of line 6.
F. The code compiles without issue but does not produce any output.

14, Assuming we have a valid, non-null HenHouse object whose value is initialized by the
blank line shown here, which of the following are possible outputs of this application?
(Choose all that apply)
```java
class Chicken {}
interface HenHouse { 
    public java.util.List<Chicken> getChickens(); 
}
public class ChickenSong {
    public static void main(String[] args) {
        HenHouse house = ______________
        Chicken chicken = house.getChickens().get(0);
        for(int i=0; i<house.getChickens().size(); chicken = house.getChickens().get(i++)) {
            System.out.println("Cluck");
        } 
    } 
}
```
A. The code will not compile because of line 6.
B. The code will not compile because of lines 7–8.
C. The application will compile but not produce any output.
D. The application will output Cluck exactly once.
E. The application will output Cluck more than once.
F. The application will compile but produce an exception at runtime.

15, Which of the following statements can be inserted in the blank line so that the code will
compile successfully? (Choose all that apply)
```java
public interface CanSwim {}
public class Amphibian implements CanSwim {}
class Tadpole extends Amphibian {}
public class FindAllTadPole {
    public static void main(String[] args) {
        List<Tadpole> tadpoles = new ArrayList<Tadpole>();
        for(Amphibian amphibian : tadpoles) {
            ___________ tadpole = amphibian;
        } 
    } 
}
```
A. CanSwim
B. Long
C. Amphibian
D. Tadpole
E. Object

16, What individual changes, if any, would allow the following code to compile? (Choose all
that apply)
```java
public interface Animal { 
    public default String getName() { 
        return null; 
    } 
}
interface Mammal { 
    public default String getName() { 
        return null; 
    } 
}
abstract class Otter implements Mammal, Animal {}
```
A. The code compiles without issue.
B. Remove the default method modifier and method implementation on line 1.
C. Remove the default method modifier and method implementation on line 2.
D. Remove the default method modifier and method implementation on lines 1 and 2.
E. Change the return value on line 1 from null to "Animal".
F. Override the getName() method with an abstract method in the Otter class.
G. Override the getName() method with a concrete method in the Otter class.

17, Which of the following lines can be inserted at line 11 to print true? (Choose all that
apply)
```java
public static void main(String[] args) {
    // INSERT CODE HERE
}
private static boolean test(Predicate<Integer> p) {
    return p.test(5);
}
```
A. System.out.println(test(i -> i == 5));
B. System.out.println(test(i -> {i == 5;}));
C. System.out.println(test((i) -> i == 5));
D. System.out.println(test((int i) -> i == 5);
E. System.out.println(test((int i) -> {return i == 5;}));
F. System.out.println(test((i) -> {return i == 5;}));

18, Which of the following print out a date representing April 1, 2015? (Choose all that apply)
A. System.out.println(LocalDate.of(2015, Calendar.APRIL, 1));
B. System.out.println(LocalDate.of(2015, Month.APRIL, 1));
C. System.out.println(LocalDate.of(2015, 3, 1));
D. System.out.println(LocalDate.of(2015, 4, 1));
E. System.out.println(new LocalDate(2015, 3, 1));
F. System.out.println(new LocalDate(2015, 4, 1));

19, Bytecode is in a file with which extension?
A. .bytecode
B. .bytes
C. .class
D. .exe
E. .javac
F. .java

20, Which of the following are checked exceptions? (Choose all that apply)
A. Exception
B. IllegalArgumentException
C. IOException
D. NullPointerException
E. NumberFormatException
F. StackOverflowError
