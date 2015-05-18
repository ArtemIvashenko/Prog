import java.io.FileOutputStream;
import java.io.IOException;
import java.lang.reflect.Array;
import java.util.Arrays;
import java.util.Scanner;

import javax.swing.JOptionPane;

public class GimnasyumClass {

	private Student[] studentclass = new Student[10];

	public void addStudent(Human a) {
		int i = -1;
		for (int j = 0; j < studentclass.length; j++) {
			if (studentclass[j] == null) {
				i = j;
				break;
			}
		}

		try {
			if (i == -1) {
				throw new ItsAman();

			}
			studentclass[i] = new Student(a.getName(), a.getLastname(),
					a.getAge(), a.getSex(), 1);
		} catch (ItsAman e) {
			System.out.println(e);
		} catch (ArrayIndexOutOfBoundsException E) {
			System.out.println("Game back in next year");
		} catch (Exception e) {
			System.out.println("studen!=Human");
		}
	}

	public void printGroupInfo() {
		for (Student temp : studentclass) {
			try {
				System.out.println(temp.printinfo());
			} catch (NullPointerException E) {

			}

		}
	}

	public String serch(String Surname) {
		for (Student temp : studentclass) {
			try {
				if (temp.getLastname().equals(Surname)) {
					System.out
							.println("Your requested for: " + Surname
									+ ". Found next student record "
									+ temp.printinfo());
					return temp.printinfo();
				}
			} catch (Exception e) {
				System.out.println("Student not in this class");
			}
		}
		System.out.println("Your requested for: " + Surname
				+ ". Such record was not found.");
		return null;
	}

	public void sort() {
		try {
			Arrays.sort(studentclass);
		} catch (Exception E) {

		}
	}

	public void Interactive() {
		Scanner sc = new Scanner(System.in);
		try {
			int count = 0;
			for (int i = 0; i < studentclass.length; i++) {
				if (studentclass[i] == null)
					count++;
				{

				}
			}
			int kol = Integer.valueOf(JOptionPane
					.showInputDialog("vvedite kol-vo studentov"));
			if (kol > count) {
				kol = count;
				System.out.println("kol-vo stud big Group" +" "+ kol);
			}
			for (int i = 0; i < kol; i++) {
				try {
					Human student = new Human(String.valueOf(JOptionPane
							.showInputDialog("Input name")),
							String.valueOf(JOptionPane
									.showInputDialog("Input lastname")),
							Integer.valueOf(JOptionPane
									.showInputDialog("Input age")),
							Character.valueOf(JOptionPane.showInputDialog(
									"Input state").charAt(0)));

					this.addStudent(student);
				} catch (Exception E) {
					System.out.println("eror format");
				}
			}
		} catch (NumberFormatException E) {
		}
	}

	public void greatedFiles() {

		for (Student temp : studentclass) {
			
		;
			try{
				String Student1 = temp.printinfo();
				
				System.out.println(Student1);
				
				
				FileOutputStream f = null;
				byte[] b = Student1.getBytes();
				try {
					f = new FileOutputStream("Students.txt");
					f.write(b);
				} catch (IOException e) {
					System.out.println("I/O Error");
				} finally {
					try {
						f.close();
					} catch (IOException e) {
						System.out.println("Error close file");
					}
				}
			} catch (NullPointerException E) {
				System.out.println("Eror kreated");
			}

		}
	}
}
