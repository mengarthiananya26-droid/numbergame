# numbergame
import java.util.Random;
import java.util.Scanner;

public class Main {

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);
        Random random = new Random();

        boolean playAgain = true;

        while (playAgain) {

            int target = random.nextInt(100) + 1;
            int guess = 0;
            int attempts = 0;

            System.out.println("==================================");
            System.out.println("     NUMBER GUESSING GAME");
            System.out.println("Guess a number between 1 and 100");
            System.out.println("==================================");

            while (guess != target) {

                System.out.print("Enter your guess: ");

                try {

                    guess = sc.nextInt();
                    attempts++;

                    if (guess < target) {
                        System.out.println("Too Low!");
                    } else if (guess > target) {
                        System.out.println("Too High!");
                    } else {
                        System.out.println("Congratulations!");
                        System.out.println("You guessed the correct number.");
                        System.out.println("Attempts: " + attempts);
                    }

                } catch (Exception e) {
                    System.out.println("Invalid input! Please enter an integer.");
                    sc.nextLine(); // Clear buffer
                }
            }

            System.out.print("Play Again? (Y/N): ");
            sc.nextLine(); // Flush leftover newline
            String choice = sc.nextLine();

            if (!choice.equalsIgnoreCase("Y")) {
                playAgain = false;
            }
        }

        System.out.println("Thank you for playing!");
        sc.close();
    }
}
