# StringManipulationPractice

using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace ConsoleApp1
{
    class Program
    {
        public static void TryAgain()
        {
            Main();
        }
        static void Main()
        {
            Console.WriteLine("Please enter a word to check if it's a palidrome: ");
            string userInput = Console.ReadLine();

            while(true)
            {
                if(userInput == "" || userInput == null) //checks if your empty word or null
                {
                    Console.WriteLine("Invalid input please try again.");
                    userInput = Console.ReadLine();
                }
                int test = userInput.IndexOfAny("123456789 ".ToCharArray());
                if(test >= 0)
                {
                    Console.WriteLine("Invalid input please try again. ");
                    userInput = Console.ReadLine();
                    test = userInput.IndexOfAny("123456789 ".ToCharArray());
                }
                break;
            }

            char[] inputArray = userInput.ToCharArray(0, userInput.Length);

            Array.Reverse(inputArray);

            string revInput = new string(inputArray);

            if(userInput == revInput)
            {
                Console.WriteLine($"Your input {userInput} is a palindrome. ");
            }
            else
            {
                Console.WriteLine($"Your input {userInput} is NOT a palindrome. ");
            }

            Console.WriteLine("Would you like to try again?");

            if(userInput.ToLower()=="y" || userInput.ToLower() == "yes")
            {
                TryAgain();
            }
            else if(userInput.ToLower()!="y" || userInput.ToLower() != "yes")
            {
                return;
            }
            Console.Clear();
        }
    }
}

