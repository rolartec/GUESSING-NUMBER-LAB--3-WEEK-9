GUESSING-NUMBER-LAB--3-WEEK-9
=============================

GUESSING NUMBER WITH RANDOM  LOW AND HIGH NUMBER


//  BY  REINA  OLARTE

//   LAB #3  WEEK # 9

import java.util.Scanner;// imports the scanner class

public class GuessingNumberwithRandomMethod 
{
	public static void main( String[]args)
	{
		//Create the Scanner to input the number
		Scanner input = new Scanner(System.in);

		//instantiate random number
		RandomNumber GuessedNumber = new RandomNumber();

		//   variables
		int UserNumber;
		int UserHighRange;
		int UserLowRange;
		int computerNumber;
		boolean SIGA = true;
		boolean PLAY = true;
		String SINO;

		while(PLAY)
		{


			System.out.println("Welcome to the Guessing game\nPlease enter a Range\nPlease enter a Low Number that you would like the computer to generate.\n");
			UserLowRange = input.nextInt();

			System.out.println("Please enter a High Number that you would like the computer to generate.\n");
			UserHighRange = input.nextInt();


			while(SIGA)
			{


				computerNumber = GuessedNumber.GetAHighNumber(UserLowRange);

				System.out.printf("Now Try to Guess the number between %d and %d\n",UserLowRange,UserHighRange);
				UserNumber = input.nextInt();

				if (computerNumber == UserNumber)
				{
					System.out.println("You Guessed the right number");
					System.out.printf("Your number %d, Random number %d" , UserNumber, computerNumber);
				}

				else
					{
						if (computerNumber < UserNumber)
						{
							System.out.println("You Guessed to High");
							System.out.printf("Your number %d, Random number %d" , UserNumber, computerNumber);
						}
						else
						{	System.out.println("You Guessed to Low");
						System.out.printf("Your number %d, Random number %d" , UserNumber, computerNumber);
						}//end else	
					}//end else
				System.out.println("\nWould you like to continue Guessing?\nPress Y for yes N for no");
				SINO = input.next();

				if (SINO.toUpperCase().startsWith("Y"))
				{
					SIGA = true;
				}
				else
				{
					SIGA = false;
				}
			}//end SIGA loop
				

		}//end loop
	}//End main

}//End class
