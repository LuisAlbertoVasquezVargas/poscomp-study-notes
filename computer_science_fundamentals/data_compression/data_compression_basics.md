<!-- File: computer_science_fundamentals/data_compression/data_compression_basics.md -->

# Data Compression Basics

## 1. Overview

Data compression aims to reduce the size of data representation while preserving the ability to reconstruct the original (lossless) or an acceptable approximation (lossy).

---

## 2. Types of Compression

### 2.1 Lossless Compression
- **Definition**: The original data can be perfectly reconstructed.
- **Examples**: Huffman coding, Lempel–Ziv–Welch (LZW), Arithmetic coding, Run-Length Encoding (RLE).
- **Use cases**: Text files, executable programs, source code, some image formats (PNG).

### 2.2 Lossy Compression
- **Definition**: Some information is lost, aiming for higher compression ratios while keeping perceptual quality.
- **Examples**: JPEG (images), MP3 (audio), MPEG (video).
- **Use cases**: Multimedia where exact reproduction is unnecessary.

---

## 3. Huffman Coding

- **Variable-length coding**: Assigns **shorter codes** to more frequent symbols and **longer codes** to less frequent ones.
- **Prefix-free codes**: No code is a prefix of another — ensures unambiguous decoding.
- **Optimality**: Produces the shortest average code length for a given set of symbol probabilities (when probabilities are powers of 1/2).

---

## 4. Run-Length Encoding (RLE)

- **Idea**: Replace sequences of the same value (runs) with a count and the value itself.
- **Example**:  
  Input: `AAAAABBBCCDAA`  
  Output: `(5,A) (3,B) (2,C) (1,D) (2,A)`
- **Advantages**:
  - Very simple to implement.
  - Efficient when data contains many long runs (e.g., bitmap images with large uniform areas).
- **Disadvantages**:
  - Inefficient for highly variable data (might even increase size).
- **Use cases**: Fax machines, simple image compression, early graphics formats.

---

## 5. Kraft Inequality

- **Statement**: For a prefix-free code with codeword lengths `l₁, l₂, ..., lₙ`:

```

Σ ( 1 / 2^(lᵢ) ) ≤ 1

```

- **Interpretation**: Provides a necessary and sufficient condition for the existence of a prefix-free code with given code lengths.
- **Exam tip**: If the sum exceeds 1, such a code cannot exist.

---

## 6. Fixed-Length vs Variable-Length Coding

| Coding Type   | Codeword Length          | Efficiency |
|---------------|--------------------------|------------|
| Fixed-length  | All symbols have same length | Simple but less efficient when probabilities vary |
| Variable-length | Length depends on frequency | More efficient — shorter for frequent symbols |

---
