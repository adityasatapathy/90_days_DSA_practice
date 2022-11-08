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
 
