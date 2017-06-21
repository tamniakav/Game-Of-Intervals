using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace Game_Of_Intervals
{
    class Program
    {
        static void Main(string[] args)
        {
            int n = int.Parse(Console.ReadLine());

            double sum = 0;
            double invalid = 0;
            double zero = 0;
            double ten = 0;
            double twenty = 0;
            double thirty = 0;
            double fourty = 0;
            
            for (int i = 1; i <= n; i++)
            {
                int num = int.Parse(Console.ReadLine());

                if (num < 0 || num > 50)
                {
                    sum /= 2;
                    invalid++;
                }
                else if (num < 10)
                {
                    sum += num * 0.20;
                    zero++;
                }
                else if (num < 20)
                {
                    sum += num * 0.30;
                    ten++;
                }
                else if (num < 30)
                {
                    sum += num * 0.40;
                    twenty++;
                }
                else if (num < 40)
                {
                    sum += 50;
                    thirty++;
                }
                else if (num <= 50)
                {
                    sum += 100;
                    fourty++;
                }
            }

            Console.WriteLine($"{sum:f2}");
            Console.WriteLine("From 0 to 9: {0:f2}%", (zero / n) * 100);
            Console.WriteLine("From 10 to 19: {0:f2}%", (ten / n) * 100);
            Console.WriteLine("From 20 to 29: {0:f2}%", (twenty / n) * 100);
            Console.WriteLine("From 30 to 39: {0:f2}%", (thirty / n) * 100);
            Console.WriteLine("From 40 to 50: {0:f2}%", (fourty / n) * 100);
            Console.WriteLine("Invalid numbers: {0:f2}%", (invalid / n) * 100);
        }
    }
}
