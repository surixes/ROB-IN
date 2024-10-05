# Examples and Use Cases

## Table of Contents

1. [Scenario 1: Pathfinding on a Small Map with Obstacles](#scenario-1-pathfinding-on-a-small-map-with-obstacles)
2. [Scenario 2: Pathfinding on a Large Map with High Obstacle Density](#scenario-2-pathfinding-on-a-large-map-with-high-obstacle-density)
3. [Scenario 3: Pathfinding with Low Obstacle Probability](#scenario-3-pathfinding-with-low-obstacle-probability)
4. [Scenario 4: Dynamic Map Changes](#scenario-4-dynamic-map-changes)

## Scenario 1: Pathfinding on a Small Map with Obstacles

**Description**:
Consider a situation where the robot navigates a `10x10` map with an obstacle probability of `wall_chance=0.2`. The starting point is in the top-left corner, and the goal is in the bottom-right corner. The robot must find the optimal route while avoiding obstacles. This scenario demonstrates the system's performance under moderate complexity, with a balance of obstacles that provides a good assessment of the A\* algorithm's basic capabilities.

```Python
mappy = generate_map(10, 10, 0.2)
```

## Scenario 2: Pathfinding on a Large Map with High Obstacle Density

**Description**:
In this scenario, consider a `50x50` map with an obstacle probability of `wall_chance=0.5`. This situation models a challenging environment with numerous obstacles, making it difficult to find a path. The robot must try to find a route despite the high obstacle density. This scenario showcases the efficiency of the A\* algorithm in high-complexity situations where obstacles are abundant, and the chances of finding a clear path are reduced.

```Python
mappy = generate_map(50, 50, 0.5)
```

## Scenario 3: Pathfinding with Low Obstacle Probability

**Description**:
In this scenario, the robot moves through a `20x20` map with an obstacle probability of `wall_chance=0.1`. This is a simplified case where the map has few obstacles, allowing the robot to find a path with minimal turns. This scenario is suitable for testing the algorithm under ideal conditions with minimal obstacles, providing insight into the maximum potential efficiency of the route.

```Python
mappy = generate_map(20, 20, 0.1)
```

## Scenario 4: Dynamic Map Changes

**Description**:
In this scenario, after generating a `30x30` map with an obstacle probability of `wall_chance=0.3`, dynamic changes are made to the map—such as adding new obstacles or removing existing ones. The robot then attempts to find a path in the updated environment. This scenario demonstrates how the system handles changes in the environment, which can be useful for modeling real dynamic environments where new objects or obstacles suddenly appear.

```Python
# Generate the map
mappy = generate_map(30, 30, 0.3)

# Add dynamic changes - adding new walls
mappy[10:15, 10:15] = 1  # Add a wall in the center of the map
```

[Back to top](../../README.en.md)
