# feb-2025-avasjcript-events-and-basic-interactivity

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Interactive Webpage</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      padding: 20px;
    }
    .hidden {
      display: none;
    }
  </style>
</head>
<body>

  <h1>Interactive Webpage Demo</h1>

  <!-- Form Section -->
  <h2>Login Form</h2>
  <form id="loginForm">
    <label for="username">Username:</label>
    <input type="text" id="username" name="username" required><br><br>
    
    <label for="password">Password:</label>
    <input type="password" id="password" name="password" required><br><br>
    
    <button type="submit">Login</button>
  </form>
  <p id="errorMessage" class="hidden" style="color: red;">Please fill in both fields.</p>

  <!-- Toggle Password Visibility -->
  <h2>Password Visibility Toggle</h2>
  <input type="password" id="passwordField" placeholder="Enter your password">
  <button id="togglePasswordBtn">Show/Hide Password</button>

  <!-- Interactive Element -->
  <h2>Interactive Message</h2>
  <label for="nameInput">Enter your name: </label>
  <input type="text" id="nameInput">
  <p id="greetingMessage">Hello, please enter your name above!</p>

  <script>
    // Event listener to handle form submission and validation
    const loginForm = document.getElementById('loginForm');
    const errorMessage = document.getElementById('errorMessage');

    loginForm.addEventListener('submit', function(event) {
      event.preventDefault(); // Prevent form submission for validation
      
      const username = document.getElementById('username').value;
      const password = document.getElementById('password').value;

      // Form validation
      if (!username || !password) {
        errorMessage.classList.remove('hidden');
      } else {
        errorMessage.classList.add('hidden');
        alert('Form submitted successfully!');
        loginForm.reset(); // Reset the form
      }
    });

    // Toggle password visibility
    const togglePasswordBtn = document.getElementById('togglePasswordBtn');
    const passwordField = document.getElementById('passwordField');

    togglePasswordBtn.addEventListener('click', function() {
      if (passwordField.type === 'password') {
        passwordField.type = 'text';
      } else {
        passwordField.type = 'password';
      }
    });

    // Interactive greeting message
    const nameInput = document.getElementById('nameInput');
    const greetingMessage = document.getElementById('greetingMessage');

    nameInput.addEventListener('input', function() {
      const name = nameInput.value.trim();
      if (name) {
        greetingMessage.textContent = `Hello, ${name}!`;
      } else {
        greetingMessage.textContent = 'Hello, please enter your name above!';
      }
    });
  </script>

</body>
</html>


Features:
Form Validation:

The login form has two fields: username and password.

If either field is empty when the form is submitted, an error message is displayed.

Toggle Password Visibility:

There is a password input field, and a button to toggle the visibility of the entered password.

JavaScript is used to change the type attribute of the password field between password and text.

Interactive Elements:

There's a text input where the user can type their name. The greeting message updates dynamically as the user types, displaying a personalized message.

Explanation:
Event Listeners: The form submission, password visibility toggle, and name input fields all use addEventListener to respond to user actions.

Form Validation: When the form is submitted, JavaScript checks if both fields are filled. If any field is empty, an error message is shown, and the form submission is prevented.

Interactive Elements: As the user types in the "Enter your name" field, the greeting message updates in real-time.

How It Works:
When the user submits the form, JavaScript checks whether the username and password fields are filled.

If the form is valid, a success message appears; otherwise, an error message is shown.

The user can toggle the visibility of the password by clicking the button.

As the user types their name, the greeting message updates to show a personalized greeting.
