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
	# DAY 2
	// node at the beginning
	public void AddNodeAtBegining(int val)
	{
		Node newNode = new Node(val);
		// checking if the head is null only 
		if(head == null)
		{
			head = newNode;
			tail = newNode;
		}
		newNode.next = head;
		head = newNode;
	}
	// Adding node at specific index
	public void AddNodeAtIndex(int val, int index)
	{
		int count = 1;
		Node current = head;
		while(current!=null && count != index-1)
		{
			current = current.next;
			count++;
		}
		Node newNode = new Node(val);
			Node temp = current.next;
			current.next = newNode;
			newNode = temp;	
	}
	// Delete the node at the end
	public void DeleteNodeAtEnd()
	{
		Node current = head;
		while(current.next.next!=null)
		{
			//continue moving to next node
			current = current.next;
		}
		current.next = null;
		tail = current;
	}
	// Delete first node
	public void DeleteFirstNode()
	{
		head = head.next;
	}
	// Delete Node at specific index
	public void RemoveAtspecifcIndex(int index)
	{	
		if(index==1)
		{
			DeleteFirstNode();
		}
		else
		{

			int count =1;
			Node current = head;
			while(current!=null && count!=index-1)
			{
				current = current.next;
				count++;
			}
			current.next = current.next.next;
		}
	}
	public void PrintLinkedList(Node HeadNode)
	{
		Node current = HeadNode;
		while(current!=null)
		{
			System.out.println(current.val);
			current = current.next;
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
# Day 3 reverse linkedlist
package linkedlist;
public class ReverseLinkedList 
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
	public void AddNodeTolast(int val)
	{
		Node newNode = new Node(val);
		if(head == null)
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
	public void PrintLinkedList(Node HeadNode)
	{
		Node current = HeadNode;
		while(current!=null)
		{
			System.out.println(current.val);
			current = current.next;
		}
	}
	// Reverse linked list
	public void ReverseLinkedlist()
	{
		Node current = head;
		Node prev = null;
		Node next = null;
		while(current!=null)
		{
			next = current.next;
			current.next = prev;
			prev = current;
			current = next;
		}
		PrintLinkedList(prev);
	}
	public static void main(String[] args) 
	{
		ReverseLinkedList node = new ReverseLinkedList();
		node.AddNodeTolast(10);
		node.AddNodeTolast(20);
		node.AddNodeTolast(30);
		node.PrintLinkedList(head);
		node.ReverseLinkedlist();
		
	}

}
# Days 3 and 4 stack and reverse stack
package Stack;

import java.util.Stack;

public class Reverse_stack {

	public static void main(String[] args) 
	{
		Stack<Integer>stack1 = new Stack<Integer>();
		System.out.println(stack1.isEmpty());
		stack1.push(10);
		stack1.push(20);
		stack1.push(30);
		System.out.println(stack1);
		Stack<Integer>stack2 = new Stack<Integer>();
		Stack<Integer>stack3 = new Stack<Integer>();
		MoveTostack(stack1, stack2);
		MoveTostack(stack2, stack3);
		MoveTostack(stack3, stack1);
		System.out.println(stack1);
	}
	
	private static void MoveTostack(Stack<Integer> source, Stack<Integer> destination) 
	{
		while(!source.isEmpty())
		{
			int value = source.peek();
			destination.push(value);
			source.pop();
		}
	}

}



