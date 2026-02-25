import java.util.ArrayList;
import java.util.Scanner;

class Student {
    int id;
    String name;
    int age;

    Student(int id, String name, int age) {
        this.id = id;
        this.name = name;
        this.age = age;
    }

    void display() {
        System.out.println(id + " " + name + " " + age);
    }
}

public class Main {
    public static void main(String[] args) {

        ArrayList<Student> students = new ArrayList<>();
        Scanner sc = new Scanner(System.in);

        while (true) {

            System.out.println("1.Add 2.View 3.Update 4.Delete 5.Exit");
            int choice = sc.nextInt();

            if (choice == 1) {

                System.out.print("Enter ID: ");
                int id = sc.nextInt();
                sc.nextLine();

                System.out.print("Enter Name: ");
                String name = sc.nextLine();

                System.out.print("Enter Age: ");
                int age = sc.nextInt();

                students.add(new Student(id, name, age));
                System.out.println("Student Added!");
            }

            else if (choice == 2) {
                for (Student s : students) {
                    s.display();
                }
            }

            else if (choice == 3) {
                System.out.print("Enter ID to update: ");
                int updateId = sc.nextInt();

                for (Student s : students) {
                    if (s.id == updateId) {
                        sc.nextLine();
                        System.out.print("Enter new name: ");
                        s.name = sc.nextLine();

                        System.out.print("Enter new age: ");
                        s.age = sc.nextInt();

                        System.out.println("Student Updated!");
                    }
                }
            }

            else if (choice == 4) {
                System.out.print("Enter ID to delete: ");
                int deleteId = sc.nextInt();

                students.removeIf(s -> s.id == deleteId);
                System.out.println("Student Deleted!");
            }

            else if (choice == 5) {
                break;
            }
        }

        sc.close();
    }
}
