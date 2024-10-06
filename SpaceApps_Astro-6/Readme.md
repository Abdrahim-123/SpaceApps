# 3D Planet and Asteroid Orbits Web Application

This project is a web application that visualizes the orbits of planets and asteroids in a 3D space using Three.js. Users can interact with the scene, control the speed of the orbits, and click on objects to view their details.

## Table of Contents

- [Features](#features)
- [Technologies Used](#technologies-used)
- [Getting Started](#getting-started)
- [Code Overview](#code-overview)
  - [HTML Structure](#html-structure)
  - [CSS Styles](#css-styles)
  - [JavaScript Logic](#javascript-logic)
- [How to Use](#how-to-use)
- [Contributing](#contributing)

## Features

- 3D visualization of planetary orbits and asteroids
- Interactive controls to adjust the speed of the orbits
- Clickable objects that display their orbital details
- Responsive design that works on various screen sizes

## Technologies Used

- **HTML**: For the structure of the web application
- **CSS**: For styling the application
- **JavaScript**: For adding interactivity and 3D rendering
- **Three.js**: A JavaScript library for 3D graphics
- **OrbitControls**: For enabling camera controls

## Getting Started

1. Clone this repository to your local machine:
   ```bash
   git clone https://github.com/yourusername/3d-planet-orbits.git
   ```
2. Open the `index.html` file in your web browser.

## Code Overview

### HTML Structure

The HTML file contains the following key elements:

- **Head**: Includes meta tags, title, Google Fonts, and CSS styles.
- **Body**: Contains div elements for displaying information about the application, controls for adjusting orbital speed, and a section for displaying asteroid information.

### CSS Styles

The CSS styles are defined to create a visually appealing layout:

- Set the background color to black and text color to white.
- Use the 'Orbitron' font for a futuristic look.
- Style the controls and information displays to be positioned correctly on the screen.

### JavaScript Logic

The JavaScript section is where most of the application logic resides:

1. **Three.js Setup**: Initializes the scene, camera, renderer, and orbit controls.
2. **Star Field Creation**: Generates a field of stars randomly positioned in the 3D space.
3. **Orbit and Object Creation**: Functions to create orbits for planets and asteroids based on their orbital parameters.
4. **Animation Loop**: Updates the positions of objects based on time and speed, and renders the scene.
5. **Mouse Interaction**: Detects mouse clicks to display information about clicked objects.
6. **Responsive Design**: Handles window resizing to maintain the aspect ratio of the scene.

## How to Use

- Open the application in a web browser.
- Use the speed control slider to adjust the orbital speed of the planets and asteroids.
- Click on any planet or asteroid to view its details, including its name, semi-major axis, eccentricity, and inclination.

## Contributing

Contributions are welcome! If you would like to contribute to this project, please fork the repository and submit a pull request with your changes.

