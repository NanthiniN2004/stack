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




