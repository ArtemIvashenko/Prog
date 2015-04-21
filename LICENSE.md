package triangle;

public class Triangle {
	private double a;
	private double b;
	private double c;

	public double getA() {
		return a;
	}

	public void setA(double a) {
		this.a = a;
	}

	public double getB() {
		return b;
	}

	public void setB(double b) {
		this.b = b;
	}

	public double getC() {
		return c;
	}

	public void setC(double c) {
		this.c = c;
	}

	public Triangle(double a, double b, double c) {
		super();
		this.a = a;
		this.b = b;
		this.c = c;
	}

	public double perimetr() {
		double per = (a + b + c) / 2;
		return per;
	}

	public double getsquare() {

		double S = Math.sqrt(perimetr() * (perimetr() - a) * (perimetr() - b)
				* (perimetr() - c));
		if (S == 0) {
			System.out.println("Eror triangle");

		}
		return S;
	}

	public void print() {
		System.out.println("a= " + a + " b= " + b + " c= " + c);
		System.out.println(getsquare());

	}
}
