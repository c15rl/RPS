# RPS
CS1 assignment (Dalton)
import java.util.Random;
import java.util.Scanner;


public class RPS {
/*Author- Raina
 * 
 * Bonuses- GUN option, keeping score, and Ignore Case
 * 
 * Errors: N/A
 * 
 * Changes: minor bug fixes and added the feature to keep score
 * 
 */

	public static void main(String[] args) 
	{

		String user = "";	//user
		Scanner input = new Scanner(System.in);	//user
		boolean letter = true;//user selection loop
		
		int nbr = 0;	//computer
		Random ran = new Random(); 
		
		int wins = 0;
		int loss = 0;
		int ties = 0;
		 
		int round = 1;//round

		while ( round <= 5)
		{

			letter = true;

			while (letter == true)
			{
				System.out.println("Use the 'R', 'P', or 'S' button to pick Rock, Paper, or Scissors");
				user = input.nextLine();

				if	(user.equalsIgnoreCase ("R"))	//user picked rock
				{	
					System.out.println("You picked Rock");	

					letter = false;
				}
				else if (user.equalsIgnoreCase ("P"))	//user picked paper
				{	
					System.out.println("You Picked Paper");
					letter = false;

				}
				else if (user.equalsIgnoreCase ("S"))	//user picked scissors
				{	
					System.out.println("You picked Scissors");	
					letter = false;

				}
				//I'm  going to write the Gun option
				else if (user.equalsIgnoreCase ("G"))	//user picked Gun
				{
					System.out.println("You picked Gun");
					letter = false;

				}
				else
				{		//wrong input
					System.out.println("You didn't pick a proper input. Please type a capital R, S, or P to make your selection");	//invalid option		
					letter = true;

				}


			} //end of user while

			nbr = ran.nextInt(3);
			nbr = nbr + 1;
			
				if(nbr == 1)	//computer # 1 = rock
					System.out.println("computer chose rock");

				if (nbr == 1 && user.equalsIgnoreCase ("R"))	//rock v. rock
				{		
					System.out.println("There was a tie!");
					ties++;
				}	

				else if (nbr == 1 && user.equalsIgnoreCase ("S"))	//scissors v. rock
				{		
					System.out.println("The computer wins");
					loss++;
				}

				else if (nbr == 1 && user.equalsIgnoreCase ("P"))	//paper v. rock
				{		
					System.out.println("You win");
					wins++;

				}

				else if (nbr == 1 && user.equalsIgnoreCase ("G"))	// gun v. rock
				{		
					System.out.println("You win");
					wins++;
				}

				if (nbr == 2)	//computer # 2 paper
					System.out.println("The computer picked Paper.");


				if (nbr == 2 && user.equalsIgnoreCase ("P"))	//paper v. paper
				{
					System.out.println("It is a tie");
					ties++;
				}

				else if (nbr == 2 && user.equalsIgnoreCase ("R"))	//rock v. paper
				{
					System.out.println("The computer wins");
					loss++;
				}

				else if (nbr == 2 && user.equalsIgnoreCase ("S"))	//scissors v. paper
				{
					System.out.println("You win");
					wins++;
				}

				else if (nbr == 2 && user.equalsIgnoreCase ("G"))	//gun v. paper
				{		
					System.out.println("You win");
					wins++;
					
				}

				if (nbr == 3)	//computer # 3 scissors
					System.out.println("The computer picked Scissors.");

				if (nbr == 3 && user.equalsIgnoreCase ("S"))	//scissors v. scissors
				{
					System.out.println("It is a tie");
					ties++;
				}

				else if (nbr == 3 && user.equalsIgnoreCase ("P"))	//paper v. scissors
				{
					System.out.println("The Computer Wins");
					loss++;
				}

				else if (nbr == 3 && user.equalsIgnoreCase ("R"))	//rock v. scissors
				{
					System.out.println("You win");
					wins++;
				}

				else if (nbr == 3 && user.equalsIgnoreCase ("G"))	//gun v. scissors
				{		
					System.out.println("You win");
					wins++;
				}
			
			round++;
		}// round end
	System.out.println("You won " + wins + " times. You lost " + loss + " times. You tied " + ties + " times.");	
	}	//program	

}//main
