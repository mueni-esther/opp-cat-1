# oop-cat-1[student . rec.java](https://github.com/user-attachments/files/25451090/student.rec.java)
import java.util.Scanner;

// i) Create a class named StudentRecord
class StudentRecord {
    // Three fields to store student details
    String studentID;
    String name;[vehicle. inh.java](https://github.com/user-attachments/files/25451091/vehicle.inh.java)

    String course;

    // Constructor to initialize these fields
    public StudentRecord(String studentID, String name, String course) {
        this.studentID = studentID;
        this.name = name;
        this.course = course;
    }

    // Method to print the student details
    public void displayInfo() {
        System.out.println("\n--- Student Details ---");
        System.out.println("Student ID: " + studentID);
        System.out.println("Name: " + name);
        System.out.println("Course: " + course);
    }
}

// ii) Create another class named StudentApp
public class StudentApp {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Prompt the user to input their details
        System.out.print("Enter Student ID: ");
        String id = scanner.nextLine();

        System.out.print("Enter Name: ");
        String name = scanner.nextLine();

        System.out.print("Enter Course: ");
        String course = scanner.nextLine();

        // Instantiate a StudentRecord object using user-provided data
        StudentRecord student = new StudentRecord(id, name, course);

        // Call the displayInfo method
        student.displayInfo();
        
        scanner.close();
    }
}
import java.util.Scanner;

// i) Create a base class named Vehicle
class Vehicle {
    // Three fields to store vehicle details
    String brand;
    String model;
    int year;

    // Constructor to initialize these fields
    public Vehicle(String brand, String model, int year) {
        this.brand = brand;
        this.model = model;
        this.year = year;
    }

    // Method to print vehicle details
    public void displayDetails() {
        System.out.println("Brand: " + brand);
        System.out.println("Model: " + model);
        System.out.println("Year: " + year);
    }
}

// ii) Create a subclass named Car that inherits from Vehicle
class Car extends Vehicle {
    // Additional field for fuel type
    String fuelType;

    // Constructor that initializes all fields including those from Vehicle
    public Car(String brand, String model, int year, String fuelType) {
        // Use 'super' to call the constructor of the parent class (Vehicle)
        super(brand, model, year);
        this.fuelType = fuelType;
    }

    // Override displayDetails to also print fuelType
    @Override
    public void displayDetails() {
        super.displayDetails(); // Call the parent method to print brand, model, year
        System.out.println("Fuel Type: " + fuelType);
    }
}

// iii) Create another class named Showroom
public class Showroom {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Prompt the user to input vehicle details
        System.out.print("Enter Car Brand: ");
        String brand = scanner.nextLine();

        System.out.print("Enter Car Model: ");
        String model = scanner.nextLine();

        System.out.print("Enter Manufacturing Year: ");
        int year = scanner.nextInt();
        
        // Consume the leftover newline character after reading the integer
        scanner.nextLine(); 

        System.out.print("Enter Fuel Type: ");
        String fuelType = scanner.nextLine();

        // Instantiate a Car object using user-provided data
        Car myCar = new Car(brand, model, year, fuelType);

        System.out.println("\n--- Car Details ---");
        // Call the displayDetails method
        myCar.displayDetails();
        
        scanner.close();
    }
}
