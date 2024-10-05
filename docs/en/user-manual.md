# User Manual

## Table of Contents

1. [Running the Navigation System](#running-the-navigation-system)
2. [Error Handling](#error-handling)
3. [Tips and Recommendations](#tips-and-recommendations)

## Running the Navigation System

To use the navigation system, follow these steps:

1. **Map Generation**: Use the `generate_map()` function to create the map. You can specify the height, width, and the probability of obstacles, or use the default values.

Generate a map with random height and width values (between 2 and 100) and a 30% chance of obstacles:

```Python
mappy = generate_map()
```

Generate a map with specified dimensions and a probability of obstacles (in this case, 100 rows, 100 columns, and a 60% chance of obstacles):

```Python
mappy = generate_map(100, 100, 0.6)
```

2. **Setting Start and End Points**:
   When calling the `find_path()` function, specify the start and end points for the robot's movement. For example, start at `(0, 0)` and end at `(9, 9)`:

   ```Python
   path = find_path(mappy, (0, 0), (9, 9))
   ```

If the start and end points are not specified, the default values are `(0, 0)` and `(height - 1, width - 1)`:

```Python
path = find_path(mappy)
```

3. **Pathfinding**: Use the `find_path()` function to calculate the path from the start to the end point. If a path is found, it will be returned as a list of coordinates. If no path is found, the function will return `None`.

4. **Interpreting the Pathfinding Result**: If the `find_path()` function returns a list of coordinates, it means a path has been found. Each coordinate in the list represents a point through which the robot will pass, starting from the initial point and ending at the target. If the function returns `None`, it means the path is unreachable due to obstacles on the map.

**Example of interpreting the result**:

5. **Path Optimization**: Optionally, use the `optimize_path()` function to optimize the found path. Optimization reduces the number of turns and makes the path more direct.

6. **Visualization**: Use the built-in visualization to display the map and the found path. In the opened window, the original and optimized paths will be displayed if they are found. If no path is found, only the map will be displayed.

## Error Handling

**No Path Found**: If the `find_path()` function returns `None`, it means that the target point is unreachable due to obstacles. In this case, try generating a new map or reducing the probability of obstacles.

**Example of handling a missing path error**:

![path_error](../assets/Handling_a_missing_path_error_1.png)

**Invalid Parameters**: Ensure that the parameters passed to the function meet the requirements (e.g., height and width should be greater than `1` and be integers, the probability of obstacles should be between `0` and `1` and be a float). If incorrect parameters are passed, an `AssertionError` will be raised. In this case, try passing valid values to the function and restart the program.

**Example of handling invalid parameters**:

```terminal
Traceback (most recent call last):
  File "c:\Users\path\to\directory\rob-in-main\main.py", line 160, in <module>
    mappy = generate_map(-15, 7, 0.3)
            ^^^^^^^^^^^^^^^^^^^^^^^^^
  File "c:\Users\path\to\directory\rob-in-main\main.py", line 24, in generate_map
    assert height > 1
           ^^^^^^^^^^
AssertionError
```

## Tips and Recommendations

- **Map Parameters**: Experiment with the map dimensions and obstacle probability to achieve the optimal balance between complexity and pathfinding feasibility.
- **Handling Large Maps**: Visualization may slow down for large maps. Consider reducing the image size or using more efficient visualization methods.
- **Repeatability of Generation**: For reproducible results, set a fixed random seed using `numpy.random.seed(seed_value)`.

[Back to top](../../README.en.md)
