# 90DaysDSA

# Day-1 recursion
# Sum of digit in array 
public class RecursionPrograms
{ 
  #sum of digit in array
  static int arr[] ={1,2,3,,4,5};
  public static void main(String[]args)
  {
    int value = SumOfDigit(arr.length-1);
    System.out.println(value);
    # Factorial using recursion
    int fact = Fact(5);
    System.out.println(fact);
    # Fibonacci
    int fib = Fib(7);
    System.out.println(fib);
  }
  # Fibonacci
  private static int Fib(int n)
  {
    if(n==0 || n==1)
      return n;
    return Fib(n-1) + Fib(n-2);
  }
  # factorial
  private static int Fact(int n)
  {
    if(n==1)
      return n;
    return n * Fact(n-1);
  }
  # sum of digit 
  private static int SumOfDigit(int n)
  {
    if(n==0)
      return arr[n];
    return arr[n] + SumOfDigit(n-1);
  }
}
# Day-1 linked list adding node to last 
package linkedlist;
public  class AddingNodeToLast 
{
	class Node
	{
		int val;
		Node next;
		public Node(int val)
		{
			this.val = val;
		}
	}
	static Node head = null;
	static Node tail = null;
	public void AddNodeInLast(int val)
	{
		Node newNode = new Node(val);
		// if head itself null
		if(head==null)
		{
			head = newNode;
			tail = newNode;
		}
		else
		{
			tail.next = newNode;
			newNode.next = null;
			tail = newNode;
		}
	}
	public void PrintLinkedlist(Node HeadNode)
	{
		Node current = HeadNode;
		while(current!=null)
		{
			System.out.println(current.val);
			current = current.next;
		}
	}
	public static void main(String[] args) 
	{
		AddingNodeToLast add = new AddingNodeToLast();
		add.AddNodeInLast(10);
		add.AddNodeInLast(20);
		add.AddNodeInLast(30);
		add.PrintLinkedlist(head);
		
	}	
}

