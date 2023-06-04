# JS_Task_4
# JavaScript for Instagram Login Page

This JavaScript file provides functionality to create an interactive login page similar to Instagram's login page. It validates user input, displays error messages, and handles the login process.

## Usage

1. Include the JavaScript file in your HTML document using the `<script>` tag:

   ```html
   <script src="instagram-login.js"></script>
   ```

2. Create an HTML form with input fields and a submit button:

   ```html
   <form id="loginForm" onsubmit="login(event)">
     <input type="text" id="username" placeholder="Username" required>
     <input type="password" id="password" placeholder="Password" required>
     <button type="submit">Log In</button>
   </form>
   ```

   Ensure that each input field has a unique `id` attribute, and the form has an `id` attribute.

3. In your JavaScript code or within a `<script>` tag, define the `login` function to handle the login process:

   ```javascript
   function login(event) {
     event.preventDefault(); // Prevent form submission

     // Fetch form input values
     const usernameInput = document.getElementById('username');
     const passwordInput = document.getElementById('password');

     // Perform validation
     const username = usernameInput.value.trim();
     const password = passwordInput.value.trim();

     if (username === '') {
       showError(usernameInput, 'Username is required');
       return;
     }

     if (password === '') {
       showError(passwordInput, 'Password is required');
       return;
     }

     // Simulate login process
     simulateLogin(username, password);
   }

   function showError(inputElement, message) {
     // Clear previous error message, if any
     const errorElement = inputElement.parentNode.querySelector('.error');
     if (errorElement) {
       errorElement.remove();
     }

     // Create and append new error message
     const error = document.createElement('div');
     error.className = 'error';
     error.textContent = message;
     inputElement.parentNode.appendChild(error);
   }

   function simulateLogin(username, password) {
     // Simulate asynchronous login process
     // Replace with your own login implementation
     setTimeout(() => {
       if (username === 'user' && password === 'password') {
         // Successful login
         console.log('Login successful');
       } else {
         // Failed login
         showError(passwordInput, 'Incorrect username or password');
       }
     }, 2000); // Simulate a 2-second delay
   }
   ```

   Customize the login process according to your specific requirements. The `simulateLogin` function is a placeholder and should be replaced with your actual login implementation.



When you submit the form, the `login` function will handle the login process. In the example, the `simulateLogin` function is used to simulate an asynchronous login process. You should replace it with your own login implementation.

If the username and password match the expected values (in this case, "user" and "password"), the console will log "Login successful". Otherwise, an error message will be displayed below the password input field.

Customize the HTML structure, CSS styling, and login logic to match your desired Instagram login page.
