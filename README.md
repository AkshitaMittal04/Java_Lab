// Source code is decompiled from a .class file using FernFlower decompiler (from Intellij IDEA).
## INDEX
[Program-01 WAP to add, sub , mul and division using Command Line Arguements](#Assi-1)

[Program-02 WAP to demonstrate the use of Constructor](#Assi-2)

[Program-03 Write a class to add two distances which is in the form of meter, centimeter and milimeter.](#Assi-3)

[Program-04 Write a class to add two times which is in the form of hour, minutes and second](#Assi-4)

[Program-05 Write a class to perform a Transpose of a Matrix.](#Assi-5)

[Program-06 Write a class to perform sum of the matrices.](#Assi-6)
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


## Assi-3

```

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
```
<img width="288" height="160" alt="image" src="https://github.com/user-attachments/assets/d485bc15-b2f1-4a89-b172-1d4be301abf5" />


## Assi-4

```
class Time {

    int hr, min, sec;

    // Constructor
    Time(int h, int m, int s) {
        hr = h;
        min = m;
        sec = s;
    }

    // Method to add two objects
    void add(Time t) {

        int totalSec = this.sec + t.sec;
        int totalMin = this.min + t.min;
        int totalHr  = this.hr + t.hr;

        // Adjust seconds
        if (totalSec >= 60) {
            totalMin = totalMin + 1;
            totalSec = totalSec - 60;
        }

        // Adjust minutes
        if (totalMin >= 60) {
            totalHr = totalHr + 1;
            totalMin = totalMin - 60;
        }

        System.out.println("Total Time = " + totalHr + " : " + totalMin + " : " + totalSec);
    }

    public static void main(String[] args) {

        Time t1 = new Time(2, 45, 50);
        Time t2 = new Time(1, 20, 30);

        t1.add(t2);   // Adding two objects
    }
}
```
<img width="326" height="181" alt="image" src="https://github.com/user-attachments/assets/1e2c54e7-8f87-496b-9f5c-f29d4b558c2d" />

## Assi-5
```
class TransposeMatrix {

    int matrix[][] = {
            { 1, 2, 3 },
            { 4, 5, 6 },
            { 7, 8, 9 }
    };

    void transpose() {
        int rows = matrix.length;
        int cols = matrix[0].length;

        int transpose[][] = new int[cols][rows];

        for (int i = 0; i < rows; i++) {
            for (int j = 0; j < cols; j++) {
                transpose[j][i] = matrix[i][j];
            }
        }

        System.out.println("Original Matrix:");
        for (int i = 0; i < rows; i++) {
            for (int j = 0; j < cols; j++) {
                System.out.print(matrix[i][j] + " ");
            }
            System.out.println();
        }

        System.out.println("Transpose Matrix:");
        for (int i = 0; i < cols; i++) {
            for (int j = 0; j < rows; j++) {
                System.out.print(transpose[i][j] + " ");
            }
            System.out.println();
        }
    }
}

public class Transpose {
    public static void main(String[] args) {

        TransposeMatrix obj = new TransposeMatrix(); // object creation
        obj.transpose(); // method call
    }
}
```
<img width="305" height="216" alt="image" src="https://github.com/user-attachments/assets/97ed40cc-006c-495d-a615-fd94fa9c966f" />

## Assi-6

```
class Matrixx {
    int A[][] = {{1,2},{3,4}};
    int B[][] = {{5,6},{7,8}};
    int C[][] = new int[2][2];

    void addMatrix() {
        for(int i = 0; i < 2; i++)
        {
            for(int j = 0; j < 2; j++)
            {
                C[i][j] = A[i][j] + B[i][j];
            }
        }
    }

    void display() {
        System.out.println("Sum of matrices:");

        for(int i = 0; i < 2; i++)
        {
            for(int j = 0; j < 2; j++)
            {
                System.out.print(C[i][j] + " ");
            }
            System.out.println();
        }
    }
}

public class Matrix{
    public static void main(String[] args) {
        Matrixx obj = new Matrixx();  // object creation
        obj.addMatrix();            // method call
        obj.display();              // display result
    }
}
```
<img width="168" height="137" alt="image" src="https://github.com/user-attachments/assets/df7877a5-aacf-467e-984a-fda7a5e46497" />


