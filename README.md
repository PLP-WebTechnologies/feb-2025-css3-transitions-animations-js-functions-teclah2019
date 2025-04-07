# CSS3 Transitions, Animations, and Advanced JavaScript Functions

## Objectives

Create smooth CSS transitions and animations.
Use JavaScript functions for dynamic behavior.
Implement local storage for data persistence.

## Instructions
Add CSS animations to elements like buttons or images.

>[!NOTE]
> - Write a JavaScript function that:
> - Stores and retrieves user preferences using localStorage.
> - Implements an animation triggered by user actions.

## Tasks

Create a CSS animation.
Store data in localStorage.
Apply JavaScript to trigger animations.

Happy Coding! 💻✨




<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Interactive Animations and LocalStorage</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      transition: background-color 0.5s, color 0.5s;
      padding: 20px;
    }
    .btn {
      background-color: #4CAF50;
      color: white;
      padding: 10px 20px;
      font-size: 16px;
      border: none;
      cursor: pointer;
      border-radius: 5px;
      transition: transform 0.3s ease, background-color 0.3s;
    }
    .btn:hover {
      transform: scale(1.1);
      background-color: #45a049;
    }
    .btn:active {
      transform: scale(0.9);
    }

    .dark-mode {
      background-color: #333;
      color: white;
    }
    .light-mode {
      background-color: #f4f4f4;
      color: black;
    }

    @keyframes fadeIn {
      from {
        opacity: 0;
      }
      to {
        opacity: 1;
      }
    }

    .fade-in {
      animation: fadeIn 2s ease-in-out;
    }
  </style>
</head>
<body id="body" class="fade-in">

  <h1>Welcome to the Interactive Page</h1>
  <p>Click the button below to toggle between light and dark modes.</p>
  
  <!-- Button to toggle theme -->
  <button class="btn" id="themeToggleBtn">Toggle Dark/Light Mode</button>

  <script>
    // Function to retrieve theme from localStorage and apply it
    function applyTheme() {
      const savedTheme = localStorage.getItem('theme');
      const body = document.getElementById('body');
      if (savedTheme) {
        body.classList.add(savedTheme);
      } else {
        body.classList.add('light-mode'); // Default theme
      }
    }

    // Function to toggle theme and store preference in localStorage
    function toggleTheme() {
      const body = document.getElementById('body');
      if (body.classList.contains('light-mode')) {
        body.classList.remove('light-mode');
        body.classList.add('dark-mode');
        localStorage.setItem('theme', 'dark-mode'); // Save the dark mode preference
      } else {
        body.classList.remove('dark-mode');
        body.classList.add('light-mode');
        localStorage.setItem('theme', 'light-mode'); // Save the light mode preference
      }
    }

    // Event listener to trigger theme toggle
    document.getElementById('themeToggleBtn').addEventListener('click', toggleTheme);

    // Apply the stored theme on page load
    applyTheme();
  </script>

</body>
</html>





Explanation of the Code:
CSS3 Transitions and Animations:

Button Hover Effect: The button scales up when hovered over and scales down when clicked (active state) using CSS transitions.

Fade-In Animation: A simple CSS keyframe animation (fadeIn) makes the page content fade in when it first loads. This is applied to the body with the fade-in class.

JavaScript Functions:

applyTheme: This function retrieves the saved theme from localStorage and applies it to the body. It checks if a theme is already stored (either light-mode or dark-mode).

toggleTheme: When the button is clicked, this function toggles between light and dark modes. It also stores the user's preference in localStorage so that the theme persists across page reloads.

localStorage:

The user's theme preference (either light-mode or dark-mode) is stored in localStorage. This allows the theme to persist even when the page is reloaded or the browser is closed and reopened.

The theme is retrieved and applied to the body when the page loads via the applyTheme function.

Features:
Animations: The page content fades in on load, and the button has smooth transition effects for hover and active states.

JavaScript and localStorage: JavaScript is used to toggle between themes and save the user's preference, ensuring that the theme is applied correctly when the page is reloaded.

Dynamic Behavior: The button provides interactive behavior, allowing the user to switch between light and dark modes.

Testing:
When you load the page for the first time, the default theme will be light mode. If you toggle the theme to dark mode, the change will be saved. When the page reloads, it will remember the user's last theme preference.
