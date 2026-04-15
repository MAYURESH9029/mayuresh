1st Display 1 to 20 using for, while, do-while
 public class LoopDemo {
    public static void main(String[] args) {

        // for loop
        for (int i = 1; i <= 20; i++) {
            System.out.print(i + " ");
        }

        System.out.println();

        // while loop
        int i = 1;
        while (i <= 20) {
            System.out.print(i + " ");
            i++;
        }

        System.out.println();

        // do-while loop
        int j = 1;
        do {
            System.out.print(j + " ");
            j++;
        } while (j <= 20);
    }
}



2nd  String & StringBuffer methods
public class StringDemo {
    public static void main(String[] args) {

        String s = "Hello";
        System.out.println(s.length());
        System.out.println(s.toUpperCase());
        System.out.println(s.toLowerCase());
        System.out.println(s.concat(" Java"));
        System.out.println(s.charAt(1));

        StringBuffer sb = new StringBuffer("World");
        sb.append(" Java");
        sb.insert(5, " Hi");
        sb.replace(0, 5, "Hello");
        sb.delete(0, 2);
        sb.reverse();

        System.out.println(sb);
    }
}

3rd Multidimensional Array

public class MultiArray {
    public static void main(String[] args) {

        int[][] arr = {
            {1, 2, 3},
            {4, 5, 6}
        };

        for (int i = 0; i < arr.length; i++) {
            for (int j = 0; j < arr[i].length; j++) {
                System.out.print(arr[i][j] + " ");
            }
            System.out.println();
        }
    }
}

4th Single & Multilevel Inheritance
class Animal {
    void eat() {
        System.out.println("Eating...");
    }
}

class Dog extends Animal {
    void bark() {
        System.out.println("Barking...");
    }
}

class Puppy extends Dog {
    void weep() {
        System.out.println("Weeping...");
    }
}

public class InheritanceDemo {
    public static void main(String[] args) {
        Puppy p = new Puppy();
        p.eat();
        p.bark();
        p.weep();
    }
}

5th Area using Interface

interface Shape {
    void area();
}

class Rectangle implements Shape {
    int l = 10, b = 5;

    public void area() {
        System.out.println("Area of Rectangle: " + (l * b));
    }
}

class Circle implements Shape {
    double r = 7;

    public void area() {
        System.out.println("Area of Circle: " + (3.14 * r * r));
    }
}

public class InterfaceDemo {
    public static void main(String[] args) {
        Rectangle r = new Rectangle();
        Circle c = new Circle();

        r.area();
        c.area();
    }
}

6th Threads with setPriority

class MyThread extends Thread {
    public void run() {
        System.out.println("Thread: " + Thread.currentThread().getName());
    }
}

public class ThreadDemo {
    public static void main(String[] args) {
        MyThread t1 = new MyThread();
        MyThread t2 = new MyThread();
        MyThread t3 = new MyThread();

        t1.setPriority(Thread.MIN_PRIORITY);
        t2.setPriority(Thread.NORM_PRIORITY);
        t3.setPriority(Thread.MAX_PRIORITY);

        t1.start();
        t2.start();
        t3.start();
    }
}

7th  custom exception 

class NotMatchException extends Exception {
    NotMatchException(String msg) {
        super(msg);
    }
}

public class ExceptionDemo {
    public static void main(String[] args) {
        String str = "India";

        try {
            if (!str.equals("India")) {
                throw new NotMatchException("String not matched");
            } else {
                System.out.println("Matched");
            }
        } catch (NotMatchException e) {
            System.out.println(e.getMessage());
        }
    }
}

8th Login Form (AWT)

import java.awt.*;
import java.awt.event.*;

public class LoginForm extends Frame implements ActionListener {

    Label l1, l2;
    TextField t1, t2;
    Button b;

    LoginForm() {
        l1 = new Label("Username:");
        l2 = new Label("Password:");

        t1 = new TextField();
        t2 = new TextField();
        t2.setEchoChar('*');

        b = new Button("Login");

        setLayout(new FlowLayout());

        add(l1); add(t1);
        add(l2); add(t2);
        add(b);

        b.addActionListener(this);

        setSize(300, 200);
        setVisible(true);
    }

    public void actionPerformed(ActionEvent e) {
        if (t1.getText().equals("admin") && t2.getText().equals("123")) {
            System.out.println("Login Successful");
        } else {
            System.out.println("Login Failed");
        }
    }

    public static void main(String[] args) {
        new LoginForm();
    }
}


9th 5x5 Grid

import java.awt.*;

public class GridDemo extends Frame {
    GridDemo() {
        setLayout(new GridLayout(5, 5));

        for (int i = 1; i <= 25; i++) {
            add(new Button("B" + i));
        }

        setSize(300, 300);
        setVisible(true);
    }

    public static void main(String[] args) {
        new GridDemo();
    }
}

10th key event 
import java.awt.*;
import java.awt.event.*;

public class KeyEventDemo extends Frame implements KeyListener {

    Label l;

    KeyEventDemo() {
        l = new Label();
        add(l);

        addKeyListener(this);

        setSize(300, 200);
        setVisible(true);
    }

    public void keyPressed(KeyEvent e) {
        l.setText("Key Pressed");
    }

    public void keyReleased(KeyEvent e) {}
    public void keyTyped(KeyEvent e) {}

    public static void main(String[] args) {
        new KeyEventDemo();
    }
}

11th URL CLASS 

import java.net.*;

public class URLDemo {
    public static void main(String[] args) throws Exception {
        URL url = new URL("http://www.msbte.org.in");

        System.out.println("Protocol: " + url.getProtocol());
        System.out.println("Host: " + url.getHost());
        System.out.println("Port: " + url.getPort());
        System.out.println("File: " + url.getFile());
    }
}

12th JDBC 

import java.sql.*;

public class StudentDB {
    public static void main(String[] args) throws Exception {

        Connection con = DriverManager.getConnection(
            "jdbc:mysql://localhost:3306/test", "root", "password");

        Statement st = con.createStatement();

        // Create table
        st.executeUpdate("CREATE TABLE Student(id INT, name VARCHAR(20))");

        // Insert
        st.executeUpdate("INSERT INTO Student VALUES(1, 'Ram')");

        // Update
        st.executeUpdate("UPDATE Student SET name='Shyam' WHERE id=1");

        // Delete
        st.executeUpdate("DELETE FROM Student WHERE id=1");

        System.out.println("Operations done successfully");

        con.close();
    }
}