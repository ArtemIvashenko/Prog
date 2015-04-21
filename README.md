package triangle;

public class Main {

	public static void main(String[] args) {
		Triangle triangle = new Triangle(3, 3, 6);

		triangle.getsquare();
		triangle.print();
		
		Triangle triangle2 = new Triangle(4, 4, 4);
		triangle2.print();
		
		Triangle triangle3 = new Triangle(8, 8, 4);
		triangle3.print();
	}

}
