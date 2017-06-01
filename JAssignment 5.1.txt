abstract class figure
{
	double dim;
	figure(double val)
	{
		dim=val;
	}
	abstract double findArea();
	abstract double findPerimeter();
}
class circle extends figure
{
	public circle(double val)
	{
		super(val);
	}
	double findArea() 
	{
		return 3.14*dim*dim;
	}
	double findPerimeter() 
	{
		return 2*3.14*dim;
	}
}

class rectangle extends figure
{
	public rectangle(double val)
	{
		super(val);
	}
	double findArea() 
	{
		return dim*dim;
	}
	double findPerimeter() 
	{
		return 2*(dim+dim);
	}
}


class triangle extends figure
{
	public triangle(double val)
	{
		super(val);
	}
	double findArea() 
	{
		return (3/4)*dim;
	}
	double findPerimeter() 
	{
		return (dim+dim+dim)/2;
	}
}
public class AreaandPer {

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		circle c1=new circle(10);
		System.out.println("area of the circle is :: "+c1.findArea());
		System.out.println("perimieter of the circle :: "+c1.findPerimeter());
		
		rectangle r1=new rectangle(10);
		System.out.println("area of the rectangle is :: "+r1.findArea());
		System.out.println("perimieter of the rectangle :: "+r1.findPerimeter());
		
		triangle t1=new triangle(10);
		System.out.println("area of the triangle is :: "+t1.findArea());
		System.out.println("perimieter of the triangle :: "+t1.findPerimeter());
	}

}
