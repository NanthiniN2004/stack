## Reverse a String using Stack

````java[]

package stack;
import java.util.*;
public class Reversestring {

	public static void main(String[] args) {
		Scanner s=new Scanner(System.in);
		String str=s.next();
		Stack<Character> st=new Stack<>();
		StringBuilder sb=new StringBuilder();
		for(char c:str .toCharArray())
		{
			st.push(c);
		}
		while(!st.isEmpty())
		{
			sb.append(st.pop());
		}
		System.out.println("Reverse a String "+ sb.toString());

	}

}

OUTPUT:
hello
Reverse a String olleh

````

## DELETE MIDDLE ELEMENT OF A STACK

````JAVA[]

package stack;
import java.util.*;
public class Deletemiddleelement {
	public static void delete(Stack<Integer> st)
	{
		Stack<Integer> res=new Stack<>();
		int count=0;
		int n=st.size();
		while(count<n/2)
		{
			res.push(st.pop());
			count++;
		}
		st.pop();
		while(!res.isEmpty()) {
			st.push(res.pop());
		}		
	}
	public static void main(String[] args) {
		Scanner s=new Scanner(System.in);
		Stack<Integer> st=new Stack<>();
		System.out.println("Enter the number of element you want add in the stack");
		int size=s.nextInt();
		for(int i=0;i<size;i++)
		{
			int val=s.nextInt();
			st.push(val);
		}
		delete(st);
		System.out.println("After delete middle of stack ");
		while (!st.isEmpty()) {
            int p = st.pop();
            System.out.print(p + " ");
        }
	}
}


OUTPUT:

Enter the number of element you want add in the stack
5
1
2
3
4
5
After delete middle of stack 
5 4 2 1

`````

## Reverse individual words

## Input: Hello World
Output: olleH dlroW
Explanation: Each word in “Hello World” is reversed individually, preserving the original order, resulting in “olleH dlroW”.


## Input: Geeks for Geeks
Output: skeeG rof skeeG

````java[]

package stack;
import java.util.*;
public class Reverseindividualword {

	public static void main(String[] args) {
		Scanner s=new Scanner(System.in);
		System.out.println("Enter the sentence ");
		String str=s.nextLine();
		Stack<Character> st=new Stack<>();
		StringBuilder sb=new StringBuilder();
		for(int i=0;i<str.length();i++)
		{
		if(str.charAt(i)!=' ')
		{
			st.push(str.charAt(i));
		}
		else {
			while(!st.isEmpty())
			{
				sb.append(st.pop());
			}
			sb.append(' ');
		}
		}
		while(!st.isEmpty())
		{
			sb.append(st.pop());
		}
	     System.out.println("After reverse "+ sb.toString());

	}

}

OUTPUT:
Enter the sentence 
hello everyone
After reverse olleh enoyreve

````

## Next Greater Element (NGE) for every element in given Array

````java[]

package stack;
import java.util.*;
public class Nextgreater {
	static ArrayList<Integer> nextgreater(int[] a)
	{
		int n=a.length;
		Stack<Integer> st=new Stack<>();
		ArrayList<Integer> res=new ArrayList<>();
		for(int i=0;i<n;i++)
		{
		     res.add(-1);
		}
		for(int i=n-1;i>=0;i--)
		{
			while(!st.isEmpty() && st.peek()<=a[i] )
			{
				st.pop();
			}
			if(!st.isEmpty())
			{
				res.set(i, st.peek());
			}
			st.push(a[i]);
		}
		return res;
		
	}

	public static void main(String[] args) {
		Scanner s=new Scanner(System.in);
		int n=s.nextInt();
		int[] a=new int[n];
		for(int i=0;i<n;i++)
		{
			a[i]=s.nextInt();
		}
		ArrayList<Integer> sol=nextgreater(a);
		System.out.println("After changing element ");
		for(int x:sol)
		{
			System.out.print(x+" ");
		}
		

	}

}

OUTPUT:

5
6
8
0
1
3
After changing element 
8-1 1 3 -1
````

## Nearest smaller numbers on left side in an array

````java[]

package stack;

import java.util.ArrayList;
import java.util.Scanner;
import java.util.Stack;

public class Nextsmallest {
	static void  nextgreater(int[] a)
	{
		int n=a.length;
		Stack<Integer> st=new Stack<>();
		for(int i=0;i<n;i++)
		{
			while(!st.isEmpty() && st.peek()>=a[i] )
			{
				st.pop();
			}
			if(st.isEmpty())
			{
				System.out.print("-1 ");
			}
			else {
				System.out.print(st.peek()+" ");
			}
			st.push(a[i]);
		}
	
	}


	public static void main(String[] args) {
		Scanner s=new Scanner(System.in);
		int n=s.nextInt();
		int[] a=new int[n];
		for(int i=0;i<n;i++)
		{
			a[i]=s.nextInt();
		}
		System.out.println("After changing element ");
		nextgreater(a);

	}

}

OUTPUT:

6
1
5
0
3
4
5
After changing element 
-1 1 -1 0 3 4

`````
## Sort a stack using a temporary stack

````java[]



package stack;
import java.util.*;
public class Sorting {
	public static Stack<Integer> sort (Stack<Integer> st){
		   Stack<Integer> t=new Stack<>();
		   
		   while(!st.isEmpty())
		   {
			   int temp=st.pop();
			   while(!t.isEmpty() && t.peek()<temp)
			   {
				   st.push(t.pop());
			   }
			   t.push(temp);
		   }
		   return t;
		   
	}

	public static void main(String[] args) {
		Scanner s=new Scanner(System.in);
		int n=s.nextInt();
		Stack<Integer> input=new Stack<>();
		for(int i=0;i<n;i++)
		{
			int val=s.nextInt();
			input.push(val);
			
		}
		Stack<Integer> result=sort(input);
		while(!result.isEmpty())
		{
			System.out.print( result.pop()+" ");
		}
		
		

	}

}

output:

6
34
2
36
76
55
51
2 34 36 51 55 76 

````
