import java.io.*;
import java.util.*;
public class Main {
    static int tempo=0;
    public static void main(String args[]) {
    Scanner sc = new Scanner(System.in);
    int num = sc.nextInt();
    int x=num;
    int len = Integer.toString(num).length(); 
    int [] number = new int[len];
    int i=len-1;
    while (x > 0) {
 
 
    number[i]=x%10;
    i--;
 
    x = x / 10;
 
    }
    int n = len;
 
    letterCombinations(number, n);
    System.out.print("\n"+tempo);
 
 
 
    }
 
       static ArrayList<String>
	letterCombinationsUtil(int[] number, int n,
						String[] table)
	{
 
		ArrayList<String> list = new ArrayList<>();
 
		Queue<String> q = new LinkedList<>();
		q.add("");
 
		while (!q.isEmpty()) {
			String s = q.remove();
 
 
			if (s.length() == n)
				list.add(s);
			else {
				String val = table[number[s.length()]];
				for (int i = 0; i < val.length(); i++) 
				{
					q.add(s + val.charAt(i));
				}
			}
		}
		return list;
	}
 
 
	static void letterCombinations(int[] number, int n)
	{
 
		String[] table
			= { "", "abc", "def", "ghi", "jkl",
				"mno", "pqrs", "tuv", "wx", "yz" };
 
		ArrayList<String> list
			= letterCombinationsUtil(number, n, table);
 
 
		for (int i = 0; i < list.size(); i++) {
			System.out.print(list.get(i) + " ");
            tempo++;
		}
	} 
}
