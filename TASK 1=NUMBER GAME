import java.util.Random;
import java.util.Scanner;

public class InteractiveNumberGame {
    private int secretNumber;
    private int maxAttempts;
    private int currentAttempts;
    private int score;
    private Scanner input;

    public InteractiveNumberGame() {
        input = new Scanner(System.in);
        score = 0;
        maxAttempts = 7; 
    }
    private void generateRandomNumber() {
        Random rand = new Random();
        secretNumber = rand.nextInt(100) + 1;
        currentAttempts = 0;
    }
    private void playRound() {
        generateRandomNumber();
        System.out.println("\n--- New Round Started ---");
        System.out.println("I'm thinking of a number between 1 and 100.");
        System.out.println("You have " + maxAttempts + " attempts. Good luck!");

        boolean guessedCorrectly = false;

        while (currentAttempts < maxAttempts) {
            System.out.print("Enter your guess: ");
            int guess;

            try {
                guess = Integer.parseInt(input.nextLine());
            } catch (NumberFormatException e) {
                System.out.println("Invalid input. Please enter a valid number.");
                continue;
            }

            currentAttempts++;

            if (guess < secretNumber) {
                System.out.println("Too low!");
            } else if (guess > secretNumber) {
                System.out.println("Too high!");
            } else {
                System.out.println("Correct! You guessed it in " + currentAttempts + " attempts.");
                score += 10; // Award points for correct guess
                guessedCorrectly = true;
                break;
            }

            System.out.println("Attempts left: " + (maxAttempts - currentAttempts));
        }

        if (!guessedCorrectly) {
            System.out.println("Oops! You've used all your attempts. The number was: " + secretNumber);
        }

        System.out.println("Your current score: " + score);
    }
    private boolean askToPlayAgain() {
        System.out.print("Do you want to play another round? (yes/no): ");
        String choice = input.nextLine().trim().toLowerCase();
        return choice.equals("yes") || choice.equals("y");
    }

    public void startGame() {
        System.out.println("Welcome to the Number Guessing Game!");
        System.out.println("Try to guess the number with as few attempts as possible.");

        do {
            playRound();
        } while (askToPlayAgain());

        System.out.println("\nThanks for playing! Your final score: " + score);
    }

    public static void main(String[] args) {
        InteractiveNumberGame game = new InteractiveNumberGame();
        game.startGame();
    }
}
