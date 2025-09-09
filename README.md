# CQRRPT: CholeskyQR with Randomization and Pivoting for Tall Matrices

This repository contains the project files for:

**"CholeskyQR with Randomization and Pivoting for Tall Matrices (CQRRPT)"**  

The project explores and implements algorithm for QR decomposition with column pivoting, specifically designed for **tall matrices** where the number of rows is much larger than the number of columns ( *m ≫ n* ).

---

## 📜 Overview
QR factorization is a fundamental tool in numerical linear algebra, but traditional methods with column pivoting (QRCP) can be computationally expensive and slow, often requiring **twice the operations** of unpivoted QR.  

This project implements and analyzes **CQRRPT**, an algorithm that leverages **randomized sketching** to accelerate the process while preserving the crucial **rank-revealing properties** of QRCP.

The core idea is:
1. Compress the large input matrix into a smaller **sketch**.  
2. Perform the expensive pivoting on this small sketch.  
3. Use the results to guide an efficient factorization on the original matrix.  

---

## ✨ Key Features
- **High Performance**: Achieves speeds close to unpivoted QR, offering significant speedups over traditional QRCP routines like LAPACK’s `GEQP3`.  
- **Rank-Revealing**: Effectively identifies the numerical rank of a matrix by inheriting the strong rank-revealing properties from the pivoted sketch.  
- **Numerical Stability**: Uses a preconditioning step to ensure the stability of CholeskyQR, even for ill-conditioned matrices.  
- **Scalability**: Communication-efficient, making it well-suited for very large matrices and distributed systems.  

---

## 📂 Repository Contents
This repository contains three main components:

### 1. **`LAA Project.ipynb`**
A Jupyter Notebook with the Python implementation of the CQRRPT algorithm and its components. It includes:
- Functions for different sketching methods (Gaussian, SASO, SRFT).  
- A performance comparison to time the different approaches.  
- A demonstration of how standard CholeskyQR can fail on ill-conditioned matrices where CQRRPT succeeds.  

### 2. **`LAA Report.pdf`**
A detailed academic report covering:
- Mathematical background  
- Algorithm justification  
- Complexity analysis  
- Experimental results  
- Applications  
