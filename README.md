# Java Password Generator

The **Java Password Generator** is a tool designed to help users create strong, customizable passwords based on their specific needs. It allows users to specify the length of their password and select which types of characters they want to include, such as lowercase letters, uppercase letters, numbers, and symbols. After generating the password, the program evaluates its strength based on the diversity of characters used.

## Features

- **Password Customization**: Users can specify the password length and choose character types such as lowercase letters, uppercase letters, digits, and symbols.
- **Randomness**: The password is generated randomly using Java’s `Random` class to ensure uniqueness and unpredictability.
- **Strength Evaluation**: After generating the password, the program evaluates its strength based on how many different types of characters it contains and assigns a score accordingly.

## Program Workflow

1. **User Input**: The program asks users for the desired password length and character types (e.g., lowercase, uppercase, digits, symbols).
2. **Password Generation**: Based on the user’s selections, the program builds a password using random characters from the specified sets. It uses `StringBuilder` for efficient string manipulation.
3. **Strength Evaluation**: The program checks the password for the presence of different character types using regular expressions and then calculates a strength score.

## Challenges and Solutions

- **Character Pool Adjustment**: A significant challenge was adjusting the available character pool based on the user’s selections. The program dynamically includes or excludes character sets (e.g., lowercase, uppercase) depending on the user’s choices.
- **Strength Evaluation**: Evaluating password strength in a simple yet effective way was another challenge. The solution was to assign a score based on how many types of characters (lowercase, uppercase, digits, symbols) were used in the generated password.

## Improvements

- **Customization**: The program was improved to offer more flexibility, allowing users to choose exactly which character types to include, compared to the basic options available in earlier versions.
- **Strength Evaluation**: The strength evaluation process was simplified, making it easier for users to understand the password’s security level based on the variety of character types used.

## User Interaction

The program interacts directly with the user through the console, where users input their preferences and instantly receive the generated password along with its strength score. No files are used for input or output; everything is handled in real time.

## Conclusion

The **Java Password Generator** is a simple yet powerful tool that helps users create secure, customizable passwords. It’s a useful program for anyone looking to enhance their online security. The project also serves as a great introduction to creating interactive and customizable software in Java.
