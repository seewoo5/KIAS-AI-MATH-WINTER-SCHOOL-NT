# Machine Learning and Number Theory

This is a repository for the number theory group of  [KIAS Winter School on Mathematics and AI](https://chlee-0.github.io/2025-KIAS-Winter-School-Math-AI/).
It contains tutorials which guide you to learn how simple machine learning algorithms can be used to predict wide range of number-theoretic invariants.

# Setup

## Requirements

- Python
    - [lmfdb-lite](https://github.com/roed314/lmfdb-lite)
    - [matplotlib](https://matplotlib.org/)
    - [numpy](https://numpy.org/)
    - [polars](https://pola.rs/)
    - [sklearn](https://scikit-learn.org/stable/)
    - [tqdm](https://tqdm.github.io/)
- [SageMath](https://www.sagemath.org/)

## Installation

First, install SageMath.
To use the python packages "inside" SageMath shell:

1. Open Sage shell in terminal as

    ```sh
    sage --sh
    ```

2. Use `pip3` to install the packages. If you are using MacOS, you need to install `polars-lts-cpu`.

    ```sh
    pip3 install -U "lmfdb-lite[pgbinary] @ git+https://github.com/roed314/lmfdb-lite.git"
    pip3 install matplotlib numpy polars-lts-cpu scikit-learn tqdm
    ```

3. Exit the Sage shell.

    ```sh
    exit
    ```

4. Now you can use these libraries in Sage as:

    ```
    $ sage
    ┌────────────────────────────────────────────────────────────────────┐
    │ SageMath version 10.6, Release Date: 2025-03-31                    │
    │ Using Python 3.12.5. Type "help()" for help.                       │
    └────────────────────────────────────────────────────────────────────┘
    sage: import polars as pl
    sage: df = pl.DataFrame()
    sage: df
    shape: (0, 0)
    ┌┐
    ╞╡
    └┘
    ```

When running Jupyter notebooks, use SageMath kernel instead of Python kernel.

# Problem Set 0: Machine Learning Basics

For the basics of machine learning, follow [this scikit-learn tutorial](https://www.geeksforgeeks.org/machine-learning/learning-model-building-scikit-learn-python-machine-learning-library/) on iris dataset.
In particular, use logistic regression and decision tree to solve the classification problem.
You can skip this part if you are already familiar with the scikit-learn library.

# Problem Set 1: Predict invariants of elliptic curves

See `pset1_ec.ipynb`.
This is a notebook for reproducing the experiments by Yang-Hui He, Kyu-Hwan Lee, Thomas Oliver, and Alexey Podznyakov on predicting the ranks and the torsion subgroups of elliptic curves.

References:

- Yang-Hui He, Kyu-Hwan Lee, Thomas Oliver, "Machine learning invariants of arithmetic curves", Journal of Symbolic Computation, 2023
- Yang-Hui He, Kyu-Hwan Lee, Thomas Oliver, Alexey Podznyakov, "Murmuration of Elliptic Curves", Experimental Mathematics, 2024

# Problem Set 2: Predict invariants of number fields

See `pset2_nf.ipynb`.
This is a notebook for reproducing the experiments by Yang-Hui He, Kyu-Hwan Lee, and Thomas Oliver on predicting signature and Galois group of number fields.

Reference:
- Yang-Hui He, Kyu-Hwan Lee, Thomas Oliver, "Machine-learning number fields", Mathmatics, Computation and Geometry of Data, 2022

- Kyu-Hwan Lee, Seewoo Lee, "Machines Learn Number Fields, But How? The Case of Galois Groups", preprint

# Problem Set 3: Use `lmfdb-lite` to query other data

See `pset3_db.ipynb`.
This is a notebook for querying data of Artin representations and abelian varieties over finite fields from LMFDB, using [`lmfdb-lite`](https://github.com/roed314/lmfdb-lite).