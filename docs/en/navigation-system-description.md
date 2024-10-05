# Navigation System Description

## Table of Contents

1. [General Concept](#general-concept)
2. [Features and Limitations](#features-and-limitations)
3. [A\* Algorithm (A-Star)](#a-algorithm-a-star)
4. [Path Optimization](#path-optimization)

## General Concept

The navigation system is designed to determine the optimal path for an autonomous robot in a two-dimensional environment with obstacles. The environment is represented as a matrix, where free cells are marked as `0` and obstacles are marked as `1`. The robot starts from an initial position and must reach the target position, avoiding collisions with obstacles.

## Features and Limitations

- **Map Generation**: The map is generated randomly or with specified dimensions and obstacle probabilities.
- **Static Obstacles**: The system considers only static obstacles.
- **Movement Constraints**: The robot can move only in four directions (up, down, left, right) when searching for a path using the A\* algorithm.

## A\* Algorithm (A-Star)

The A\* algorithm is used to find the shortest path from the starting point to the goal using a heuristic function to estimate the cost of the path. Manhattan distance is used as the heuristic.

## Path Optimization

After finding the initial path, optimization is performed. The goal of optimization is to reduce the number of turns and improve the overall efficiency of the robot's movement. The main idea is to add "shortcuts" at 45-degree angles, allowing the robot to reduce the number of turns.

[Back to top](../../README.en.md)
