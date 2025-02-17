import java.util.Random;
import java.util.Scanner;

public class Main {


    private static final String LOWERCASE = "abcdefghijklmnopqrstuvwxyz";
    private static final String UPPERCASE = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";
    private static final String NUMBERS = "0123456789";
    private static final String SYMBOLS = "!@#$%^&*()-_=+[]{};:'\",.<>/?`~";

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);


        System.out.print("Enter the minimum password length: ");
        int minLength = scanner.nextInt();
        System.out.print("Enter the maximum password length: ");
        int maxLength = scanner.nextInt();


        if (minLength > maxLength || minLength <= 0) {
            System.out.println("Invalid length range. Please try again.");
            return;
        }

        System.out.print("Include lowercase letters? (y/n): ");
        boolean includeLowercase = scanner.next().equalsIgnoreCase("y");
        System.out.print("Include uppercase letters? (y/n): ");
        boolean includeUppercase = scanner.next().equalsIgnoreCase("y");
        System.out.print("Include numbers? (y/n): ");
        boolean includeNumbers = scanner.next().equalsIgnoreCase("y");
        System.out.print("Include symbols? (y/n): ");
        boolean includeSymbols = scanner.next().equalsIgnoreCase("y");

        if (!includeLowercase && !includeUppercase && !includeNumbers && !includeSymbols) {
            System.out.println("You must include at least one character type.");
            return;
        }


        String password = generatePassword(minLength, maxLength, includeLowercase, includeUppercase, includeNumbers, includeSymbols);
        System.out.println("Generated Password: " + password);


        int strength = evaluatePasswordStrength(password);
        System.out.println("Password Strength: " + strength + "/4");
    }

    private static String generatePassword(int minLength, int maxLength, boolean includeLowercase, boolean includeUppercase, boolean includeNumbers, boolean includeSymbols) {
        StringBuilder characterSet = new StringBuilder();
        Random random = new Random();


        if (includeLowercase) characterSet.append(LOWERCASE);
        if (includeUppercase) characterSet.append(UPPERCASE);
        if (includeNumbers) characterSet.append(NUMBERS);
        if (includeSymbols) characterSet.append(SYMBOLS);


        int length = random.nextInt(maxLength - minLength + 1) + minLength;

        StringBuilder password = new StringBuilder();
        for (int i = 0; i < length; i++) {
            int randomIndex = random.nextInt(characterSet.length());
            password.append(characterSet.charAt(randomIndex));
        }

        return password.toString();
    }

    private static int evaluatePasswordStrength(String password) {
        int score = 0;


        if (password.matches(".*[a-z].*")) score++;

        if (password.matches(".*[A-Z].*")) score++;
        if (password.matches(".*[0-9].*")) score++;
        if (password.matches(".*[!@#$%^&*()\\-_=+\\[\\]{};:'\",.<>/?`~].*")) score++;

        return score;
    }
}
