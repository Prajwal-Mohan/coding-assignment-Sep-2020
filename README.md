# README #

### What is this repository for? ###

* Contains all the interview assignments and interview questions

### Contribution guidelines ###

* Create a branch with your name and send a PR
import java.io.IOException;
import java.util.Arrays;
import java.util.Scanner;

public class Goodiss {

static int minDiff(int arr[], int n, int k) {
	int result = Integer.MAX_VALUE;
	Arrays.sort(arr);
	for (int i=0; i<= n-k;i++)
		result = Math.min(result, arr[i + k - 1] - arr[i]);
	return result;
	
}
static int findele(int res,int arr[], int n, int k)
{
	int result = Integer.MAX_VALUE;
	for(int i=0; i<=n; i++)
	{
		result = Math.min(result, arr[i + k - 1] - arr[i]);
		if (res==result)
			return i;
				
	}
	return 0;
}
public static void main(String[] args) throws IOException  {
    
    int arr[]={7980,22349,999,2799,229900,11101,9999,2195,9800,4999};
    String items[]={ "MI Band: 999","Sandwich Toaster: 2195" ,"Cult Pass: 2799","Scale: 4999","Fitbit Plus: 7980","Microwave Oven: 9800"  ,"Alexa: 9999","Digital Camera: 11101", "IPods: 22349","Macbook Pro: 229900" };
    int n = arr.length;
    System.out.println("Enter the number of employees");
    Scanner s = new Scanner(System.in);
    int k=s.nextInt();
    int result=minDiff(arr, n, k);  
    System.out.println("Number of the employees:"+k); 
    int startindex=findele(result,arr,n,k);
    System.out.println("Here the goodies that are selected for distribution are:");
    for(int i=startindex;i<startindex+k;i++)
    System.out.println(items[i]);
      System.out.println("And the difference between the chosen goodie with highest price and the lowest price is:"+result);
} 

	
}
