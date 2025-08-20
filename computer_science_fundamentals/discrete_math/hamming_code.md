<!-- File: discrete_math/hamming_code.md -->

# 🧩 Hamming Codes — Notes

---

## Overview

The **Hamming code** is a family of linear error-correcting codes that detect and correct single-bit errors.  
It is a type of **block code** characterized by parameters:

$$
[n, k]
$$

where:

- $n$ = total number of bits in the codeword  
- $k$ = number of **data bits**  
- $r = n - k$ = number of **redundancy (parity) bits**

Hamming codes are a subset of **binary linear codes** and can be expressed using **generator** and **parity-check** matrices.

---

## Generator and Parity-Check Matrices

A **generator matrix** $\mathbf{G}$ and a **parity-check matrix** $\mathbf{H}$ define encoding and validation rules.

Let $k$ = number of information bits, $r$ = number of parity bits, and $n = k + r$. Then:

### Generator matrix

$$
\mathbf{G} = \left( I_k \;\middle|\; -P^T \right)
$$

- $I_k$: $k \times k$ identity matrix  
- $-P^T$: transpose of the $r \times k$ matrix $P$ (over a general field)

### Parity-check matrix

$$
\mathbf{H} = \left( P \;\middle|\; I_r \right)
$$

- $I_r$: $r \times r$ identity matrix  
- $P$: $r \times k$ matrix derived from the code

> **Note (general vs. binary):**  
> Over a general field:
>
> $$
> \mathbf{G} = \left( I_k \;\middle|\; -P^T \right), \qquad
> \mathbf{H} = \left( P \;\middle|\; I_r \right)
> $$
>
> For binary codes (mod 2), $-1 \equiv 1 \pmod{2}$, so:
>
> $$
> \mathbf{G} = \left( I_k \;\middle|\; P^T \right), \qquad
> \mathbf{H} = \left( P \;\middle|\; I_r \right)
> $$
>
> In other words, the left block of $\mathbf{H}$ equals the transpose of the right block of $\mathbf{G}$ (up to sign).

---

## Properties of Systematic Codes

- In **systematic form**, **data bits** always appear at the **beginning** of the codeword.  
- Redundancy bits (parity) follow.  
- Matrix structure guarantees:
  - $\mathbf{H} \cdot \mathbf{G}^T = 0$  
  - Left block of $\mathbf{H}$ = transpose of right block of $\mathbf{G}$ (up to sign)

---

## Structure of $\mathbf{H}$

- Columns of $\mathbf{H}$ are all nonzero binary vectors of length $r = n-k$  
- Each vector appears exactly once  
- Right-hand block of $\mathbf{H}$ is usually the identity $I_r$  

Thus:

$$
\mathbf{H} = \left( P \;\middle|\; I_r \right)
$$

Corresponding generator matrix:

$$
\mathbf{G} = \left( I_k \;\middle|\; -P^T \right) \quad \text{(general)}, \qquad
\mathbf{G} = \left( I_k \;\middle|\; P^T \right) \quad \text{(binary)}
$$

---

## Syndrome and Error Detection

Given a received codeword $\mathbf{y}$, the **syndrome** $\mathbf{s}$ is:

$$
\mathbf{s} = \mathbf{H} \mathbf{y}^T
$$

- All arithmetic modulo 2 (binary codes)  
- If $\mathbf{s} = \mathbf{0}$ → no errors detected  
- If $\mathbf{s} \neq \mathbf{0}$ → the syndrome corresponds to the **column of $\mathbf{H}$ of the error bit**  

> 🔑 Safe rule: *syndrome = column of $\mathbf{H}$ corresponding to the error bit*.  
> “Binary index shortcut” works only for specific column orderings.

---

## Example: Hamming Code [7,4]

Take $n = 7$, $k = 4$, $r = 3$

### Generator Matrix

$$
\mathbf{G} =
\begin{bmatrix}
1 & 0 & 0 & 0 & 0 & 1 & 1 \\
0 & 1 & 0 & 0 & 1 & 0 & 1 \\
0 & 0 & 1 & 0 & 1 & 1 & 0 \\
0 & 0 & 0 & 1 & 1 & 1 & 1 \\
\end{bmatrix}
$$

### Parity-Check Matrix

$$
\mathbf{H} =
\begin{bmatrix}
0 & 1 & 1 & 1 & 1 & 0 & 0 \\
1 & 0 & 1 & 1 & 0 & 1 & 0 \\
1 & 1 & 0 & 1 & 0 & 0 & 1 \\
\end{bmatrix}
$$

- $\mathbf{G} = (I_4 \mid P^T)$  
- $\mathbf{H} = (P \mid I_3)$  
- $\mathbf{G}\mathbf{H}^T = 0$  
- Corrects all single-bit errors

---

## Worked Example: Decoding with Multiple Errors (Systematic Hamming [7,4])

Given $\mathbf{H}$:

$$
\mathbf{H} =
\begin{pmatrix}
1 & 1 & 0 & * & * & * & * \\
0 & 1 & 1 & * & * & * & * \\
1 & 0 & 1 & * & * & * & *
\end{pmatrix} = \begin{pmatrix}-P^T & I_r\end{pmatrix}, \quad r=3, n=7, k=4
$$

A codeword $\mathbf{y} = 0000000$ is transmitted; errors occur at positions 2,3,4,5.  

### 1) Complete $\mathbf{H}$

All columns of $\mathbf{H}$ are nonzero 3-bit vectors:

$$
\mathbf{H} = 
\begin{bmatrix}
1 & 1 & 0 & 1 & 1 & 0 & 0 \\
0 & 1 & 1 & 1 & 0 & 1 & 0 \\
1 & 0 & 1 & 1 & 0 & 0 & 1
\end{bmatrix}
$$

### 2) Syndrome

Received vector:

$$
\mathbf{y}_{\text{recv}} = 0\,1\,1\,1\,1\,0\,0
$$

Syndrome via matrix-vector multiplication:

$$
\mathbf{s} = \mathbf{H} \cdot \mathbf{y}_{\text{recv}}^T
=
\begin{bmatrix} 1 & 1 & 0 & 1 & 1 & 0 & 0 \\ 1 & 0 & 1 & 1 & 0 & 1 & 0 \\ 1 & 1 & 0 & 1 & 0 & 0 & 1 \end{bmatrix}
\cdot
\begin{bmatrix} 0 \\ 1 \\ 1 \\ 1 \\ 1 \\ 0 \\ 0 \end{bmatrix}
=
\begin{bmatrix} 1 \\ 1 \\ 0 \end{bmatrix}
$$

Matches column 2 → decoder assumes **single error at position 2**.

### 3) Apply Decoder

Flip bit 2:

$$
\mathbf{y}' = 0\,0\,1\,1\,1\,0\,0
$$

Systematic code → decoded message = first 4 bits:

$$
\hat{\mathbf{u}} = 0\,0\,1\,1
$$

### 4) Remark

- Hamming [7,4] corrects only **1 error**  
- With 4 errors, decoder outputs **wrong message**  
- Illustrates: 

$$
\text{syndrome} = \text{column of $\mathbf{H}$ corresponding to error}
$$
