# Profiling with dotTrace

## Short Description

This is a task for investigation of app profiling with dotTrace.

## Estimation (h)

8

## Topics

* Investigating profiling modes
* Investigating performance Viewer

## Requirements

You should be able to determine best solution by timeline profiling investigation.

Create a DebuggingAndPerformance C# console app and update the it with the code as below. Run startup configuration
perfomance profiling with different modes. Figure out which one sorting function has minimum Swap function calls.
Refactore code with inline implementation of Swap function and check is it works faster? Determine the best sort
function for different NumsCount: 5, 100, 600, 2000. Implement your own function which will use the best sort function
according to array size. Check implemented function working time.

```cs
using System;

namespace DebuggingAndPerformance
{
    class Program
    {
        static void Main(string[] args)
        {
            const int NumsCount = 100;
            int[] nums1 = new int[NumsCount];
            // rand initialisation
            Input(nums1);

            int[] nums2 = (int[])nums1.Clone();
            int[] nums3 = (int[])nums1.Clone();
            int[] nums4 = (int[])nums1.Clone();

            //sort
            Sort1_ShakerSort(nums1);
            Sort2_QuickSort(nums2);
            Sort3_SelectionSort(nums3);
            Sort4_DefaultSort(nums4);


            if (!CheckSortResults(nums1))
            {
                Console.WriteLine("Array 1 is unsorted!");
            }
            if (!CheckSortResults(nums2))
            {
                Console.WriteLine("Array 2 is unsorted!");
            }
            if (!CheckSortResults(nums3))
            {
                Console.WriteLine("Array 3 is unsorted!");
            }
            if (!CheckSortResults(nums4))
            {
                Console.WriteLine("Array 4 is unsorted!");
            }

            // output
            //Console.WriteLine("Array 1:");
            //Otput(nums1);
            //Console.WriteLine("Array 2:");
            //Otput(nums2);
            //Console.WriteLine("Array 3:");
            //Otput(nums3);
            //Console.WriteLine("Array 4:");
            //Otput(nums4);
        }

        private static bool CheckSortResults(int[] nums)
        {
            for (int i = 1; i < nums.Length; i++)
            {
                if (nums[i - 1] > nums[i])
                {
                    return false;
                }
            }

            return true;
        }

        private static void Otput(int[] nums)
        {
            for (int i = 0; i < nums.Length; i++)
            {
                Console.WriteLine(nums[i]);
            }
        }

        private static void Input(int[] nums)
        {
            Random random = new Random();
            for (int i = 0; i < nums.Length; i++)
            {
                nums[i] = random.Next(0, 100);
            }
        }

        private static void Sort1_ShakerSort(int[] nums)
        {
            int tmp;
            for (var i = 0; i < nums.Length / 2; i++)
            {
                var swapFlag = false;
                for (var j = i; j < nums.Length - i - 1; j++)
                {
                    if (nums[j] > nums[j + 1])
                    {
                        //tmp = nums[j];
                        //nums[j] = nums[j + 1];
                        //nums[j + 1] = tmp;
                        Swap(ref nums[j], ref nums[j + 1]);
                        swapFlag = true;
                    }
                }

                for (var j = nums.Length - 2 - i; j > i; j--)
                {
                    if (nums[j - 1] > nums[j])
                    {
                        //tmp = nums[j - 1];
                        //nums[j - 1] = nums[j];
                        //nums[j] = tmp;
                        Swap(ref nums[j - 1], ref nums[j]);
                        swapFlag = true;
                    }
                }

                if (!swapFlag)
                {
                    break;
                }
            }
        }

        private static void Sort2_QuickSort(int[] nums)
        {
            QuickSortRecursion(nums, 0, nums.Length - 1);

            //find base element index
            static int Partition(int[] array, int minIndex, int maxIndex)
            {
                int tmp;
                var pivot = minIndex - 1;
                for (var i = minIndex; i < maxIndex; i++)
                {
                    if (array[i] < array[maxIndex])
                    {
                        pivot++;
                        Swap(ref array[pivot], ref array[i]);
                        //tmp = array[pivot];
                        //array[pivot] = array[i];
                        //array[i] = tmp;
                    }
                }

                pivot++;
                Swap(ref array[pivot], ref array[maxIndex]);
                //tmp = array[pivot];
                //array[pivot] = array[maxIndex];
                //array[maxIndex] = tmp;

                return pivot;
            }

            static void QuickSortRecursion(int[] array, int minIndex, int maxIndex)
            {
                if (minIndex >= maxIndex)
                {
                    return;
                }

                var pivotIndex = Partition(array, minIndex, maxIndex);
                QuickSortRecursion(array, minIndex, pivotIndex - 1);
                QuickSortRecursion(array, pivotIndex + 1, maxIndex);
            }
        }

        private static void Sort3_SelectionSort(int[] nums)
        {
            int tmp;
            for (var i = nums.Length - 1; i > 0; i--)
            {
                var maxIndex = i;
                int j;
                for (j = i - 1; j >= 0; --j)
                {
                    if (nums[j] > nums[maxIndex])
                    {
                        maxIndex = j;
                    }
                }

                if (i != maxIndex)
                {
                    Swap(ref nums[i], ref nums[maxIndex]);
                    //tmp = nums[i];
                    //nums[i] = nums[maxIndex];
                    //nums[maxIndex] = tmp;
                }
            }
        }

        private static void Sort4_DefaultSort(int[] nums)
        {
            Array.Sort(nums);
        }

        static void Swap(ref int x, ref int y)
        {
            var t = x;
            x = y;
            y = t;
        }
    }
}
```cs
