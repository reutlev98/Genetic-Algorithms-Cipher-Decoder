# Genetic Algorithm - Monoalphabetic Cipher Breaker

## Overview

This repository contains a project dedicated to breaking monoalphabetic ciphers using advanced genetic algorithms. By employing evolutionary techniques, the project aims to decode encrypted text through an iterative optimization process that identifies the best possible decryption key.

## About This Project

This project was developed as part of the **Bioinformatics course** at **Bar-Ilan University** during the 2023 academic year. It serves as a practical demonstration of key programming techniques such as **multithreading**, **algorithm optimization**, and **simulation of evolutionary processes**.

## Contributors

- **Reut Lev** ([reutlev98](https://github.com/reutlev98))
- **Ye'ela Granot** ([yeela8g](https://github.com/yeela8g))

## Introduction

The project includes three variations of genetic algorithms:
- **Standard Genetic Algorithm**: Implements a classic genetic algorithm approach for text decryption.
- **Darwinian Genetic Algorithm**: Simulates natural selection where only the fittest solutions propagate.
- **Lamarckian Genetic Algorithm**: Incorporates local optimization to improve solutions before passing them to the next generation.

Each variation provides a unique strategy for deciphering the encrypted message, leveraging principles of natural evolution and optimization.

## Input and Output Files

### Input Files:
- `enc.txt`: The file containing the encrypted text to be decoded.
- `dict.txt`: A dictionary file used for comparing decrypted words during fitness evaluation.
- `Letter_Freq.txt`: Contains the expected frequency distribution of letters in the English language.

### Output Files:
- `plain.txt`: Outputs the decrypted message.
- `perm.txt`: Saves the permutation table that was used for decoding the encrypted text.

## How to Run

You can run the program using one of the following methods:

### Option 1: Using the Executable

1. Download and extract the `main.zip` file.
2. Navigate to the extracted directory and double-click `main.exe`.
3. Follow the prompt to select the desired algorithm variant:
   - `1` for the Standard Genetic Algorithm.
   - `2` for the Darwinian Genetic Algorithm.
   - `3` for the Lamarckian Genetic Algorithm.
4. Wait for the computation to complete.
5. The results will be written to `plain.txt` and `perm.txt` in the same directory.

### Option 2: Running the Python Script

1. Place the input files (`enc.txt`, `dict.txt`, `Letter_Freq.txt`) in the same directory as the Python script.
2. Execute the Python script using your Python environment:
   ```bash
   python decryptor.py
   ```
3. Follow the prompts to select the algorithm variant and input required parameters.

## Algorithmic Approach

The genetic algorithms implemented in this project decode the encrypted text by evolving a **population** of potential decryption keys, each represented as a **permutation of the English alphabet**. The evolutionary process includes the following stages:

- **Population Initialization**: A population of 1000 random permutations is generated, each representing a potential decoding key.
- **Selection**: A subset of the population is selected based on their **fitness score**, which measures how well they decode the text.
- **Crossover**: Pairs of selected solutions are combined to produce new offspring, inheriting traits from both parents.
- **Mutation**: Random alterations are introduced to the offspring to maintain genetic diversity.
- **Elitism**: The best-performing solutions are preserved to ensure they survive into the next generation.
- **Diversification**: Additional mutations are applied if the population's fitness plateaus, to prevent stagnation.

### Fitness Function

The fitness of each solution is evaluated by comparing the decrypted output against the dictionary (`dict.txt`) and analyzing the similarity between the decrypted letter frequencies and those in `Letter_Freq.txt`. Higher fitness scores correspond to solutions that produce readable decrypted text.

## Lamarckian vs. Darwinian Evolution

- **Lamarckian Approach**: Solutions undergo local optimization before being passed to the next generation, allowing improved adaptations to be directly inherited.
- **Darwinian Approach**: Solutions are evaluated as-is, with optimizations only influencing fitness but not being inherited. This maintains closer adherence to natural evolutionary processes.

## Summary

This project highlights the capabilities of genetic algorithms for tackling cryptographic challenges, providing a sophisticated approach to solving monoalphabetic ciphers. The adaptive nature of the genetic algorithm allows it to explore a wide solution space efficiently, offering valuable insights into the power of evolutionary computation.
