# stableunstable
import java.util.ArrayList;

import java.util.Collections;

import java.util.Set;

import java.util.TreeSet;

public class StableUnstable {

public 	static boolean  add(int num)
	{
	int a[]=new int[(num+"").length()]; 
	int te=0;
	while (num>0)
	{
		int rem=num%10;
		num=num/10; 
		a[te]=rem;
		//System.out.println(a[te]);
		te++;
	}
	int b[][]=new int [10][1];  //
	
	for(int j=0;j<=9;j++)
	{	int count=0;
		for (int i=0;i<a.length;i++)
		{
			if(j==a[i]) //0 -->j
			{
				count++;
			}
		}
		System.out.println("the j value is "+ j + " "+ "count" + count);
			b[j][0]=count;
		
	}
	TreeSet <Integer>s=new TreeSet<Integer>();
		for (int i=0;i<=9;i++) {
		if(b[i][0]>0)
		{
			s.add(b[i][0]);
		}
		}
		System.out.println(s);
		if(s.size()==1)
			return true;
		else 
			return false;
	}
	
public static void main(String[] args) {
	 int n1=7722;
	 int n2=100;
	 int n3=100011;
	 int n4=1;
	 boolean b=add(n1);
	 ArrayList sal=new ArrayList();
	 ArrayList ual=new ArrayList();
	 boolean x = b==true?sal.add(n1):ual.add(n1);
	 b=add(n2);
	 x = (b==true)?sal.add(n2):ual.add(n2);
	 b=add(n3);
	 x = b==true?sal.add(n3):ual.add(n3);
	 b=add(n4);
	 x = b==true?sal.add(n4):ual.add(n4);
	 
		 System.out.println(sal);
		 System.out.println(ual);
		 //stable max-stable min
		 System.out.println((int)Collections.max(sal)-(int) Collections.min(sal));
		 //stable max -unstable min
		 System.out.println((int)Collections.max(sal)-(int) Collections.min(ual));
		 //unstable min - stable min
		 System.out.println((int) Collections.min(ual)-(int)Collections.min(sal));
		 
		 System.out.println((int)Collections.max(sal) - (int)Collections.min(sal)); //karthi
}
}
