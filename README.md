# Matrix Factorization for Design and Analaysis of Algorithms

This project implements a matrix factorization technique on numerical data from a CSV file. The provided functions perform tasks such as reading data, computing matrix means, initializing factor matrices, and iteratively adjusting these factors to minimize reconstruction error. The ultimate goal is to identify two matrices (B and C) whose product approximates the original matrix (A), with non-zero entries indicating a focus on significant data points. This methodology is commonly used in recommendation systems and for pattern recognition in datasets with latent variables. The notebook includes both randomized and ordered approaches for optimizing the matrices.

## Prerequisites and Installation

Before you begin, ensure that you have Python 3.x installed on your system. Python is necessary to run JupyterLab and the notebook. You can install JupyterLab with the following command:

`pip install jupyterlab`

## How To Execute

Install Python if you haven't already and then install JupyterLab using the command above.

Open your terminal or command prompt.

Navigate to your project folder with cd path/to/project_folder.
Start JupyterLab by typing:

`jupyter lab`

Once JupyterLab opens in your web browser, navigate to the file browser within the JupyterLab interface.

Locate the Project.ipynb Jupyter Notebook file .

Click on the file to open it in a new tab within JupyterLab.

Run the notebook cells by clicking the play button (▶️) on the toolbar, using the "Run" menu at the top, or by pressing Shift + Enter on your keyboard for each cell you want to execute.

## Functions

Here's a brief description of each function within the provided code:

- `load_data(fname)`: Loads numerical data from a CSV file and returns it as a 2D list (matrix).

- `mean_M(M)`: Calculates the mean of all non-zero entries in a matrix M.

- `create_arrays(R, C, insert_value)`: Creates a 2D array with R rows and C columns, filled with `insert_value`.

- `initial_setup(A, d)`: Initializes the factor matrices B and C with values derived from the mean of matrix A and the number of features d.

- `non_zero(M)`: Counts the number of non-zero elements in a matrix M.

- `subtract_matrices(A, P)`: Subtracts matrix P from matrix A and returns the resulting matrix.

- `calc_error(A, P)`: Calculates the root mean square error between two matrices, focusing on non-zero entries of the original matrix A.

- `adjust_B(M, B, C)`: Adjusts the B matrix by a specific formula to move towards minimizing the error with matrix A.

- `adjust_C(M, B, C)`: Adjusts the C matrix in a similar fashion to `adjust_B`, aiming to reduce the reconstruction error.

- `matrix_product(M1, M2)`: Calculates the product of two matrices M1 and M2.

- `random_update(M, d, max_runs, epsilon)`: Iteratively adjusts matrices B and C in a random order to minimize error, within a specified number of iterations or until the change in error is below a threshold.

- `ordered_update(data_mat, feat_num, max_runs, epsilon)`: Similar to `random_update`, but adjustments to B and C are made in a fixed order.

- `run_analysis(data)`: Runs both the random and ordered update methods over a range of feature numbers and tolerance levels to determine the best setup.

- `min_key(data_dict)`: Finds the key in a dictionary that corresponds to the smallest value.

- `best_setup(rand_res, ord_res, A)`: Determines the best configuration (including d and epsilon) that results in the lowest error, choosing between the random and ordered methods.
