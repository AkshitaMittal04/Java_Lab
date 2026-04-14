// Source code is decompiled from a .class file using FernFlower decompiler (from Intellij IDEA).
## INDEX
[Program-01 WAP to add, sub , mul and division using Command Line Arguements](#Assi-1)

[Program-02 WAP to demonstrate the use of Constructor](#Assi-2)

[Program-03 Write a class to add two distances which is in the form of meter, centimeter and milimeter.](#Assi-3)
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





class Distance {
    int meter;
    int centimeter;
    int millimeter;

    // Method to take input values
    void set(int m, int c, int mm) {
        meter = m;
        centimeter = c;
        millimeter = mm;
    }

    // Method to add two Distance objects
    Distance add(Distance d) {
        Distance result = new Distance();

        result.millimeter = this.millimeter + d.millimeter;
        result.centimeter = this.centimeter + d.centimeter;
        result.meter = this.meter + d.meter;

        // Conversion
        result.centimeter += result.millimeter / 10;
        result.millimeter = result.millimeter % 10;

        result.meter += result.centimeter / 100;
        result.centimeter = result.centimeter % 100;

        return result;
    }

    // Method to display distance
    void display() {
        System.out.println("Distance = " + meter + " m "
                + centimeter + " cm "
                + millimeter + " mm");
    }
}

public class Dis {
    public static void main(String[] args) {

        Distance d1 = new Distance();
        Distance d2 = new Distance();

        d1.set(8, 80, 9); // 8m 80cm 9mm
        d2.set(3, 50, 6); // 3m 50cm 6mm

        Distance sum = d1.add(d2);

        System.out.println("First Distance:");
        d1.display();

        System.out.println("Second Distance:");
        d2.display();

        System.out.println("Total Distance:");
        sum.display();
    }
}

<img width="288" height="160" alt="image" src="https://github.com/user-attachments/assets/d485bc15-b2f1-4a89-b172-1d4be301abf5" />
