# JavaLab4thsem

##################  part-A  #####################


1. Design a java Program to add two matrix using multi-dimensional arrays, pass
two-dimensional array as parameter to the method. 


import java.util.*;
public class matrix_add {
	static void printMatrix(int M[][], int row, int col) {
		for (int i = 0; i < row; i++) {
			for (int j = 0; j < col; j++) {
				System.out.print(M[i][j] + " ");
			}
			System.out.println();
		}
	}

	static void Multiply(int row1, int col1, int arr1[][], int row2, int col2, int arr2[][]) {
		System.out.println("First Matrix:");
		printMatrix(arr1, row1, col1);
		System.out.println("Second Matrix:");
		printMatrix(arr2, row2, col2);
		int arr3[][] = new int[row1][col2];
		for (int i = 0; i < row1; i++) {
			for (int j = 0; j < col2; j++) {
				arr3[i][j] = arr1[i][j] + arr2[i][j];
			}
		}
		System.out.println();
		System.out.println("Resultant Matrix:");
		printMatrix(arr3, row1, col2);
	}

	public static void main(String[] args) {
		Scanner sc = new Scanner(System.in);
		System.out.println("Enter the number of rows in first matrix");
		int row1 = sc.nextInt();
		System.out.println("Enter the number of columns in first matrix");
		int col1 = sc.nextInt();
		System.out.println("Enter the number of rows in second matrix");
		int row2 = sc.nextInt();
		System.out.println("Enter the number of columns in second matrix");
		int col2 = sc.nextInt();
		int arr1[][] = new int[row1][col1];
		int arr2[][] = new int[row2][col2];
		System.out.println("Enter the elements of first matrix:");
		for (int i = 0; i < row1; i++) {
			for (int j = 0; j < col1; j++) {
				arr1[i][j] = sc.nextInt();
			}
		}
		System.out.println("");
		System.out.println("Enter the elements of second matrix:");
		for (int i = 0; i < row2; i++) {
			for (int j = 0; j < col2; j++) {
				arr2[i][j] = sc.nextInt();
			}
		}
		Multiply(row1, col1, arr1, row2, col2, arr2);
	}
}



###############Matrix Multy###################

import java.util.*;
public class matrix_multiply {
	static void printMatrix(int M[][], int row, int col) {
		for (int i = 0; i < row; i++) {
			for (int j = 0; j < col; j++) {
				System.out.print(M[i][j] + " ");
			}
			System.out.println();
		}
	}

	static void Multiply(int row1, int col1, int arr1[][], int row2, int col2, int arr2[][]) {
		System.out.println("First Matrix:");
		printMatrix(arr1, row1, col1);
		System.out.println("Second Matrix:");
		printMatrix(arr2, row2, col2);
		int arr3[][] = new int[row1][col2];
		for (int i = 0; i < row1; i++) {
			for (int j = 0; j < col2; j++) {
				for(int k=0; k<row2; k++) {
                    arr3[i][j] += arr1[i][j] * arr2[i][j];
                }
			}
		}
		System.out.println("Resultant Matrix:");
		printMatrix(arr3, row1, col2);
	}

	public static void main(String[] args) {
		Scanner sc = new Scanner(System.in);
		System.out.println("Enter the number of rows in first matrix");
		int row1 = sc.nextInt();
		System.out.println("Enter the number of columns in first matrix");
		int col1 = sc.nextInt();
		System.out.println("Enter the number of rows in second matrix");
		int row2 = sc.nextInt();
		System.out.println("Enter the number of columns in second matrix");
		int col2 = sc.nextInt();
		if (row2 != col1) {
			System.out.println("Multiplication Not Possible");
		}
		else {
			int arr1[][] = new int[row1][col1];
			int arr2[][] = new int[row2][col2];
			System.out.println("Enter the elements of first matrix:");
			for (int i = 0; i < row1; i++) {
				for (int j = 0; j < col1; j++) {
					arr1[i][j] = sc.nextInt();
				}
			}
			System.out.println("");
			System.out.println("Enter the elements of second matrix:");
			for (int i = 0; i < row2; i++) {
				for (int j = 0; j < col2; j++) {
					arr2[i][j] = sc.nextInt();
				}
			}
			Multiply(row1, col1, arr1, row2, col2, arr2);
		}
	}
}















2. Design a java program with one method to put even & odd elements of an array
in 2 separate arrays, and another method to find the transpose of the matrix by
implementing the concept of method overriding

import java.util.*;

class EvenOdd {
    void meth() {
        System.out.print("Enter size of matrix: ");
        Scanner sc = new Scanner(System.in);
        int x = sc.nextInt();
        int l = 0, k = 0;
        int a[] = new int[x];
        int even[] = new int[x];
        int odd[] = new int[x];
        System.out.println("Enter the elements of matrix: ");
        for (int i = 0; i < x; i++) {
            a[i] = sc.nextInt();
        }

        for (int i = 0; i < x; i++) {
            if (a[i] % 2 == 0) {
                even[k] = a[i];
                k++;
            }
            else {
                odd[l] = a[i];
                l++;
            }
        }
        System.out.println("Even matrix: ");
        for (int i = 0; i < k; i++) {
            System.out.print(even[i] + " ");
        }
        System.out.println();
        System.out.println("Odd matrix: ");
        for (int i = 0; i < l; i++) {
            System.out.print(odd[i] + " ");
        }
        System.out.println();
    }
}

class Transpose extends EvenOdd {
    void meth() {
        super.meth();
        int m, n;
        System.out.println();
        System.out.print("Enter number of rows: ");
        Scanner track = new Scanner(System.in);
        m = track.nextInt();
        System.out.print("Enter number of columns: ");
        n = track.nextInt();
        int a[][] = new int[m][n];
        int b[][] = new int[m][n];
        System.out.println("Enter a 2D matrix: ");
        for (int i = 0; i < m; i++) {
            for (int j = 0; j < n; j++) {
                a[i][j] = track.nextInt();
            }
        }
        for (int i = 0; i < m; i++) {
            for (int j = 0; j < n; j++) {
                b[i][j] = a[j][i];
            }
        }

        System.out.println("Entered matrix is: ");
        for (int i = 0; i < m; i++) {
            for (int j = 0; j < n; j++) {
                System.out.print(a[i][j] + "  ");
            }
            System.out.println();
        }
        System.out.println();
        System.out.println("Transpose of matrix is");
        for (int i = 0; i < m; i++) {
            for (int j = 0; j < n; j++) {
                System.out.print(b[i][j] + "  ");
            }
            System.out.println();
        }
    }
}

class matrix_transpose {
    public static void main(String[] args) {
        Transpose obj = new Transpose();
        obj.meth();
    }
}











3. Design a java code to accept a value for ‘n’ and calculate the total number of all
possible squares in a square matrix





// Design a java code to accept a value for n and calculate the total number of all possible squares in a square matrix
import java.util.*;
public class square_matrix
{
    public static void main(String[] args)
    {
        int size, sum=0;
        Scanner sc = new Scanner(System.in);
        System.out.println("Enter the size of the matrix");
        size = sc.nextInt();
        if (size<1)
        {
            System.out.println("Invalid Input");
        }    
        else
        {
            while(size!=0)
            {
                sum += size*size;
                size--;
            }
        }
        System.out.println("Total number of square matrices are "+ sum);
    }
}







4. Design a code for a simple calculator which takes input from the user and also
details of what operation must be performed. The user can input only 2 operands.



import java.util.*;
public class simple_calculator {
    public static void main(String args[]) {
        int op1, op2, res;
        Scanner sc = new Scanner(System.in);
        System.out.println("Enter ther first operand");
        op1 = sc.nextInt();
        System.out.println("Enter the second operand");
        op2 = sc.nextInt();
        char operator;
        System.out.print("Enter the operator (+,-,*,/,%): ");
        System.out.println();
        operator = sc.next().charAt(0);
        switch (operator) {
            case '+':
                res = op1 + op2;
                System.out.println("The addition is " + res);
                break;
            case '-':
                res = op1 - op2;
                System.out.println("The subtraction is " + res);
                break;
            case '*':
                res = op1 * op2;
                System.out.println("The multiplication is " + res);
                break;
            case '/':
                res = op1 / op2;
                System.out.println("The division is " + res);
                break;
            case '%':
                res = op1 % op2;
                System.out.println("The division is " + res);
                break;
            default:
                System.out.println("Invalid Input");
                break;
        }
    }
}








5. Design a java program to calculate the difference between the sum of the odd
level and even level nodes of a binary tree
class Node {
    int data;
    Node left, right;

    public Node(int item) {
        data = item;
        left = right = null;
    }
}

class binary_tree {
    Node root;
    int getLevelDiff(Node node) {
        if (node == null)
            return 0;
        return node.data - getLevelDiff(node.left) - getLevelDiff(node.right);
    }

    public static void main(String[] args) {
        binary_tree tree = new binary_tree();
        tree.root = new Node(1);
        tree.root.left = new Node(2);
        tree.root.right = new Node(3);
        tree.root.left.left = new Node(4);
        tree.root.left.right = new Node(5);
        tree.root.right.left = new Node(6);
        tree.root.right.right = new Node(7);
        int levelDiff = tree.getLevelDiff(tree.root);
        System.out.println("Difference between sum of odd and even level nodes: " + levelDiff);
    }
}













6.Design a java code to accept 5 strings from the user and print them in lexicographical
order


import java.util.*;
public class lexicographic {
    public static void main(String[] args) {
        System.out.println("Enter five names: ");
        String array[] = new String[5];       // Declaration of string array
        Scanner sc = new Scanner(System.in);
        for (int i = 0; i < 5; i++) {
            array[i] = sc.nextLine();
        }
        Arrays.sort(array);
        System.out.print("Sorted list is: ");
        for (int i = 0; i < 5; i++) {
            System.out.print(array[i] + " ");
        }
    }
}








7. Design a java code for implementing Binary Search, pass array as parameter to
the method

import java.util.*;
public class binary_search {
    int binarySearch(int arr[], int low, int high, int x) {
        if (high >= low) {
            int mid = low+(high-low)/2;
            if (arr[mid] == x)
                return mid;
            else if (arr[mid] > x)
                return binarySearch(arr, low, mid-1, x);
            else
                return binarySearch(arr, mid+1, high, x);
        }
        return -1;
    }
    public static void main(String args[]) {
        binary_search ob = new binary_search();
        int arr[] = { 10, 20, 30, 40, 50 };
        int n = arr.length;
        int x = 30;
        int result = ob.binarySearch(arr, 0, n - 1, x);
        if (result == -1)
            System.out.println("Element is not present in array");
        else
            System.out.println("Element is present at index " + result);
    }
}




8. Design a java code to implement method overloading.

import java.util.*;
public class method_overloading
{
    public void add(int a, int b)
    {
        int sum = a + b;
        System.out.println("Sum of two integers: " + sum);
    }

    public void add(double a, double b)
    {
        double sum = a + b;
        System.out.println("Sum of two doubles: " + sum);
    }

    public void add(String a, String b)
    {
        String result = a + b;
        System.out.println("Concatenation of two strings: " + result);
    }

    public static void main(String[] args)
    {
        method_overloading example = new method_overloading();
        // Call the add() method with different argument types
        example.add(5, 10);
        example.add(3.5, 2.8);
        example.add("Hello, ", "world!");
    }
}





9. Design a java program to implement multiple inheritance using an interface.

import java.util.*;
interface motar1 {
    int speed = 90;
    public void distance();
}
interface motar2 {
    int distance = 200;
    public void speed();
}

class Vehicle implements motar1, motar2 {
    public void distance() {
        int distance = speed * 100;
        System.out.println("Distance is: " + distance);
    }

    public void speed() {
        int speed = distance / 100;
        System.out.println("Speed is: " + speed);
    }
}

public class multiple_inheritance {
    public static void main(String[] args) {
        Vehicle obj = new Vehicle();
        obj.distance();
        obj.speed();
    }
}






10. Design a code to print a pyramid based on level entered by the user

import java.util.*;
public class Pattern
{
    public static void main(String[] args)
    {
        int rows = 5, k = 0, count = 0, count1 = 0;    
        for (int i = 1; i <= rows; ++i)
        {
            for (int space = 1; space <= rows - i; ++space)
            {
                System.out.print("  ");
                ++count;
            }
            while (k != 2 * i - 1)
            {
                if (count <= rows-1)
                {
                    System.out.print((i + k) + " ");
                    ++count;
                }
                else
                {
                    ++count1;
                    System.out.print((i + k - 2 * count1) + " ");
                }
                ++k;
            }
            count1 = count = k = 0;
            System.out.println();
        }
    }
}






11. Write a Java program to find digit sum two digit number until the digit sum is less
than 10. 


import java.util.*;
public class sumofdigit {
    public static void main(String[] args) {
        int num, temp, sum = 0;
        Scanner sc = new Scanner(System.in);
        System.out.println("Enter a number");
        num = sc.nextInt();
        while (num != 0) {
            while (num != 0) {
                temp = num % 10;
                sum = sum + temp;
                num = num/10;
            }
            if (sum >= 10) {
                System.out.println("Sum " + sum);
                num = sum;
                sum = 0;
            }
        }
        System.out.println("Sum in single digit is: "+ sum);
    }
}





12. Design a java code which accepts a number (which is non-zero and positive) from
the user and then checks if it is a happy number or not. Implement it using nested
interface concept

import java.util.*;
interface yes {
    int check(int num);
}

class Happy implements yes {
    public int check(int num) {
        int rem = 0, sum = 0;
        // calculate the sum of squares of each digit
        while (num > 0) {
            rem = num % 10;
            sum = sum + (rem * rem);
            num = num / 10;
        }
        return sum;
    }
}

public class happy_number {
    public static void main(String[] args) {
        Happy obj = new Happy();
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter a number: ");
        int num = sc.nextInt();
        int finalVal = num;
        while (finalVal != 1 && finalVal != 4) {
            finalVal = obj.check(finalVal);
        }
        if (finalVal == 1) {
            System.out.println(num + " is a Happy Number");
        }
        else {
            System.out.println(num + " is not a Happy Number");
        }
    }
}






13. Design an java code which accepts a Room Number, Mobile Number and Name
of the Customer and generate a 6 Character Unique Password

import java.util.*;
public class password_generator {
    public static void main(String args[]) {
        int rno, sum = 0, temp;
        long ph;
        String pw = new String();
        String name;
        Scanner sc = new Scanner(System.in);
        System.out.println("Enter the Room Number");
        rno = sc.nextInt();
        int rno1 = rno;
        System.out.println("Enter the Mobile Number");
        ph = sc.nextLong();
        System.out.println("Enter the Name");
        name = sc.next();
        char sym[] = { ')', '@', '#', '$', '%', '^', '!', '&', '(', '*' };
        while(rno != 0) {
            while (rno != 0) {
                temp = rno % 10;
                sum = sum + temp;
                rno = rno / 10;
            }
            if (sum >= 10) {
                rno = sum;
                sum = 0;
            }
        }
        int c = rno1 / 100;
        int len = name.length();
        System.out.println("Password is: ");
        pw = "" + name.charAt(0) + (ph % 10) + sum + sym[c] + name.charAt(len - 1);
        System.out.println(pw);
    }
}













##################  part-B  #####################


1.Develop a small java application, which accepts employee id from the command prompt
and displays the details using arrays.


->Emp No 
->Emp Name
->Department 
->Designation and Salary
Your may assume that the array is initialized with the following details

Salary is calculated as Basic+HRA+DA-IT. (DA details are given in the Designation table)
Designation details:



Use Switch-Case to print Designation in the output and to find the value of DA for a
particular employee





import java.util.*;

public class prac{
    public void calc(int id){
        int[] EmpId = { 1001, 1002, 1003, 1004, 1005, 1006, 1007 };
		String[] EmpName = { "Abc", "Opqr", "Ghi", "Wxyz", "Jklmn", "Stuv", "Def" };
		String[] JoinDate = { "01/04/2009", "23/08/2012", "12/11/2008", "29/01/2013", "16/07/2005", "01/01/2000","12/06/2006" };
		char[] DesigCode = { 'e', 'c', 'k', 'r', 'm', 'e', 'c' };
		String[] Department = { "R&D", "PM", "Acct", "Front Desk", "Engg", "Manufacturing", "PM" };
		double[] Basic = { 20000, 30000, 10000, 12000, 50000, 23000, 29000 };
		double[] HRA = { 8000, 12000, 8000, 6000, 20000, 9000, 12000 };
		double[] IT = { 3000, 9000, 1000, 2000, 20000, 4400, 10000 };
		char[] DesignationCode = { 'e', 'c', 'k', 'r', 'm' };
		String[] Designation = { "Engineer", "Consultant", "Clerk", "Receptionist", "Manager" };
		double[] DA = { 20000, 32000, 12000, 15000, 40000 };
        for (int i = 0; i < EmpId.length; i++) {
			if (EmpId[i] == id) {
				System.out.println("Emp Id\tEmp Name  Department\tDesignation\tDA\tSalary");
				System.out.print(EmpId[i]+"\t"+EmpName[i]+"\t\t"+Department[i]);
				for (int j = 0; j < DesignationCode.length; j++) {
					if (DesigCode[i] == DesignationCode[j]) {
						System.out.print("\t"+Designation[j]+"\t"+DA[i]+"\t");
						double sum = Basic[i]+HRA[i]+DA[j]-IT[i];
						System.out.println(sum);
					}
				}
			}
		}
    }

	public static void main(String[] args) {
        prac obj = new prac();
		Scanner sc =  new Scanner(System.in);
		System.out.println("Enter Employee ID: ");
		int id = sc.nextInt();
        switch (id) {
            case 1001: obj.calc(id); break;
            case 1002: obj.calc(id); break;
            case 1003: obj.calc(id); break;
            case 1004: obj.calc(id); break;
            case 1005: obj.calc(id); break;
            case 1006: obj.calc(id); break;
            case 1007: obj.calc(id); break;
            default:
                System.out.println("There is no employee with EmpId: " + id);
                break;
        }
	}
}












2.Develop a producer-consumer problem using the concept of multithreading


Producer Consumer-- file 
program1 file  ---psvm -- Threa1 andd thread 2





3. Design and Implement GUI for managing Employee Details using concepts of Files

import java.awt.*;
import java.awt.event.*;
import java.io.*;
import javax.swing.*;

public class EmployeeFile {
    private static Color black;
    public static void main(String[] args) {

        JFrame frameobj = new JFrame(); // creating frame
        frameobj.setSize(500, 500); // declaring frame size
        GridLayout g1 = new GridLayout(5, 2); // layout of the frame
        frameobj.setLayout(g1); // layout is set to the frame created

        JPanel p1 = new JPanel(); // creating panels
        JPanel p2 = new JPanel();
        JPanel p3 = new JPanel();
        JPanel p4 = new JPanel();
        JPanel p5 = new JPanel();
        JPanel p6 = new JPanel();
        JPanel p7 = new JPanel();
        JPanel p8 = new JPanel();
        JPanel p9 = new JPanel();
        JPanel p10 = new JPanel();

        JLabel l1 = new JLabel("NAME"); // creating labels
        JLabel l2 = new JLabel("ID");
        JLabel l3 = new JLabel("DOJ");
        JLabel l4 = new JLabel("DOB");

        JTextField f1 = new JTextField(); // create obj for txtfield
        JTextField f2 = new JTextField();
        JTextField f3 = new JTextField();
        JTextField f4 = new JTextField();

        f1.setPreferredSize(new Dimension(200, 30)); // size of txtfield
        f2.setPreferredSize(new Dimension(200, 30));
        f3.setPreferredSize(new Dimension(200, 30));
        f4.setPreferredSize(new Dimension(200, 30));

        JButton b1 = new JButton("SUBMIT");
        JButton b2 = new JButton("RESET");
        b1.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                File fileobj = new File("C:\\Users\\Piyush Narayan\\OneDrive\\Desktop\file.txt");
                try {
                    FileWriter fw = new FileWriter(fileobj.getAbsoluteFile(), true);
                    System.out.println("\nNAME: "+f1.getText()+"\n"+"ID : "+f2.getText()+"\n"+"DOJ:"+f3.getText()+"\n"+"DOB"+f4.getText()+"\n");
                    fw.write("Name:"+f1.getText()+"\n"+"ID:"+f2.getText()+"\n"+"DOJ:"+f3.getText()+"\n"+"DOB"+f4.getText()+"\n");
                    fw.close();
                } catch (IOException e1) {
                    e1.printStackTrace();
                }
            }
        });
        b2.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                f1.setText("");
                f2.setText(null);
                f3.setText(null);
                f4.setText(null);
            }
        });
        p1.add(l1); // add labels to panels where labels=name,id,doj,dob
        p3.add(l2);
        p5.add(l3);
        p7.add(l4);
        p2.add(f1); // add textfield to panels where txtfield is user defined
        p4.add(f2);
        p6.add(f3);
        p8.add(f4);
        p9.add(b1); // add buttons to panel
        p10.add(b2);

        // l1.setBorder(BorderFactory.createLineBorder(Color.black));
        l1.setBorder(BorderFactory.createLineBorder(black, 10));
        l2.setBorder(BorderFactory.createLineBorder(black, 10));
        l3.setBorder(BorderFactory.createLineBorder(black, 10));
        l4.setBorder(BorderFactory.createLineBorder(black, 10));
        frameobj.add(p1); // add panels to frames
        frameobj.add(p2);
        frameobj.add(p3);
        frameobj.add(p4);
        frameobj.add(p5);
        frameobj.add(p6);
        frameobj.add(p7);
        frameobj.add(p8);
        frameobj.add(p9);
        frameobj.add(p10);
        frameobj.setVisible(true);
    }
}






4.Write a program to implement different exception handling methods in java.




import java.util.*;
public class exception_handling {
    public static void main(String[] args) {
        try {
            try {
                int[] a = { 1, 2, 3 };
                System.out.println(a[3]);
            } catch (ArrayIndexOutOfBoundsException e) {
                System.out.println("Exception Type: "+ e);
            }
            System.out.println(4 / 0);
        } catch (ArithmeticException e) {
            System.out.println("Exception Type: "+ e);
        }
    }
}





5.Design and implement a simple inventory central system for a small video rental store
using constructors and Object List


##############Video##########################
public class Video {
	String Name;
	boolean status;
	double rating;
	public Video(String n, boolean s, double r) {
		super();
		this.Name = n;
		this.status = s;
		this.rating = r;
	}
	public String getmName() {
		return Name;
	}
	public void setmName(String mName) {
		this.Name = mName;
	}
	public boolean isStatus() {
		return status;
	}
	public void setStatus(boolean status) {
		this.status = status;
	}
	public double getRating() {
		return rating;
	}
	public double setRating(double rating) {
		return this.rating = rating;
	}
}



#################VideoMethods ####################


import java.util.List;
import java.util.Scanner;
import java.util.ArrayList;
public class VideoMethods{
	List<Video> MovieList = new ArrayList<Video>();
	public void AddMovies() {
		Scanner in = new Scanner(System.in);
		System.out.print("Enter the name of the movie:");
		String mName = in.nextLine();
		System.out.print("Enter the status of the movie(True/False):");
		boolean status = in.nextBoolean();
		System.out.print("Enter the ratings for the movie(0-5):");
		double rating = in.nextDouble();
		Video v = new Video(mName, status, rating);
		MovieList.add(v);
		System.out.println("Library Initialized");
	}

	public void DisplayAll() {
		if (MovieList.isEmpty()) {
			System.out.println("No movies in the library");
		}
		for (Video m : MovieList) {
			System.out.println("Movie : " + m.getmName() + "  " + "Status : " + m.isStatus() + " " + "Rating " + m.getRating());
		}
	}

	boolean RentOut(String name)
	{
 		for(Video m :MovieList){
			if(m.getmName().equalsIgnoreCase(name)){
				if(m.isStatus()){
					m.setStatus(false);
					return true;
				}		
			}
			return false;
		}
		return false;
	}

	public void CollectIn(String name,double rat)
	{
 		boolean flag=false;
 		for(Video m :MovieList)
 		{
 			if(m.getmName().equalsIgnoreCase(name)){
	 			m.setStatus(true);
 				flag=true;
 				Math.round(m.setRating((m.getRating() + rat)/2));
			}
		}
 		if(!flag){
	 		System.out.println("Requested Movie not rented out");
		} 
	}
}




##########################video Main##################

import java.util.Scanner;
public class VideoMain {
	public static void main(String args[]) {
		VideoMethods mm = new VideoMethods();
		while (true) {
			System.out.println("----------VIDEO LIBRARY CENTER----------");
			int n;
			System.out.println("1.ADD MOVIES");
			System.out.println("2.DISPLAY MOVIES");
			System.out.println("3.RENT OUT");
			System.out.println("4.COLLECT BACK ");
			System.out.println("PLEASE ENTER YOUR OPTION");
			Scanner in = new Scanner(System.in);
			n = in.nextInt();
			switch (n) {
				case 1:
					mm.AddMovies();
					break;
				case 2:
					mm.DisplayAll();
					break;
				case 3:
					System.out.print("Enter the movie you want to rent.");
					in.nextLine();
					if (mm.RentOut(in.nextLine())) {
						System.out.println("Rent out successfull");
					} else {
						System.out.println("Sorry!! Not Available");
					}
					break;
				case 4:
					System.out.println("Enter the name and the ratings of the movie");
					in.nextLine();
					mm.CollectIn(in.nextLine(), in.nextDouble());
					break;
			}
		}
	}
}







6.. Tic Tac Toe Game 



import javax.swing.*;
import java.awt.*;
import java.awt.event.*;
import java.util.logging.Logger;
/**
* TicTacToe Application
* @author Steve Robinson
* @version 1.0
*/
class TicTacToeFrame extends JFrame
{
JButton [][] buttons= new JButton[3][3];
JTextField statusBar;
GamePanel panel;
Integer turn;
GameListener listener=new GameListener();
Integer count;
public TicTacToeFrame()
{
 setLayout(new BorderLayout());
 panel=new GamePanel();
 add(panel,BorderLayout.CENTER);
 statusBar=new JTextField("Player1's Turn");
 statusBar.setEditable(false);
 add(statusBar,BorderLayout.SOUTH);
 setTitle("Tic Tac Toe!");
 setVisible(true);
 setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
 setBounds(400,400,300,300);
}
class GamePanel extends JPanel
{
 public GamePanel()
 {
 setLayout(new GridLayout(3,3));
 turn =1;
 count=0;
 for(int i=0;i<3;i++)
 for(int j=0;j<3;j++) {
 buttons[i][j]=new JButton();
 buttons[i][j].putClientProperty("INDEX", new Integer[]{i,j});
 buttons[i][j].putClientProperty("OWNER", null);
 buttons[i][j].addActionListener(listener);
 add(buttons[i][j]);
 }
 }
}
class GameListener implements ActionListener
{
 public void actionPerformed(ActionEvent e)
 {
 count++;
 JButton b=(JButton)e.getSource();
 Integer[]index=(Integer[]) b.getClientProperty("INDEX");
 //System.out.println(turn);
//turn // //System.out.println("["+index[0]+"]"+"["+
index[1]+"]"); //
 b.putClientProperty("OWNER", turn);
 Icon ico=new ImageIcon(turn.toString()+".gif");
 b.setIcon(ico);
 b.setEnabled(false);
 boolean result=checkVictoryCondition(index);
 if(result)
 {
 JOptionPane.showMessageDialog(null, "Player "+turn.toString()+"
Wins");
 initComponents();
 }
 else
 {
 if(turn==1)
 {
 turn=2;
 statusBar.setText("Player2's Turn");
 }
 else
 {
 turn=1;
 statusBar.setText("Player1's Turn");
 }
 }
 if(count==9)
 {
 JOptionPane.showMessageDialog(null, "Match is a draw!");
 initComponents();
 }
 }
 Integer getOwner(JButton b)
 {
 return (Integer)b.getClientProperty("OWNER");
 }
 //PrintButtonMap for Diagnostics
 void printbuttonMap(Integer [][]bMap)
 {
 for(int i=0;i for(int j=0;j System.out.print(bMap[i][j]+" ");
 System.out.println("");
 }
 }
 boolean checkVictoryCondition(Integer [] index)
 {
 /*Integer[][]buttonMap=new Integer[][] {
 {
getOwner(buttons[0][0]),getOwner(buttons[0][1]),getOwner(buttons[0][2])
},
 {
getOwner(buttons[1][0]),getOwner(buttons[1][1]),getOwner(buttons[1][2])
},
 {
getOwner(buttons[2][0]),getOwner(buttons[2][1]),getOwner(buttons[2][2])
}
 };
 printbuttonMap(buttonMap); */
 Integer a=index[0];
 Integer b=index[1];
 int i;
 //check row
 for(i=0;i<3;i++) {
 if(getOwner(buttons[a][i])!=getOwner(buttons[a][b]))
 break;
 }
 if(i==3)
 return true;
 //check column
 for(i=0;i<3;i++) {
 if(getOwner(buttons[i][b])!=getOwner(buttons[a][b]))
 break;
 }
 if(i==3)
 return true;
 //check diagonal
 if((a==2&&b==2)||(a==0&&b==0)||(a==1&&b==1)||(a==0&&b==2)||(a==2&&b=
=0))
 {
 //left diagonal
 for(i=0;i if(getOwner(buttons[i][i])!=getOwner(buttons[a][b]))
 break;
 if(i==3)
 return true;
 //right diagonal
 if((getOwner(buttons[0][2])==getOwner(buttons[a][b]))&&(getOwner(bu
ttons[1][1])==getOwner(buttons[a][b]))&&(getOwner(buttons[2][0])==getOw
ner(buttons[a][b])))
 return true;
 }
 return false;
 }
}
void initComponents()
{
 for(int i=0;i<3;i++) 
 for(int j=0;j<3;j++) {
 buttons[i][j].putClientProperty("INDEX", new Integer[]{i,j});
 buttons[i][j].putClientProperty("OWNER",null);
 buttons[i][j].setIcon(null);
 buttons[i][j].setEnabled(true);
 turn=1;
 count=0;
 statusBar.setText("Player1's Turn");
 }
}
}
class TicTacToe {
public static void main(String[] args) {
 EventQueue.invokeLater(new Runnable(){
 public void run()
 {
 TicTacToeFrame frame=new TicTacToeFrame();
 }
 });
}
}








7.... Program to find the minimum and maximum node from the doubly linked list 




//Represent a node of the doubly linked list 
 
 class Node{ 
 int data; 
 Node previous; 
 Node next; 
 
 public Node(int data) { 
 this.data = data; 
 } 
 } 
 
 //Represent the head and tail of the doubly linked list 
 Node head, tail = null; 
 
 //addNode() will add a node to the list 
 public void addNode(int data) { 
 //Create a new node 
 Node newNode = new Node(data); 
 
 //If list is empty 
 if(head == null) { 
 //Both head and tail will point to newNode 
 head = tail = newNode; 
 //head's previous will point to null 
 head.previous = null; 
 //tail's next will point to null, as it is the last node of the list 
 tail.next = null; 
 } 
 else { 
 //newNode will be added after tail such that tail's next will point to newNode 
 tail.next = newNode; 
 //newNode's previous will point to tail 
 newNode.previous = tail; 
 //newNode will become new tail 
 tail = newNode; 
 //As it is last node, tail's next will point to null 
 tail.next = null; 
 } 
 } 
 
 //MinimumNode() will find out minimum value node in the list 
 public int minimumNode() { 
 //Node current will point to head 
 Node current = head; 
 int min; 
 
 //Checks if list is empty 
 if(head == null) { 
 System.out.println("List is empty"); 
 return 0; 
 } 
 else { 
 //Initially, min will store the value of head's data 
 min = head.data; 
 while(current != null) { 
 //If the value of min is greater than the current's data 
 
 //Then, replace the value of min with current node's data 
 
 if(min > current.data) 
 min = current.data; 
 current = current.next; 
 } 
 } 
 return min; 
 } 
 
 //MaximumNode() will find out maximum value node in the list 
 public int maximumNode() { 
 //Node current will point to head 
 Node current = head; 
 int max; 
 
 //Checks if list is empty 
 if(head == null) { 
 System.out.println("List is empty"); 
 return 0; 
 } 
 else { 
 //Initially, max will store the value of head's data 
 max = head.data; 
 //If value of max is lesser than current's data 
 //Then, replace value of max with current node's data 
 while(current != null) { 
 if(current.data > max) 
 max = current.data; 
 current = current.next; 
 } 
 } 
 return max; 
 } 
 
 public static void main(String[] args) { 
 
 MinMax dList = new MinMax(); 
 //Add nodes to the list 
 dList.addNode(5); 
 dList.addNode(7); 
 dList.addNode(9); 
 dList.addNode(1); 
 dList.addNode(2); 
 
 //Prints the minimum value node in the list 
 System.out.println("Minimum value node in the list: "+ dList.minimumNode()); 
 //Prints the maximum value node in the list 
 System.out.println("Maximum value node in the list: "+ dList.maximumNode()); 
 } 
}








####################################  Number Based Special Functions ################################

##----->to find freq of the number 



public class FrequencyCounter {

    public static int findFrequency(int[] arr, int number) {
        int frequency = 0;

        for (int num : arr) {
            if (num == number) {
                frequency++;
            }
        }

        return frequency;
    }

    public static void main(String[] args) {
        int[] numbers = {1, 2, 3, 4, 3, 2, 1, 3, 5, 3};
        int targetNumber = 3;

        int frequency = findFrequency(numbers, targetNumber);
        System.out.println("Frequency of " + targetNumber + " is: " + frequency);
    }
}



###################Factorial of the Number 


import java.util.Scanner;

public class Factorial {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter a number: ");
        int number = sc.nextInt();

        int factorial = 1;
        for (int i = 1; i <= number; i++) {
            factorial *= i;
        }

        System.out.println("Factorial of " + number + " is: " + factorial);
    }
}




##################Prime or not 

import java.util.Scanner;

public class PrimeNumber {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter a number: ");
        int number = sc.nextInt();

        boolean isPrime = true;

        if (number <= 1) {
            isPrime = false;
        } else {
            for (int i = 2; i <= Math.sqrt(number); i++) {
                if (number % i == 0) {
                    isPrime = false;
                    break;
                }
            }
        }

        if (isPrime) {
            System.out.println(number + " is a prime number.");
        } else {
            System.out.println(number + " is not a prime number.");
        }
    }
}



##########################Fibbonacci Series 


import java.util.Scanner;

public class FibonacciSeries {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter the number of terms: ");
        int n = sc.nextInt();

        int firstTerm = 0, secondTerm = 1;

        System.out.print("Fibonacci Series: " + firstTerm + ", " + secondTerm);

        for (int i = 2; i < n; i++) {
            int nextTerm = firstTerm + secondTerm;
            System.out.print(", " + nextTerm);

            firstTerm = secondTerm;
            secondTerm = nextTerm;
        }
        System.out.println();
    }
}




################Armstrong Number 



import java.util.Scanner;

public class ArmstrongNumber {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter a number: ");
        int number = sc.nextInt();

        int originalNumber = number;
        int sum = 0;

        while (number != 0) {
            int digit = number % 10;
            sum += Math.pow(digit, 3);
            number /= 10;
        }

        if (sum == originalNumber) {
            System.out.println(originalNumber + " is an Armstrong number.");
        } else {
            System.out.println(originalNumber + " is not an Armstrong number.");
        }
    }
}




######################## G CD


import java.util.Scanner;

public class GCD {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter two numbers: ");
        int num1 = sc.nextInt();
        int num2 = sc.nextInt();

        int gcd = findGCD(num1, num2);

        System.out.println("GCD of " + num1 + " and " + num2 + " is: " + gcd);
    }

    public static int findGCD(int a, int b) {
        if (b == 0) {
            return a;
        }
        return findGCD(b, a % b);
    }
}







#######################Palindrom Number



import java.util.Scanner;

public class PalindromeNumber {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter a number: ");
        int number = sc.nextInt();

        int originalNumber = number;
        int reversedNumber = 0;

        while (number != 0) {
            int digit = number % 10;
            reversedNumber = reversedNumber * 10 + digit;
            number /= 10;
        }

        if (originalNumber == reversedNumber) {
            System.out.println(originalNumber + " is a palindrome number.");
        } else {
            System.out.println(originalNumber + " is not a palindrome number.");
        }
    }
}



