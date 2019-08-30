# Hacker


import java.util.Scanner;
 
class Hacker {
    public static void main(String args[] ) throws Exception 
    {
        try(Scanner sc = new Scanner(System.in))
        {
            int N = sc.nextInt();
            int K = sc.nextInt();
            int[] input = new int[N];
 
            for(int i = 0; i < N; ++i) 
            {
                switch (s.next().charAt(0))
                {
                    case 'G': input[i] = 0; 
                             break;
                    case 'R': input[i] = 1; 
                             break;
                    case 'Y': input[i] = 2;
                              break;
                }
            }
 
            int[] temp = new int[N];
            int offset = 0, result = 0;
 
            for(int i = 0; i < N; ++i)
            {
                input[i] += offset;
 
                switch (input[i] % 3) {
                    case 1: temp[i] = 2;
                            result += 2;
                          offset += 2;
                           break;
                    case 2: temp[i] = 1;
                           result += 1; offset += 1;
                           break;
                    default: temp[i] = 0; 
                       break;
                }
 
                if ((i+1)-K >= 0) offset -= temp[i+1-K];
            }
            System.out.println(result);
        }
    }
}

