using System;
using System.Collections.Generic;
using System.Diagnostics;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace BucketSort
{
    internal class Program
    {
        public static List<double> BucketSort(double[] x, int n)
        {

            //Крок 1
            List<double> result = new List<double>();

            //Крок 2
            List<double>[] buckets = new List<double>[n];

            for (int i = 0; i < buckets.Length; i++)
                buckets[i] = new List<double>();

            //Крок 3
            //for (int i = 0; i < x.Length; i++)
            //{
            //    buckets[(int)(n * x[i])].Add(x[i]);
            //}

            //Крок 3 parallel
            Parallel.For(0, x.Length, i => buckets[(int)(n * x[i])].Add(x[i]));


            //Крок 4
            for (int i = 0; i < buckets.Count(); i++)
                result.AddRange(buckets[i].ToArray());


            return result;
        }

        static void Main(string[] args)
        {
            while(true)
            {
                Stopwatch sw = new Stopwatch();

                Console.Write("Введiть розмiр масиву: ");
                Random rnd = new Random();
                int len = Convert.ToInt32(Console.ReadLine());

                Console.Write("\nВведiть кількість кошиків: ");
                int n = Convert.ToInt32(Console.ReadLine());
                double[] arr = new double[len];

                Console.Write("Початковий масив: ");
                for (int i = 0; i < len; i++)
                {
                    arr[i] = rnd.NextDouble();
                    Console.Write(arr[i] + " ");
                }

                sw.Start();
                var res = BucketSort(arr, n);
                sw.Stop();

                Console.Write("\nВiдсортований мaсив: ");
                foreach (double el in res)
                    Console.Write(el + " ");
                Console.WriteLine();

                Console.WriteLine($"Витрачений час: {sw.ElapsedMilliseconds} мс\n");
            }
        }
    }
}
