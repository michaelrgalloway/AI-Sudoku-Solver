# Artificial Intelligence Nanodegree
## Introductory Project: Diagonal Sudoku Solver

# Question 1 (Naked Twins)
Q: How do we use constraint propagation to solve the naked twins problem?  
A: During the naked twins algorithm, we reduced the gridspace that we look in by first reducing the relative gridspace (in regards to the current cell), by searching through
a unit at a time. Then within the scope of this unit we look for duplicate 2-digit values. If we find a duplicate, we can then reduce the space even more by taking a subset of the 
current unit space. With each of the nodes in this subset, we can remove individual digits from the pair match from these nodes because the only nodes that can possibly contain these
values are the duplicates found.

# Question 2 (Diagonal Sudoku)
Q: How do we use constraint propagation to solve the diagonal sudoku problem?  
A: Before we had 3 unit spaces, row, column and block. However now we have introduced another, however smaller, unit space. The diagonal unit space. Just like the previous 3, we can simply
add the definition of the diaginal unit space to the unitlist list. Since this space only consists of 2 sets, I have simply assigned the sets manually consisting of 
(RMin++,CM++) and (RMin++,CMax--).

Since our existing function use the unitlist as constraints, simply adding the diagonal unit space to the unit definition, the constraint will automatically be incorporated into the 
searching and solving of the puzzle. 

### Install

This project requires **Python 3**.

We recommend students install [Anaconda](https://www.continuum.io/downloads), a pre-packaged Python distribution that contains all of the necessary libraries and software for this project. 
Please try using the environment we provided in the Anaconda lesson of the Nanodegree.

##### Optional: Pygame

Optionally, you can also install pygame if you want to see your visualization. If you've followed our instructions for setting up our conda environment, you should be all set.

If not, please see how to download pygame [here](http://www.pygame.org/download.shtml).

### Code

* `solutions.py` - You'll fill this in as part of your solution.
* `solution_test.py` - Do not modify this. You can test your solution by running `python solution_test.py`.
* `PySudoku.py` - Do not modify this. This is code for visualizing your solution.
* `visualize.py` - Do not modify this. This is code for visualizing your solution.

### Visualizing

To visualize your solution, please only assign values to the values_dict using the ```assign_values``` function provided in function.py

### Data

The data consists of a text file of diagonal sudokus for you to solve.