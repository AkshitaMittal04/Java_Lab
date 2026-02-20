// Source code is decompiled from a .class file using FernFlower decompiler (from Intellij IDEA).
## INDEX
[Program-01 WAP to add, sub , mul and division using Command Line Arguements](#Assi-1)

[Program-02 WAP to demonstrate the use of Constructor](#Assi-2)
## Assi-1
```

public class Calc {
   public Calc() {
   }

   public static void add(int var0, int var1) {
      System.out.println(" Addition " + (var0 + var1));
   }

   public static void sub(int var0, int var1) {
      System.out.println(" Subtraction " + (var0 - var1));
   }

   public static void mul(int var0, int var1) {
      System.out.println(" Multiply " + var0 * var1);
   }

   public static void div(int var0, int var1) {
      System.out.println("  Divison " + var0 / var1);
   }

   public static void main(String[] var0) {
      int var1 = Integer.parseInt(var0[0]);
      int var2 = Integer.parseInt(var0[1]);
      add(var1, var2);
      sub(var1, var2);
      mul(var1, var2);
      div(var1, var2);
```
<img width="392" height="221" alt="Screenshot (98)" src="https://github.com/user-attachments/assets/b7ff48ae-06f0-4e9d-aca4-2e841c9ea1a6" />



## Assi-2

```
class Student {

    String name;
    int age;

    // Constructor
    Student(String n, int a) {
        name = n;
        age = a;
    }

    void display() {
        System.out.println("Name: " + name);
        System.out.println("Age: " + age);
    }

    public static void main(String[] args) {
        // Creating object
        Student s1 = new Student("Akshita", 20);
        s1.display();
    }
}
```
<img width="497" height="231" alt="Screenshot (99)" src="https://github.com/user-attachments/assets/bf076657-d0a8-4cf1-b13b-ddb5ac2060d3" />

