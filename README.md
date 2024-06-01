![A-4-way-intersection](https://github.com/Emin-35/4-Way-Cross-Walk/assets/77839861/a7302c62-6f24-44bb-b57e-b9a5cd55f3aa)

# 4-Way Crossroad Simulation
## Overview
This project simulates a 4-way crossroad intersection with cars moving in different directions. The primary focus is on preventing collisions at the intersection using semaphores to manage access to the critical crossing area. The project is implemented in Java using multithreading and graphical components from the Swing library.

## Project Structure
The project consists of several Java classes, each serving a specific purpose in the simulation. Below is a brief description of each class and its role in the project:

## 1. SemaphoreCar1, SemaphoreCar2, SemaphoreCar3, SemaphoreCar4
These classes represent individual cars moving towards the crossroad from different directions. Each class has the following responsibilities:

Variables:

Semaphore: To control access to the critical section (crossroad).

ImageIcon: The image representing the car.

Coordinates (carX, carY): To track the car's position.

Velocity (carVelocity): To control the car's speed.

Boolean (critic): To manage entry into the critical section.

Constructor: Initializes the car's properties, including its image, initial coordinates, and velocity.

Getters and Setters: Provide access to the car's properties, allowing other classes to interact with and modify these properties as needed.

## 2. CriticCar1, CriticCar2, CriticCar3, CriticCar4
These classes implement the Runnable interface and define the behavior of cars as they approach and enter the critical section of the crossroad. Each class:

Variables:

References to SemaphoreCar objects to access their properties.
Random: To generate random speeds for the cars.
Constructor: Takes references to the SemaphoreCar objects for all four cars.

run Method: Defines the behavior of the car as it moves towards the intersection:

Moves the car based on its velocity.

Checks if the car is approaching the critical section.

Acquires the semaphore to enter the critical section.

Releases the semaphore after crossing the intersection.

Resets the car's position and speed once it leaves the visible area.

## 3. CrossRoad
This class extends JPanel and implements the Runnable interface to create the graphical representation of the crossroad and manage the animation of the cars. The responsibilities of this class include:

Variables:

Car speed and coordinates.

Instances of SemaphoreCar and CriticCar classes.

Images for the cars.

Semaphore (crash): To control access to the critical section.

Threads for each car to handle their movement concurrently.

Random: To generate random car speeds.

Constructor: Initializes the crossroad panel, sets up the car objects and their corresponding threads, and configures the initial properties of the graphical components.

paintComponent Method: Overrides the JPanel method to draw the crossroad and the cars on the panel.

run Method: Continuously updates the positions of the cars and repaints the panel to reflect the changes, ensuring the animation runs smoothly.

## 4. Test
This class contains the main method and serves as the entry point for the application. It sets up the JFrame to display the crossroad simulation and starts the animation:

main Method:

Creates an instance of CrossRoad.

Configures the JFrame settings (size, visibility, location, close operation).

Adds the CrossRoad panel to the JFrame.

Starts the animation thread.

## How to Run
Ensure that the image files for the cars (redU.png, yellowD.png, etc.) are in the correct directory relative to the project's execution path.

Compile the Java files.

Run the Test class to start the simulation.

## Notes
Semaphores: Used to manage the critical section, ensuring that only one car can be in the intersection at a time to prevent collisions.

Multithreading: Each car runs in its own thread, allowing for concurrent movement and realistic simulation of traffic.

Swing Components: The graphical user interface is built using Swing, with custom drawing in the CrossRoad class to represent the cars and the road.

By following the above structure, the project achieves a simulation of a 4-way crossroad with cars moving in different directions, managing access to the intersection using semaphores to ensure safety and prevent collisions.














