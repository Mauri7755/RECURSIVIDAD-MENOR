# RECURSIVIDAD-MENOR
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace ConsoleApplication67
{
    class Program
    {

        static int NumeroMenor(int  [] x, int n, int menor)
         {
            
            if (n == 0) 
            {
                if (menor > x [n]) 
                {
                    return x [0];
                }
                else 
                {
                    return menor;
                }
            }
                else
            {
                if (menor > x [n]) 
                {
                    return NumeroMenor (x, n - 1, x [n]);
                }
                     else
                {
                    return NumeroMenor (x, n - 1, menor);
                    
                }
            }
        }

           
        static void Main(string[] args)
       {
          
           Random rmd = new Random();
             int m=0,i;
           Console.WriteLine("ingrese el tamaño del vector que quiera el usuario");
           m = int.Parse(Console.ReadLine());

           int[] vec = new int[m];
            for ( i=0;i<m;i++)
            {
                vec[i] = rmd.Next(0, 50);
                Console.WriteLine(vec[i]);
            }
            Console.WriteLine("el numero menor es:" + NumeroMenor(vec, m-1,vec[0]));
            Console.ReadKey();
        }
    }
}
