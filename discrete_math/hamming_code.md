<!-- File: discrete_math/hamming_code.md -->

# Hamming Code

---

## Overview

The **Hamming code** is a family of linear error-correcting codes that detect and correct single-bit errors.  
It is a type of **block code** characterized by parameters $[n, k]$, where:

- $n$ is the total number of bits in the codeword.
- $k$ is the number of **data bits**.
- $r = n - k$ is the number of **redundancy bits** (also called **parity bits**).

Hamming codes are a subset of **binary linear codes** and can be expressed using **generator** and **parity-check** matrices.

---

## Generator and Parity-Check Matrices

A **generator matrix** $\mathbf{G}$ and a **parity-check matrix** $\mathbf{H}$ define the encoding and validation rules for Hamming codes.

Let:

- $k$: number of information bits
- $r$: number of parity bits
- $n = k + r$

Then we can construct the matrices:

### Generator matrix $\mathbf{G}$

$$
\mathbf{G} = \left( I_k \mid P^T \right)
$$

- $I_k$: $k \times k$ identity matrix
- $P^T$: transpose of the $r \times k$ matrix $P$

### Parity-check matrix $\mathbf{H}$

$$
\mathbf{H} = \left( P \mid I_r \right)
$$

- $I_r$: $r \times r$ identity matrix
- $P$: $r \times k$ matrix derived from the structure of the code

> **Note:** In general, for linear codes over a field:
>
> - Generator matrix:    $\mathbf{G} = \left( I_k \mid -P^T \right)$  
> - Parity-check matrix:  $\mathbf{H} = \left( P \mid I_r \right)$  
>
> However, for **Hamming codes over binary (mod 2)**, we have $-1 \equiv 1 \pmod{2}$, so:
>
> - $\mathbf{G} = \left( I_k \mid P^T \right)$  
> - $\mathbf{H} = \left( P \mid I_r \right)$  
>
> As you can see, the **right matrix of $\mathbf{H}$** is simply the **transpose** of the right matrix in $\mathbf{G}$.

---

## Structure of $\mathbf{H}$

In the standard construction of Hamming codes:

- The **columns** of $\mathbf{H}$ are all the nonzero binary vectors of length $r = n - k$.
- These vectors can be arranged in **any order** in the columns of $\mathbf{H}$.
- The right-hand side of $\mathbf{H}$ is typically chosen to be the $r \times r$ identity matrix $I_r$.

Thus, $\mathbf{H}$ can be viewed as:

$$
\mathbf{H} = \left( P \mid I_r \right)
$$

where $P$ contains the remaining columns (i.e., those corresponding to the $k$ data bits), and these can be **any permutation** of the $r$-bit nonzero vectors not used in $I_r$.

Once this form of $\mathbf{H}$ is established, $\mathbf{G} = \left( I_k \mid P^T \right)$ follows.

---

## Syndrome and Error Detection

Given a received codeword (possibly with errors) represented as a vector $\mathbf{y}$, the **syndrome** $\mathbf{s}$ is calculated using the parity-check matrix $\mathbf{H}$ as:

$$
\mathbf{s} = \mathbf{H} \cdot \mathbf{y}^T
$$

- All operations are done **modulo 2**.
- If $\mathbf{s} = \mathbf{0}$ (the zero vector), then $\mathbf{y}$ is a valid codeword with **no detected errors**.
- If $\mathbf{s} \neq \mathbf{0}$, the syndrome $\mathbf{s}$ corresponds to the binary representation of the position of the erroneous bit in the codeword.
- This allows **single-bit error detection and correction** by identifying which bit to flip.

> **Example:** For a Hamming [7,4] code, $\mathbf{s}$ will be a 3-bit column vector that points to the position (1 to 7) of the error in $\mathbf{y}$.

---

## Example: Hamming Code [7, 4]

Here is a concrete example of a Hamming code with $n = 7$, $k = 4$, and $r = 3$:

### Generator Matrix $\mathbf{G}$

$$
\mathbf{G} =
\begin{bmatrix}
1 & 0 & 0 & 0 & 0 & 1 & 1 \\
0 & 1 & 0 & 0 & 1 & 0 & 1 \\
0 & 0 & 1 & 0 & 1 & 1 & 0 \\
0 & 0 & 0 & 1 & 1 & 1 & 1 \\
\end{bmatrix}
$$

### Parity-Check Matrix $\mathbf{H}$

$$
\mathbf{H} =
\begin{bmatrix}
0 & 1 & 1 & 1 & 1 & 0 & 0 \\
1 & 0 & 1 & 1 & 0 & 1 & 0 \\
1 & 1 & 0 & 1 & 0 & 0 & 1 \\
\end{bmatrix}
$$

Note how:

- $\mathbf{G} = \left( I_4 \mid P^T \right)$
- $\mathbf{H} = \left( P \mid I_3 \right)$
- $\mathbf{G} \cdot \mathbf{H}^T = 0$
- All arithmetic is done **modulo 2**

These matrices define a valid $[7,4]$ binary Hamming code capable of correcting all single-bit errors.
