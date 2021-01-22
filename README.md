# ElectricityBill-

import java.util.Scanner;
class ElectricityBill
{
	int units;
	String name,city;
	double bill,total=0;
	public void input()
	{
		
		
		Scanner sc=new Scanner(System.in);
		System.out.print("\n\n  Enter Your Name :                                          \t");
		if(sc.hasNext("[A-Za-z]*"))
			{
				name=sc.nextLine();
			}
			else
			{
				System.out.println("Invalid Input ");
			}
		System.out.print("  Enter Your City :                                            \t");
		city=sc.nextLine();
		System.out.print("  Enter the  Unit :                                            \t");
		while(!sc.hasNextInt())
		{
			System.out.println("Invalid Input");
			sc.next();
		}
		System.out.print("                                                  			 \t");
		units=sc.nextInt();
	}
	public void calculate()
	{
		
		if(units>=1 && units<=50)
		{
			bill=1.50*units;
		}
		else if(units>=51 && units<=100)
		{
			bill=3.00*units;
		}
		else if(units>=101 && units<=200)
		{
			bill=4.00*units;
		}
		else if(units>=200 && units<=300)
		{
			bill=5.00*units;
		}
		else 
		{
			bill=6.00*units;
		}

		if(bill>500)
		{
			total=bill+(bill*0.15);
		}
		else
		{
			total=bill;
		}
	}
	public void display()
	{
		System.out.println(" __________________________________________________________________________________");
		System.out.println("|                                                                                  |");
		System.out.println("|                                                                                  |");
		System.out.println("|                   ***********ELECTRICITY BILL***********                         |");
		System.out.println("|                                                                                  |");
		System.out.println("|                                                                                  |");
		System.out.print("|__________________________________________________________________________________|");
		System.out.println("\n\n Name :                                                     \t"+name);
		System.out.println(" City :                                                        \t"+city);
		System.out.println(" Unit :                                                        \t"+units);
		System.out.println("___________________________________________________________________________________");
		System.out.println("\n  Bill Charges Per Unit                                              ");
		System.out.println("  1 Unit to 50 Units                                              1.50");
		System.out.println("  51 Unit to 100 Units                                            3.00");
		System.out.println("  101 Unit to 200 Units                                           4.00");
		System.out.println("  201 Unit to 300 Units                                           5.00");
		System.out.println("  Above 300 Units                                                 6.00");
		System.out.println("___________________________________________________________________________________");
		System.out.println("\n  Bill Amount                                                     "+bill);
		System.out.println("  The Total amount                                                "+total);
		System.out.println("___________________________________________________________________________________");
	}
	public static void main(String args[])
	{
		char ch;
		ElectricityBill b1=new ElectricityBill();
		Scanner sc=new Scanner(System.in);
				do
				{
					b1.input();
					b1.calculate();
					b1.display();
			System.out.print("Do you want to Generate another bill (y/n) ");
			ch=sc.next().charAt(0);
		}while(ch=='y');
	}
}
