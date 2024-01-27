# Working with breakpoints and windows

## Short Description

This is a task for investigation of debugging process, breakpoints, watch windows.

## Estimation (h)

8

## Topics

* Breakpoints
* Release and Debug modes
* Watch windows

## Requirements

You should be able to debug the app, check variables in watch windows.

Create a DebuggingAndPerformance C# console app and update the it with the code as below. Switch between Release and
Debug modes and try to debug the app, check the varibles, feel the difference. Switch to Debug mode. Find a bug by using
breakpoints, step into/over/out buttons and watch, quick watch, locals, autos windows (check the difference). Check
hints for variables. Check the callstack window when you will debug SelectionSort function, try to switch to main
function and back again, check the variable windows on each state.

```cs
using System;

namespace DebuggingAndPerformance
{
    class Program
    {
        static void Main(string[] args)
        {
            const int NumsCount = 10;
            int[] nums = new int[NumsCount];
            // rand initialisation
            Input(nums);

            //sort
            SelectionSort(nums);

            if (!CheckSortResults(nums))
            {
                Console.WriteLine("Array is unsorted!");
            }

            // output
            Console.WriteLine("Array:");
            Otput(nums);
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

        private static void SelectionSort(int[] nums)
        {
            for (var i = nums.Length - 1; i > 0; i--)
            {
                var maxIndex = i;
                int j;
                for (j = i - 1; j > 0; --j)
                {
                    if (nums[j] > nums[maxIndex])
                    {
                        maxIndex = j;
                    }
                }

                if (i != maxIndex)
                {
                    Swap(ref nums[i], ref nums[maxIndex]);
                }
            }
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
