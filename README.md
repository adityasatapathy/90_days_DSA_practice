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
# Day 5 inserting element into stack at given index
package Stack;

import java.util.Stack;

public class InsertAtGivenIndex {

	public static void main(String[] args) 
	{
		Stack<Integer>stack1 = new Stack<Integer>();
		stack1.push(10);
		stack1.push(20);
		stack1.push(30);
		System.out.println(stack1);
		inseringAtgivenindex(2, 40, stack1);
		System.out.println(stack1);
	}

	private static void inseringAtgivenindex(int index, int value, Stack<Integer> source) 
	{
		Stack<Integer>temp = new Stack<Integer>();
		for(int i=0; i<=source.size()-index;i++)
		{
			int item = source.peek();
			temp.push(item);
			source.pop();
		}
		source.push(value);
		while(!temp.isEmpty())
		{
			int item = temp.peek();
			source.push(item);
			temp.pop();
		}
		
	}

}
# Day 5 min value from stack
package Stack;

import java.util.Stack;

public class MinFromStack 
{
	static Stack<Integer>source = new Stack<Integer>();
	static Stack<Integer>temp = new Stack<Integer>();
	public static void main(String[] args) 
	{
		custompush(10);
		custompush(20);
		custompush(2);
		System.out.println(temp.peek()+":is the min value");
		custompop();
		System.out.println(temp.peek()+":is the min value");

	}
	private static void custompush(int n) 
	{
		
		source.push(n);
		if(temp.isEmpty())
		{
			temp.push(n);
		}
		else if(temp.peek()>n)
		{
			temp.push(n);
		}
	}
	private static void custompop() 
	{
		int item = source.peek();
		source.pop();
		if(temp.peek() == item)
		{
			temp.pop();
		}
	}

}

# Day 5 sorted stack
package Stack;

import java.util.Stack;

public class SortedStack {

	public static void main(String[] args) 
	{
		Stack<Integer>stack1 = new Stack<Integer>();
		stack1.push(40);
		stack1.push(20);
		stack1.push(30);
 		System.out.println("sorted stack is:"+sortedstack(stack1));

	}

	private static Stack<Integer> sortedstack(Stack<Integer> source)
	{
		Stack<Integer>temp = new Stack<Integer>();
		while(!source.isEmpty())
		{
			int item = source.pop();
			while(!temp.isEmpty() && temp.peek()>item)
			{
				int temp_item = temp.pop();
				source.push(temp_item);
			}
			temp.push(item);
		}
		return temp;
	}

}

# Day 7 Queue - Enqueue Dequeue using Array
package queue;

public class EnqueueDequeueUsingArray
{
	int rear;
	int front;
	int a[];
	int size;
	public EnqueueDequeueUsingArray(int size)
	{
		rear = -1;
		this.size = size;
		this.a = new int[size];
	}
	public void enqueue(int n) 
	{
		rear++;
		a[rear] = n;
	}
	public int dequeue()
	{
		int item = a[0];
		for(int i=0;i<rear;i++)
		{
			a[i]=a[i+1];
		}
		rear--;
		return item;
	}
	public void printqueue()
	{
		for(int i=0;i<=rear;i++)
		{
			System.out.println(a[i]);
		}
	}
	public static void main(String[] args)
	{
		
		EnqueueDequeueUsingArray queue = new EnqueueDequeueUsingArray(5);
		queue.enqueue(4);
		queue.enqueue(2);
		queue.dequeue();
		queue.enqueue(9);
		queue.enqueue(3);
		queue.printqueue();
	}

}
# Day 7- reversing using ArrayDeque
package queue;

import java.util.ArrayDeque;
import java.util.Queue;
import java.util.Stack;

public class ReverseInbuiltIMethodUsing_ArrrayDequeue 
{

	public static void main(String[] args) 
	{
		Queue<Integer> queue = new ArrayDeque<Integer>();
		queue.add(10);
		queue.add(20);
		queue.add(30);
		queue.add(40);
		queue.add(50);
		queue.remove();
		queue.remove(40);
		for (int ele :queue)
		{
			System.out.println(ele);
		}
		Stack<Integer>stack1 = new Stack<Integer>();
		while(!queue.isEmpty())
		{
			int item = queue.remove();
			stack1.push(item);
		}
		while(!stack1.isEmpty())
		{
			int item = stack1.pop();
			queue.add(item);
		}
		System.out.println("Queue after reverse");
		for (int ele :queue)
		{
			System.out.println(ele);
		}
	}

}
# Day 7- PriorityQueue Enqueue
package queue;
import java.util.PriorityQueue;

public class Enqueue_priority_queue 
{
		int rear;
		int front;
		int[] a;
		int size;
		public Enqueue_priority_queue(int size)
		{
			rear = -1;
			this.size=size;
			//front = 0;
			this.a = new int[size];
		}
		
		public void enQueue(int x)
		{
			if(rear == -1)
			{
				rear++;
				a[rear]=x;
			}
			else
			{
			for(int i =rear;i>=0;i--)
			{
				if(a[i]>x)
				{
					a[i+1] = a[i];
					if(i == 0)
						a[i]= x;
				}
				else {
					a[i+1]=x;
					break;
				}
			}
			
				rear++;
			}
				
			
		}
		
		public int deQueue()
		{
			
			int ele =a[0];
			for(int i =0;i<rear;i++)
			{
				a[i] = a[i+1];
				
			}
			rear--;
			return ele;
		}
		
		public void printQueue()
		{
			for(int i =0;i<=rear;i++)
			{
				System.out.println(a[i]);
			}
		}
	
		public static void main(String[] args)
		{
			Enqueue_priority_queue qd = new Enqueue_priority_queue(10);
			qd.enQueue(4);
			qd.enQueue(2);
			qd.deQueue();
			qd.enQueue(9);
			qd.enQueue(3);
			qd.enQueue(12);
			qd.deQueue();
			qd.deQueue();
			qd.printQueue();

		}
	
	}

# Day 8 bubble sort and time complexity
package sorting;

import java.util.Arrays;

public class BubbleSort {

	public static void main(String[] args) 
	{
		int arr[] = {6,4,7,8,9,10};
		System.out.println("Array before sort:"+ Arrays.toString(arr));
		int size = arr.length;
		for(int i=0;i<size-1;i++)
		{
			for(int j=0;j<size-1;j++)
			{
				if(arr[j]>arr[j+1])
				{
					int temp = arr[j];
					arr[j]=arr[j+1];
					arr[j+1]=temp;
				}
			}
		}
		System.out.println("Array after sort:"+ Arrays.toString(arr));

	}

}









