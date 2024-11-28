## README for 102ARCHITECT
# Overview

102ARCHITECT is a home-planning software designed for an architecture firm. 
Its primary objective is to simplify architectural drafting by providing tools for geometric transformations, allowing users to manipulate points and objects in 2D space using homogeneous coordinates.

**This software supports:**

    Translating points
    Scaling objects
    Rotating points around the origin
    Reflecting points over a defined axis
    Combining multiple transformations into a sequence

The program runs in the terminal and avoids using external matrix libraries, ensuring efficiency and self-contained operations.

**Features**

    Translation: Move points along a vector.
    Scaling: Adjust the size of points relative to the origin.
    Rotation: Rotate points around the origin by a specified degree.
    Reflection: Reflect points over any axis passing through the origin.
    Combination: Chain multiple transformations for complex operations.

# Usage

./102architect x y transfo1 arg11 [arg12] [transfo2 arg21 [arg22]] ...

***Parameters**

    x, y: Coordinates of the point to transform.
    transfo: Transformation type:
        -t i j: Translation along vector (i, j).
        -z m n: Scaling by factors m (x-axis) and n (y-axis).
        -r d: Rotation by d degrees around the origin.
        -s d: Reflection over the axis with an inclination angle d degrees.

# Compilation

Compile the program using the provided Makefile:

    make to build the program.
    make clean to remove temporary files.
    make fclean to remove all generated files, including the binary.
    make re to rebuild the program from scratch.

# Examples

**Translation**

./102architect 5 0 -t -1 1

Result: (5.00, 0.00) => (4.00, 1.00)

**Scaling**

./102architect 2 2 -z -1 1

Result: (2.00, 2.00) => (-2.00, 2.00)

**Rotation**

./102architect 1 0 -r 90

Result: (1.00, 0.00) => (0.00, 1.00)

**Reflection**

./102architect 3 -1 -s 270

Result: (3.00, -1.00) => (-3.00, -1.00)

**Combination**

./102architect 1 2 -t 2 3 -z 1 -2 -r 45 -s 30

Result: (1.00, 2.00) => (0.31, 10.44)

# Error Handling

    Invalid inputs result in error messages sent to standard error output.
    The program exits with code 84 for errors or 0 on success.

# License

This project is released under the MIT License.

Enjoy using 102ARCHITECT for your architectural drafting needs!
