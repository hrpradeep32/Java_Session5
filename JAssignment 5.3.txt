class employee
{
	int emplid;
	String empName;
	int totalLeaves=20;
	double totalSalary=21000;
	void calculateBalanceLeaves()
	{
		System.out.println("leaves available= "+totalLeaves);
	}
	boolean availLeave(int noOfLeaves,char typeOfLeave)
	{
		if(totalLeaves-noOfLeaves>0)
		{
			totalLeaves=totalLeaves-noOfLeaves;
			return true;
		}
		else
		{
			System.out.println("you dont have so many leaves");
			return false;
		}
	}
	void calculateSalary()
	{
		System.out.println("total Salary: "+totalSalary);
	}
}
class permanentEmployee extends employee
{
	char paidLeave, sickLeave, casualLeave;
	double basic=18000,hra=4000,pf=1000;
	void printLeaveDetails()
	{
		System.out.println("you have "+totalLeaves+" leaves");
		System.out.println("you can avail those using any of below:");
		System.out.println("1. Paid Leave");
		System.out.println("2. Sick Leave");
		System.out.println("3. Casual Leave");
	}
	void calculateBalanceLeaves()
	{
		System.out.println("leaves available= "+totalLeaves);
	}
	boolean availLeave(int noOfLeaves,char typeOfLeave)
	{
		if(totalLeaves-noOfLeaves>0)
		{
			totalLeaves=totalLeaves-noOfLeaves;
			System.out.println(noOfLeaves+" leaves availed");
			return true;
		}
		else
		{
			System.out.println("you dont have so many leaves");
			return false;
		}
	}
	void calculateSalary()
	{
		System.out.println("total Salary: "+(basic+hra-pf));
	}
}

class temporaryEmployee extends employee
{
	void calculateBalanceLeaves()
	{
		System.out.println("leaves available= "+totalLeaves);
	}
	boolean availLeave(int noOfLeaves,char typeOfLeave)
	{
		if(totalLeaves-noOfLeaves>0)
		{
			totalLeaves=totalLeaves-noOfLeaves;
			System.out.println(noOfLeaves+" leave availed");
			return true;
		}
		else
		{
			System.out.println("you dont have so many leaves");
			return false;
		}
	}
	void calculateSalary()
	{
		System.out.println("total Salary: "+totalSalary);
	}
}


public class EmployeeLeaves {

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		permanentEmployee pe=new permanentEmployee();
		pe.printLeaveDetails();
		pe.calculateBalanceLeaves();
		pe.availLeave(2,'c');
		pe.calculateBalanceLeaves();
		pe.calculateSalary();
		temporaryEmployee te=new temporaryEmployee();
		te.calculateBalanceLeaves();
		te.availLeave(4,'c');
		te.calculateBalanceLeaves();
		te.calculateSalary();
	}

}
