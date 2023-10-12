# OIBSIP TASK 2
Oasis Infobyte Java Development Internship Tasks. # Task2

//                                             :::TASK 2:::
//****************************************NUMBER GUESSING GAME*******************************************************

import java.util.Random;

public class task2 {

    public static void main(String[] args) {
        // Generate a random number
        Random random = new Random();
        int number = random.nextInt(100) + 1;

        // Initialize the number of attempts
        int attempts = 0;

        // Start the game loop
        while (true) {
            // Prompt the user to enter a number
            System.out.print("Enter a number: ");
            int guess = Integer.parseInt(System.console().readLine());

            // Check if the guess is correct
            if (guess == number) {
                System.out.println("You guessed the number!");
                break;
            } else {
                // Increment the number of attempts
                attempts++;

                // Tell the user if the guess is too high or too low
                if (guess < number) {
                    System.out.println("Your guess is too low.");
                } else {
                    System.out.println("Your guess is too high.");
                }
            }
        }

        // Display the final score
        System.out.println("You guessed the number in " + attempts + " attempts.");
    }
}

