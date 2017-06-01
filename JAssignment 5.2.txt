import java.util.Scanner;

interface stack
{
	void push(int i);
	int pop();
}
class fixedstack implements stack 
{
	int[] arr;
	int pos=0;
	fixedstack(int i)
	{
		arr=new int[i];
		pos=0;
	}
	public void push(int i) throws ArrayIndexOutOfBoundsException
	{
		arr[pos]=i;
		pos++;
	}
	public int pop()
	{
		int temp=arr[pos-1];
		pos--;
		return temp;
	}
}


class variablestack implements stack 
{
	int[] arr,temparr;
	int pos=0;
	variablestack(int i)
	{
		arr=new int[i];
		pos=0;
	}
	public void push(int i) throws ArrayIndexOutOfBoundsException
	{
		if(pos==arr.length)
		{
			temparr=new int[pos*2];
			for(int j=0;j<pos;j++)
			{
				temparr[j]=arr[j];
			}
			arr=temparr;
		}
		arr[pos]=i;
		pos++;
	}
	public int pop()
	{
		int temp=arr[pos-1];
		pos--;
		return temp;
	}
}



public class StackImplemen {

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		System.out.println("enter size of fixed stack:");
		Scanner sc=new Scanner(System.in);
		int i=sc.nextInt();
		sc.nextLine();
		fixedstack fs=new fixedstack(i);
		String c="y";
		try
		{
		while(c.equals("y"))
		{
			System.out.println("enter P for push o for pop");
			String d=sc.nextLine();
			switch(d)
			{
			case "p": System.out.println("enter number to push");
						int temp=sc.nextInt();
						sc.nextLine();
						fs.push(temp);
						break;
			case "o": System.out.println("poped out data: "+fs.pop());
						
			}
			System.out.println("enter y to continue n to end fixed stack");
			c=sc.nextLine();
		}	
		}
		catch(ArrayIndexOutOfBoundsException e)
		{
			System.out.println("Stack overflow");
		}
		System.out.println("enter size of variable stack:");
		int p=sc.nextInt();
		sc.nextLine();
		variablestack vs=new variablestack(p);
		String c1="y";
		while(c1.equals("y"))
		{
			System.out.println("enter P for push o for pop");
			String d=sc.nextLine();
			switch(d)
			{
			case "p": System.out.println("enter number to push");
						int temp=sc.nextInt();
						sc.nextLine();
						vs.push(temp);
						break;
			case "o": System.out.println("poped out data: "+vs.pop());
						
			}
			System.out.println("enter y to continue n to end variable stack");
			c1=sc.nextLine();
		}	
	}
}
