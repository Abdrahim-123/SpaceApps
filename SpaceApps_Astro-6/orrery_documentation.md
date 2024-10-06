
# Documentation: 3D Planet and Asteroid Orbits

## Overview

This code creates a 3D orrery (planetary model) visualization using the **Three.js** library. It simulates the orbits of planets and asteroids/comets around the Sun in space. The app allows for user interaction, such as changing orbital speed, viewing object details on click, and navigating the 3D environment with mouse controls.

## File Structure

### 1. **HTML Structure**
- The core of the page is the `canvas` element managed by Three.js.
- Div elements are used for displaying:
  - **Title and Info** (`#name` and `#info`)
  - **Speed Control** (`#controls`)
  - **Object Info Popup** (`#asteroid-info`)

### 2. **CSS**
The CSS styles define the layout and design for the app:
- **Background** is set to black, with white-colored text and fonts from the 'Orbitron' family for a futuristic look.
- **Positioning**: The `#name`, `#info`, and control UI components are positioned using absolute positioning.
- **Canvas**: Takes up the entire window, and there is no scrolling (`overflow: hidden`).

### 3. **JavaScript (Three.js Integration)**

#### 3.1. **Scene Setup**
The scene is created using **Three.js** with the following components:
- **Scene**: Holds all the objects.
- **Camera**: A perspective camera for viewing the 3D space.
- **Renderer**: Renders the scene and is attached to the body of the document.
- **OrbitControls**: Allows the user to navigate the 3D space by clicking and dragging.

#### 3.2. **Adding Objects**
- **Star Field**: Created using small spheres randomly positioned in 3D space. The number of stars is adjustable (`numStars`).
- **Sun**: A sphere representing the Sun is added at the center of the scene.
- **Orbits and Objects**: 
  - The `createOrbit` function generates elliptical orbits using Kepler's laws, taking into account the semi-major axis (`a`), eccentricity (`e`), and inclination (`i`).
  - Planets and asteroids/comets are created using spheres, with customizable colors and radii.
- **Labels**: Each object is labeled using a sprite containing text.

#### 3.3. **Planetary and Asteroid Data**
The planetary and asteroid data are stored in arrays with the following parameters:
- **`a`**: Semi-major axis (orbit size)
- **`e`**: Eccentricity (how elliptical the orbit is)
- **`i`**: Inclination (tilt of the orbit)

The following celestial bodies are included:
- **Planets**: Mercury, Venus, Earth, Mars, Jupiter, Saturn, Uranus, Neptune (with adjusted orbits for better visualization).
- **Asteroids/Comets**: Ceres, Pallas, Juno, Vesta, and more.

#### 3.4. **Orbital Animation**
The app includes an animation loop:
- Time (`t`) is advanced based on a speed factor that can be controlled via a slider.
- Each object's position is updated based on its orbit, and the corresponding label is updated.

#### 3.5. **Interactive Features**
- **Speed Control**: A slider allows the user to control the simulation's orbital speed. The current speed is displayed dynamically.
- **Object Info on Click**: When a planet or asteroid is clicked, its detailed information (name, semi-major axis, eccentricity, inclination) is shown in the `#asteroid-info` popup.

#### 3.6. **Raycaster for Object Selection**
A **raycaster** is used to detect mouse clicks on planets and asteroids:
- The user clicks anywhere on the screen, and the raycaster checks for intersections with the objects.
- If an intersection occurs, the object's details are displayed; otherwise, the info box is hidden.

#### 3.7. **Responsive Design**
The window's resize event is handled to adjust the camera and renderer to the new window dimensions, ensuring the app is responsive.

## Code Highlights

### HTML:
- Basic structure with `div` elements for UI components and control sliders.

### CSS:
- Simple styles with a focus on positioning UI elements and ensuring a fullscreen canvas experience.

### JavaScript:
1. **Scene Setup**:
   ```javascript
   let scene = new THREE.Scene();
   let camera = new THREE.PerspectiveCamera(75, window.innerWidth / window.innerHeight, 0.1, 1000);
   let renderer = new THREE.WebGLRenderer();
   renderer.setSize(window.innerWidth, window.innerHeight);
   document.body.appendChild(renderer.domElement);
   ```
   This sets up the basic scene and renders it to fit the entire window.

2. **Creating Orbits and Objects**:
   ```javascript
   function createOrbit(a, e, i, color) { /*...*/ }
   function createObject(radius, color) { /*...*/ }
   ```
   These functions generate elliptical orbits and spherical objects to represent planets and asteroids.

3. **Animation**:
   ```javascript
   function animate() {
     requestAnimationFrame(animate);
     controls.update();
     time += 0.01 * speed;
     objects.forEach((entry, index) => {
       /* Orbital mechanics calculations */
     });
     renderer.render(scene, camera);
   }
   ```
   The `animate` function updates object positions over time, factoring in the orbital parameters and the speed multiplier.

4. **Interactivity with Raycaster**:
   ```javascript
   window.addEventListener('click', onMouseClick);
   function onMouseClick(event) { /*...*/ }
   ```
   The raycaster detects mouse clicks and retrieves the clicked object’s data to display detailed information.

## Future Improvements
- **Add more objects**: Additional celestial bodies, moons, or dwarf planets.
- **Realistic textures**: Use textures for the planets to add visual realism.
- **Dynamic lighting**: Implement directional lights for simulating sunlight and shadows.
- **Advanced orbital mechanics**: Introduce more complex gravitational effects or additional orbital parameters like perihelion and aphelion.

## AI Assistance
This code was developed with the assistance of **AI** to help with structuring and enhancing the implementation of the interactive 3D orrery.

