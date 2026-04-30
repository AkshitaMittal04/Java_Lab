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

[Program-16 WAP for the matrix addition using swing class.](Assi-16)

[Program-17 Create one jframe apply 10 buttons on that after clicking on each button a new structure is created.](Assi-17)



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

## Assi-12
```
// Program to demonstrate the use of join() method in Java threads

// Custom thread class
class MyThread extends Thread {

    String name; // to store thread name

    // Constructor to initialize thread name
    MyThread(String name) {
        this.name = name;
    }

    // run() method defines the task of the thread
    public void run() {
        for (int i = 1; i <= 5; i++) {
            System.out.println(name + " -> " + i);
            try {
                Thread.sleep(500); // delay for better visibility
            } catch (Exception e) {
                System.out.println(e);
            }
        }
    }
}

// Main class
public class ThreadJoinDemo {

    public static void main(String[] args) {

        // Creating thread objects
        MyThread t1 = new MyThread("Thread-1");
        MyThread t2 = new MyThread("Thread-2");
        MyThread t3 = new MyThread("Thread-3");

        try {
            // Start and wait for each thread one by one
            t1.start();
            t1.join();   // main thread waits until t1 finishes

            t2.start();
            t2.join();   // waits for t2

            t3.start();
            t3.join();   // waits for t3

        } catch (Exception e) {
            System.out.println(e);
        }

        System.out.println("All threads completed.");
    }
}
```
<img width="329" height="373" alt="image" src="https://github.com/user-attachments/assets/5b5d1a39-fd55-46f6-9174-0a4a5e174e7a" />


## Assi-13

```
// Import required packages for GUI
import javax.swing.*;
import java.awt.*;
import java.awt.event.*;

// Class extending JFrame and implementing ActionListener
public class AdditionGUI extends JFrame implements ActionListener {

    // Declare components
    JTextField num1, num2, result;
    JButton addBtn;

    // Constructor to design GUI
    public AdditionGUI() {

        setTitle("Addition of Two Numbers"); // Set window title
        setSize(500, 250); // Set window size
        setLayout(new GridLayout(4, 2, 15, 15)); // Layout with rows, columns, spacing
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE); // Close operation

        // Create text fields
        num1 = new JTextField();
        num2 = new JTextField();
        result = new JTextField();

        result.setEditable(false); // Result field should not be editable

        // Create button
        addBtn = new JButton("Add");
        addBtn.setPreferredSize(new Dimension(120, 40));

        // Register event listener
        addBtn.addActionListener(this);

        // Add components to frame
        add(new JLabel("Number 1:"));
        add(num1);

        add(new JLabel("Number 2:"));
        add(num2);

        add(new JLabel("Result:"));
        add(result);

        add(new JLabel("")); // Empty label for spacing
        add(addBtn);

        setLocationRelativeTo(null); // Center the window
        setVisible(true); // Make frame visible
    }

    // Event handling method
    public void actionPerformed(ActionEvent e) {
        try {
            // Convert input text to integers
            int a = Integer.parseInt(num1.getText());
            int b = Integer.parseInt(num2.getText());

            // Perform addition and display result
            result.setText(String.valueOf(a + b));

        } catch (Exception ex) {
            // Show error message if input is invalid
            JOptionPane.showMessageDialog(this, "Enter valid numbers!");
        }
    }

    // Main method
    public static void main(String[] args) {
        new AdditionGUI(); // Create object to launch GUI
    }
}

```
<img width="476" height="236" alt="image" src="https://github.com/user-attachments/assets/bad39b8d-fe74-400f-892b-09fc212e675c" />

## Assi-14
```

// Import required packages
import javax.swing.*;
import java.awt.*;
import java.awt.event.*;
import java.sql.*;

// Main class
public class RegistrationForm extends JFrame implements ActionListener {

    // Declare components
    JTextField firstNameField, lastNameField, ageField, emailField, phoneField, cityField;
    JTextArea addressArea;
    JRadioButton maleBtn, femaleBtn;
    JComboBox<String> courseBox, branchBox;
    JButton submitBtn, clearBtn;

    // Constructor to design GUI
    RegistrationForm() {

        setTitle("Student Registration Form");
        setSize(600, 650);
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        setLocationRelativeTo(null);
        setLayout(null);

        // Title
        JLabel title = new JLabel("Student Registration Form");
        title.setFont(new Font("Arial", Font.BOLD, 24));
        title.setBounds(140, 20, 350, 40);
        add(title);

        // First Name
        add(new JLabel("First Name:")).setBounds(80, 90, 120, 25);
        firstNameField = new JTextField();
        firstNameField.setBounds(220, 90, 250, 25);
        add(firstNameField);

        // Last Name
        add(new JLabel("Last Name:")).setBounds(80, 130, 120, 25);
        lastNameField = new JTextField();
        lastNameField.setBounds(220, 130, 250, 25);
        add(lastNameField);

        // Gender
        add(new JLabel("Gender:")).setBounds(80, 170, 120, 25);
        maleBtn = new JRadioButton("Male");
        femaleBtn = new JRadioButton("Female");

        maleBtn.setBounds(220, 170, 80, 25);
        femaleBtn.setBounds(310, 170, 100, 25);

        ButtonGroup bg = new ButtonGroup();
        bg.add(maleBtn);
        bg.add(femaleBtn);

        add(maleBtn);
        add(femaleBtn);

        // Age
        add(new JLabel("Age:")).setBounds(80, 210, 120, 25);
        ageField = new JTextField();
        ageField.setBounds(220, 210, 250, 25);
        add(ageField);

        // Email
        add(new JLabel("Email:")).setBounds(80, 250, 120, 25);
        emailField = new JTextField();
        emailField.setBounds(220, 250, 250, 25);
        add(emailField);

        // Phone
        add(new JLabel("Phone:")).setBounds(80, 290, 120, 25);
        phoneField = new JTextField();
        phoneField.setBounds(220, 290, 250, 25);
        add(phoneField);

        // Course
        add(new JLabel("Course:")).setBounds(80, 330, 120, 25);
        courseBox = new JComboBox<>(new String[]{"B.Tech", "BCA", "MCA"});
        courseBox.setBounds(220, 330, 250, 25);
        add(courseBox);

        // Branch
        add(new JLabel("Branch:")).setBounds(80, 370, 120, 25);
        branchBox = new JComboBox<>(new String[]{"CSE", "IT", "ECE"});
        branchBox.setBounds(220, 370, 250, 25);
        add(branchBox);

        // City
        add(new JLabel("City:")).setBounds(80, 410, 120, 25);
        cityField = new JTextField();
        cityField.setBounds(220, 410, 250, 25);
        add(cityField);

        // Address
        add(new JLabel("Address:")).setBounds(80, 450, 120, 25);
        addressArea = new JTextArea();
        addressArea.setBounds(220, 450, 250, 70);
        add(addressArea);

        // Buttons
        submitBtn = new JButton("Submit");
        submitBtn.setBounds(160, 550, 120, 35);
        submitBtn.addActionListener(this);
        add(submitBtn);

        clearBtn = new JButton("Clear");
        clearBtn.setBounds(310, 550, 120, 35);
        clearBtn.addActionListener(this);
        add(clearBtn);

        setVisible(true);
    }

    // Database Connection Method
    public Connection getConnection() {
        try {
            Class.forName("oracle.jdbc.OracleDriver");

            return DriverManager.getConnection(
                "jdbc:oracle:thin:@localhost:1521:XE",
                "stress_user",
                "Stress123"
            );

        } catch (Exception e) {
            JOptionPane.showMessageDialog(this, "DB Error: " + e.getMessage());
            return null;
        }
    }

    // Event Handling
    public void actionPerformed(ActionEvent e) {

        if (e.getSource() == submitBtn) {

            try {
                Connection con = getConnection();

                String query = "INSERT INTO registration VALUES (reg_seq.NEXTVAL,?,?,?,?,?,?,?,?,?,?)";

                PreparedStatement pst = con.prepareStatement(query);

                pst.setString(1, firstNameField.getText());
                pst.setString(2, lastNameField.getText());
                pst.setString(3, maleBtn.isSelected() ? "Male" : "Female");
                pst.setInt(4, Integer.parseInt(ageField.getText()));
                pst.setString(5, emailField.getText());
                pst.setString(6, phoneField.getText());
                pst.setString(7, courseBox.getSelectedItem().toString());
                pst.setString(8, branchBox.getSelectedItem().toString());
                pst.setString(9, cityField.getText());
                pst.setString(10, addressArea.getText());

                pst.executeUpdate();

                JOptionPane.showMessageDialog(this, "Registration Successful!");
                con.close();

            } catch (Exception ex) {
                JOptionPane.showMessageDialog(this, "Error: " + ex.getMessage());
            }
        }

        // Clear Button
        if (e.getSource() == clearBtn) {
            firstNameField.setText("");
            lastNameField.setText("");
            ageField.setText("");
            emailField.setText("");
            phoneField.setText("");
            cityField.setText("");
            addressArea.setText("");
        }
    }

    // Main Method
    public static void main(String[] args) {
        new RegistrationForm();
    }
}
```
<img width="732" height="797" alt="image" src="https://github.com/user-attachments/assets/58081e78-4144-4273-b21d-c28fd39b2225" />

## Assi-15
```
// Import required packages
import javax.swing.*;
import java.awt.*;
import java.awt.event.*;

// Main class
public class CalculatorGUI extends JFrame implements ActionListener {

    // Display field
    JTextField display;

    // Variables to store numbers and operator
    String operator = "";
    double num1 = 0, num2 = 0;

    // Constructor to design GUI
    public CalculatorGUI() {

        setTitle("Calculator"); // Set title
        setSize(300, 400); // Set size
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        setLayout(new BorderLayout());

        // ===== DISPLAY =====
        display = new JTextField();
        display.setFont(new Font("Arial", Font.BOLD, 20));
        display.setHorizontalAlignment(JTextField.RIGHT);
        add(display, BorderLayout.NORTH);

        // ===== BUTTON PANEL =====
        JPanel panel = new JPanel(new GridLayout(4, 4, 5, 5));

        // Button labels
        String buttons[] = {
            "7", "8", "9", "/",
            "4", "5", "6", "*",
            "1", "2", "3", "-",
            "0", "C", "=", "+"
        };

        // Create buttons dynamically
        for (String text : buttons) {
            JButton btn = new JButton(text);
            btn.setFont(new Font("Arial", Font.BOLD, 16));
            btn.addActionListener(this); // Register event
            panel.add(btn);
        }

        add(panel, BorderLayout.CENTER);

        setVisible(true); // Make GUI visible
    }

    // Event handling method
    public void actionPerformed(ActionEvent e) {

        String cmd = e.getActionCommand();

        // If number button is pressed
        if (cmd.matches("[0-9]")) {
            display.setText(display.getText() + cmd);
        }

        // If operator button is pressed
        else if (cmd.matches("[+\\-*/]")) {
            num1 = Double.parseDouble(display.getText());
            operator = cmd;
            display.setText("");
        }

        // If equals button is pressed
        else if (cmd.equals("=")) {
            num2 = Double.parseDouble(display.getText());
            double result = 0;

            switch (operator) {
                case "+": result = num1 + num2; break;
                case "-": result = num1 - num2; break;
                case "*": result = num1 * num2; break;
                case "/": result = num1 / num2; break;
            }

            display.setText(String.valueOf(result));
        }

        // If clear button is pressed
        else if (cmd.equals("C")) {
            display.setText("");
            num1 = num2 = 0;
            operator = "";
        }
    }

    // Main method
    public static void main(String[] args) {
        new CalculatorGUI();
    }
}
```
<img width="365" height="489" alt="image" src="https://github.com/user-attachments/assets/9126880a-023c-48dc-8056-6b76c7c969ef" />

## Assi-16
```
// Import required packages
import javax.swing.*;
import java.awt.*;
import java.awt.event.*;

// Main class
public class MatrixAdditionGUI extends JFrame implements ActionListener {

    // 2x2 matrices for input and result
    JTextField[][] A = new JTextField[2][2];
    JTextField[][] B = new JTextField[2][2];
    JTextField[][] R = new JTextField[2][2];

    JButton addButton;

    // Constructor to design GUI
    public MatrixAdditionGUI() {

        setTitle("Matrix Addition"); // Title
        setSize(500, 400); // Size
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        setLayout(new BorderLayout(10, 10));

        // ===== TITLE =====
        JLabel title = new JLabel("Matrix Addition", JLabel.CENTER);
        title.setFont(new Font("Arial", Font.BOLD, 18));
        add(title, BorderLayout.NORTH);

        // ===== CENTER PANEL =====
        JPanel center = new JPanel(new GridLayout(1, 3, 20, 20));
        center.setBorder(BorderFactory.createEmptyBorder(20, 20, 20, 20));

        // Add 3 matrices (A, B, Result)
        center.add(createMatrixPanel(A, "Matrix A"));
        center.add(createMatrixPanel(B, "Matrix B"));
        center.add(createMatrixPanel(R, "Result"));

        add(center, BorderLayout.CENTER);

        // ===== BUTTON PANEL =====
        JPanel bottom = new JPanel();
        addButton = new JButton("Add");
        addButton.setPreferredSize(new Dimension(100, 40));
        addButton.addActionListener(this);

        bottom.add(addButton);
        add(bottom, BorderLayout.SOUTH);

        setVisible(true); // Show GUI
    }

    // Method to create a matrix panel
    JPanel createMatrixPanel(JTextField[][] matrix, String title) {

        JPanel panel = new JPanel(new GridLayout(2, 2, 5, 5));
        panel.setBorder(BorderFactory.createTitledBorder(title));

        for (int i = 0; i < 2; i++) {
            for (int j = 0; j < 2; j++) {

                matrix[i][j] = new JTextField();
                matrix[i][j].setHorizontalAlignment(JTextField.CENTER);

                // Result matrix should not be editable
                if (title.equals("Result")) {
                    matrix[i][j].setEditable(false);
                    matrix[i][j].setBackground(new Color(230, 230, 230));
                }

                panel.add(matrix[i][j]);
            }
        }
        return panel;
    }

    // Event handling
    public void actionPerformed(ActionEvent e) {
        try {
            for (int i = 0; i < 2; i++) {
                for (int j = 0; j < 2; j++) {

                    // Read values from matrices
                    int a = Integer.parseInt(A[i][j].getText());
                    int b = Integer.parseInt(B[i][j].getText());

                    // Perform addition
                    R[i][j].setText(String.valueOf(a + b));
                }
            }
        } catch (Exception ex) {
            JOptionPane.showMessageDialog(this, "Enter valid numbers!");
        }
    }

    // Main method
    public static void main(String[] args) {
        new MatrixAdditionGUI();
    }
}
```
<img width="591" height="492" alt="image" src="https://github.com/user-attachments/assets/f5d7f057-4b93-46ea-8bb8-b192264c31e4" />


## Assi-17
```
// Import required packages
import javax.swing.*;
import java.awt.*;
import java.awt.event.*;

// Main class
public class ShapeDrawer extends JFrame implements ActionListener {

    String shape = ""; // stores selected shape

    // Constructor to design GUI
    public ShapeDrawer() {

        setTitle("Shape Drawer"); // Title
        setSize(600, 500); // Window size
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        setLayout(new BorderLayout());

        // Panel for buttons
        JPanel panel = new JPanel(new GridLayout(2, 5));

        // Button names
        String buttons[] = {
            "Circle", "Oval", "Rectangle", "Square", "Line",
            "Arc", "RoundRect", "3D Rect", "Fill Oval", "Fill Rect"
        };

        // Create buttons dynamically
        for (String name : buttons) {
            JButton btn = new JButton(name);
            btn.addActionListener(this); // Register event
            panel.add(btn);
        }

        add(panel, BorderLayout.NORTH);

        setVisible(true); // Show GUI
    }

    // Event handling method
    public void actionPerformed(ActionEvent e) {
        shape = e.getActionCommand(); // Get button name
        repaint(); // Redraw screen
    }

    // Method to draw shapes
    public void paint(Graphics g) {
        super.paint(g);

        g.setColor(Color.BLUE); // Set drawing color

        switch (shape) {

            case "Circle":
                g.drawOval(200, 150, 100, 100);
                break;

            case "Oval":
                g.drawOval(200, 150, 150, 100);
                break;

            case "Rectangle":
                g.drawRect(200, 150, 150, 100);
                break;

            case "Square":
                g.drawRect(200, 150, 100, 100);
                break;

            case "Line":
                g.drawLine(200, 150, 350, 250);
                break;

            case "Arc":
                g.drawArc(200, 150, 150, 100, 0, 180);
                break;

            case "RoundRect":
                g.drawRoundRect(200, 150, 150, 100, 30, 30);
                break;

            case "3D Rect":
                g.draw3DRect(200, 150, 150, 100, true);
                break;

            case "Fill Oval":
                g.fillOval(200, 150, 150, 100);
                break;

            case "Fill Rect":
                g.fillRect(200, 150, 150, 100);
                break;
        }
    }

    // Main method
    public static void main(String[] args) {
        new ShapeDrawer();
    }
}
```
<img width="731" height="615" alt="image" src="https://github.com/user-attachments/assets/dbb97b35-7341-4f34-9ee5-0307579f0bed" />






