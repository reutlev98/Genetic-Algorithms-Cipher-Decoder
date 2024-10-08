
# Genetic Algorithms Cipher Decoder

## Overview

This project implements genetic algorithms to solve a specific permutation problem in computational biology. The program is capable of simulating different evolutionary models, including a standard genetic algorithm, a Darwin-based approach, and a Lamarck-based approach. The program is designed to be run with multiple threads for improved performance and efficiency.

## Features

- **Choice of Algorithm**: Users can select between the following algorithms:
  - **Standard Genetic Algorithm**: A baseline evolutionary approach without local optimizations.
  - **Lamarckian Evolutionary Model**: Applies local optimizations directly to each solution and saves these changes to the population.
  - **Darwinian Evolutionary Model**: Applies local optimizations temporarily for evaluating fitness but does not keep the optimizations in the subsequent generations.
    

- **Multithreading Support**: The program supports running the algorithm with multiple threads for parallel processing.
- **Fitness Evaluation**: Evaluates solutions based on the number of real words decoded using the given permutation and compares frequency distributions.
- **Stopping Criteria**: Stops based on fitness score improvement over generations or after a predefined number of generations without improvement.

## Algorithm Details

### Lamarckian Evolutionary Model
The Lamarckian model applies local optimizations to each solution, allowing it to learn and adapt better before being added to the next generation. If a solution benefits from an improvement (e.g., better decoding of words), these changes are retained when the solution is carried forward. This approach helps increase the average fitness of the population as solutions become more refined over time.

### Darwinian Evolutionary Model
In contrast, the Darwinian model uses local optimizations purely for evaluation. After assessing a solution's fitness with the optimizations, it reverts to its original state before being added to the next generation. This model relies more on natural selection and the variety of mutations to guide evolution, potentially retaining more diversity but progressing slower compared to the Lamarckian model.

## Population Initialization

- The initial population is generated with 1,000 randomly created solutions. Each solution is a permutation of 26 English alphabet letters.
- The initial solutions contain no repeated characters, ensuring a diverse set of starting points.
- From this initial population, a fitness score is calculated for each solution based on the number of real words decoded from the encrypted text and their adherence to expected letter frequency distributions.

## Running the Program
1. Clone the repository and navigate to the project directory:
    ```bash
    git clone <repository-link>
    cd <repository-folder>
    ```
2. Run the program using the following command:
    ```bash
    python main.py
    ```
    Or run the exe file - `main.exe` by double clicking. The output files `txt.plain` and `txt.perm` will appear in the folder of the exe file along with the input files
3. You will be prompted to choose the type of algorithm to run (Standard, Lamarck, or Darwin).
   
   ![image](https://github.com/user-attachments/assets/b821e00b-418c-4ab5-8532-5327d6f56353)


### Example Files

- **Input**: Provide input files like `plain.txt` and `perm.txt` in the same directory as `main.exe` if using the compiled version.
- **Output**: The decoded text and performance metrics will be saved in the output directory.


## Conclusion

Through testing and analysis, we found that the **Lamarckian model** tends to reach higher fitness values faster than the **Darwinian model** due to its ability to directly incorporate improvements into the population. However, the Darwinian approach helps maintain genetic diversity for a longer period, which can be beneficial in avoiding premature convergence to suboptimal solutions. The standard genetic algorithm offers a balanced, simpler approach, but it generally performs less efficiently than the Lamarckian model for this problem.

## About This Project

This project was developed as part of an exercise in computational biology, focusing on the use of genetic algorithms for decoding tasks. It explores different approaches to evolutionary optimization and compares their effectiveness based on fitness scores and accuracy of decoded text. 

## Contributors

- **Reut Lev** (reutlev98)
- **Ye'ela Granot** (yeela8g)
