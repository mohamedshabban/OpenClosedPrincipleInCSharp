https://chat.openai.com/share/e10bfd6b-3ea0-4dfb-8491-51a14fa71b2d

﻿namespace OCS_Principle
{
    internal class Program
    {
        static void Main(string[] args)
        {
            //Console.WriteLine("Hello, World!");
            CustomerSilver customerSilver = new CustomerSilver();
            Console.WriteLine(customerSilver.GetDiscount(300)); ;

            GoldCustomer goldCustomer = new GoldCustomer();
            Console.WriteLine(goldCustomer.GetDiscount(300));
        }
    }
    /// <summary>
    /// the “Customer” class is now closed 
    /// for any new modification 
    /// but it’s open for extensions when
    /// new customer types are added to the project.
    /// </summary>
    public class Customer
    {
        public virtual double GetDiscount(double TotalSales)
        {
            return TotalSales;
        }
    }
    public class CustomerSilver : Customer
    {
        public override double GetDiscount(double TotalSales)
        {
            return base.GetDiscount(TotalSales) - 100;
        }
    }
    public class GoldCustomer : Customer
    {
        public override double GetDiscount(double TotalSales)
        {
            return base.GetDiscount(TotalSales) - 50;
        }
    }
}
