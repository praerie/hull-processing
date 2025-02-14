# Hull Processing

Python-based computational geometry playground focused on convex hull construction and visualization.

## Graham's Scan: Convex Hull Construction

[convex_hull.py](/convex_hull.py) computes the convex hull of a set of 2D points using implements Graham's scan algorithm.

### Steps:

1. Find the starting point by selecting the lowest point (or the leftmost if tied).
2. Sort all points by polar angle relative to the starting point to determine processing order.
3. Build the hull contour by iterating through the sorted points, removing any that introduce a concave (clockwise) turn before adding the next point.

Visualized using `matplotlib`, the result is the smallest convex polygon enclosing all given points:

<p align="center">
  <img src="assets/grahams_scan.png" alt="Convex Hull" width="550">
</p>

#### Processing time: `O(n log n)`

## Animated Convex Hull Construction

[convex_hull_animated.py](/convex_hull_animated.py) visualizes the step-by-step construction of a convex hull using Graham's scan. Each animation frame highlights a point as it is evaluated for inclusion: it is added if it maintains a counterclockwise turn or removed if it introduces a concave (clockwise) turn.

### Steps:
1. Sort points by x-coordinate (and y if tied) to establish a processing order.
2. Build the lower hull by iterating from left to right, adding points and removing concave turns.
3. Build the upper hull by iterating in reverse, applying the same counterclockwise rule.
4. Animate each step, highlighting points as they are evaluated, added, or removed.
5. Display the complete hull contour as the final animation frame.