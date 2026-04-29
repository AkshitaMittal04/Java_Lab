// Source code is decompiled from a .class file using FernFlower decompiler (from Intellij IDEA).
## INDEX
[Program-01 WAP to add, sub , mul and division using Command Line Arguements](#Assi-1)

[Program-02 WAP to demonstrate the use of Constructor](#Assi-2)

[Program-03 Write a class to add two distances which is in the form of meter, centimeter and milimeter.](#Assi-3)

[Program-04 Write a class to add two times which is in the form of hour, minutes and second](#Assi-4)

[Program-05 Write a class to perform a Transpose of a Matrix.](#Assi-5)

[Program-06 Write a class to perform sum of the matrices.](#Assi-6)

[Program-07 Write a class to perform the multiplication of two matrices.](#Assi-7)

[Program-08 Write a class to reverse a 1D array.](#Assi-8)

[Program-09 Write a class to perform the sum of each row and column.](Assi-9)

[Program-10 Write a C class program in java.](Assi-10)

[Program-11  Write a program using three classes to print 1-100 ,1-100,1-100 with and without thread and analyse the output and repeat the same program using runnable interface.](Assi-11)

[Program-12  Using the concept of multithreading the output of all three threads must be synchronised.](Assi-12)

[Program-13 WAP to perform the addition of two numbers using swing.](Assi-13)

[Program-14 WAP to make the registration form with 10 elements and send the data into database.](Assi-14)

[Program-15 WAP to make a calculator in swing.](Assi-15)



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
## Assi-7
```
class MatrixMultiplication {
    int a[][] = {
            { 1, 2, 3 },
            { 4, 5, 6 }
    };

    int b[][] = {
            { 7, 8 },
            { 9, 10 },
            { 11, 12 }
    };

    int c[][] = new int[2][2];

    void multiply() {
        for (int i = 0; i < 2; i++) {
            for (int j = 0; j < 2; j++) {
                c[i][j] = 0;
                for (int k = 0; k < 3; k++) {
                    c[i][j] = c[i][j] + a[i][k] * b[k][j];
                }
            }
        }
    }

    void display() {
        System.out.println("Result Matrix:");
        for (int i = 0; i < 2; i++) {
            for (int j = 0; j < 2; j++) {
                System.out.print(c[i][j] + " ");
            }
            System.out.println();
        }
    }
}

class MulMatrix {
    public static void main(String args[]) {
        MatrixMultiplication obj = new MatrixMultiplication();
        obj.multiply();
        obj.display();
    }
}
```
<img width="243" height="145" alt="image" src="https://github.com/user-attachments/assets/0d8693d6-539d-482f-a15a-4125debeb3cb" />

## Assi-8

```
class ReverseArrayy {

    void reverse(int arr[]) {
        int start = 0;
        int end = arr.length - 1;

        while(start < end) {
            int temp = arr[start];
            arr[start] = arr[end];
            arr[end] = temp;

            start++;
            end--;
        }
    }
}

public class ReverseArray {
    public static void main(String[] args) {

        int arr[] = {1, 2, 3, 4, 5};

        ReverseArrayy obj = new ReverseArrayy();
        obj.reverse(arr);

        System.out.println("Reversed Array:");

        for(int i = 0; i < arr.length; i++) {
            System.out.print(arr[i] + " ");
        }
    }
}
```
<img width="413" height="216" alt="image" src="https://github.com/user-attachments/assets/d3adb5db-3e5a-4b6e-9103-c7fc26add4a3" />

## Assi-9

```
class MatrixSum {

    int matrix[][] = {
        { 1, 2, 3 },
        { 4, 5, 6 },
        { 7, 8, 9 }
    };

    void rowSum() {
        for (int i = 0; i < matrix.length; i++) {
            int sum = 0;
            for (int j = 0; j < matrix[i].length; j++) {
                sum += matrix[i][j];
            }
            System.out.println("Sum of Row " + (i + 1) + " = " + sum);
        }
    }

    void columnSum() {
        for (int i = 0; i < matrix[0].length; i++) {
            int sum = 0;
            for (int j = 0; j < matrix.length; j++) {
                sum += matrix[j][i];
            }
            System.out.println("Sum of Column " + (i + 1) + " = " + sum);
        }
    }

    public static void main(String[] args) {
        MatrixSum obj = new MatrixSum();

        System.out.println("Row Sums:");
        obj.rowSum();

        System.out.println("\nColumn Sums:");
        obj.columnSum();
    }
}
```
<img width="310" height="277" alt="image" src="https://github.com/user-attachments/assets/a5046dc0-7967-4970-8a1d-70b5149ef0d0" />

## Assi-11
```

//  WITHOUT THREAD 
class A1 {
    // Method to print numbers from 1 to 100
    void print() {
        for (int i = 1; i <= 100; i++) {
            System.out.println("A (NO THREAD): " + i);
        }
    }
}

class B1 {
    void print() {
        for (int i = 1; i <= 100; i++) {
            System.out.println("B (NO THREAD): " + i);
        }
    }
}

class C1 {
    void print() {
        for (int i = 1; i <= 100; i++) {
            System.out.println("C (NO THREAD): " + i);
        }
    }
}

//  USING THREAD CLASS 
class A2 extends Thread {
    // run() method contains the code executed by thread
    public void run() {
        for (int i = 1; i <= 100; i++) {
            System.out.println("A (THREAD): " + i);
        }
    }
}

class B2 extends Thread {
    public void run() {
        for (int i = 1; i <= 100; i++) {
            System.out.println("B (THREAD): " + i);
        }
    }
}

class C2 extends Thread {
    public void run() {
        for (int i = 1; i <= 100; i++) {
            System.out.println("C (THREAD): " + i);
        }
    }
}

//  USING RUNNABLE INTERFACE 
class A3 implements Runnable {
    // run() method defines the task for the thread
    public void run() {
        for (int i = 1; i <= 100; i++) {
            System.out.println("A (RUNNABLE): " + i);
        }
    }
}

class B3 implements Runnable {
    public void run() {
        for (int i = 1; i <= 100; i++) {
            System.out.println("B (RUNNABLE): " + i);
        }
    }
}

class C3 implements Runnable {
    public void run() {
        for (int i = 1; i <= 100; i++) {
            System.out.println("C (RUNNABLE): " + i);
        }
    }
}

//  MAIN CLASS 
public class AllInOneThreads {

    public static void main(String[] args) {

        // WITHOUT THREAD 
        // Methods are called one after another (sequential execution)
        System.out.println("===== WITHOUT THREAD =====");
        new A1().print();
        new B1().print();
        new C1().print();

        //  USING THREAD CLASS
        // Threads run simultaneously (concurrent execution)
        System.out.println("\n===== WITH THREAD =====");

        A2 t1 = new A2(); // Create thread objects
        B2 t2 = new B2();
        C2 t3 = new C2();

        t1.start(); // Start thread execution
        t2.start();
        t3.start();

        // join() ensures main thread waits until all threads finish
        try {
            t1.join();
            t2.join();
            t3.join();
        } catch (Exception e) {
            System.out.println(e);
        }

        // Runnable separates task from thread (better approach)
        System.out.println("\n===== USING RUNNABLE =====");

        Thread r1 = new Thread(new A3());
        Thread r2 = new Thread(new B3());
        Thread r3 = new Thread(new C3());

        r1.start();
        r2.start();
        r3.start();
    }
}
```
<img width="1003" height="443" alt="image" src="https://github.com/user-attachments/assets/740c615b-f9db-4055-ae1a-607a1fc79b7b" />



