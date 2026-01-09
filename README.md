using System;

class ATM
{
    static void Main()
    {
        int balance = 10000;
        int choice;

        Console.WriteLine("===== ATM SIMULATION SYSTEM =====");

        do
        {
            Console.WriteLine("\n1. Check Balance");
            Console.WriteLine("2. Deposit Money");
            Console.WriteLine("3. Withdraw Money");
            Console.WriteLine("4. Exit");
            Console.Write("Enter your choice: ");

            choice = Convert.ToInt32(Console.ReadLine());

            switch (choice)
            {
                case 1:
                    Console.WriteLine("Your Current Balance is: ₹" + balance);
                    break;

                case 2:
                    Console.Write("Enter amount to deposit: ₹");
                    int deposit = Convert.ToInt32(Console.ReadLine());
                    balance += deposit;
                    Console.WriteLine("Amount Deposited Successfully!");
                    break;

                case 3:
                    Console.Write("Enter amount to withdraw: ₹");
                    int withdraw = Convert.ToInt32(Console.ReadLine());

                    if (withdraw <= balance)
                    {
                        balance -= withdraw;
                        Console.WriteLine("Please collect your cash.");
                    }
                    else
                    {
                        Console.WriteLine("Insufficient Balance!");
                    }
                    break;

                case 4:
                    Console.WriteLine("Thank you for using ATM!");
                    break;

                default:
                    Console.WriteLine("Invalid Choice. Try Again.");
                    break;
            }

        } while (choice != 4);
    }
}
