### Description of the Code

This project is designed for DNA sequence analysis, specifically for searching a DNA pattern in a given DNA sequence using the **Knuth-Morris-Pratt (KMP) string matching algorithm**. Additionally, it provides functionality to display the matches in **highlighted colors** when run in IDLE.

#### Main Components and Features:

1. **IDLE Color Highlighting**:
   - The script allows for custom syntax coloring for various elements when executed in Python's IDLE environment. It maps specific color names to IDLE's predefined highlighting tags.
   - Colors are defined in the `colormap` dictionary.
   - The `printc()` function handles formatted and colorized printing.

2. **KMP Algorithm Functions**:
   - The KMP algorithm is efficient for searching substrings in a larger text with precomputed prefix-suffix data (stored in the `lps` array).
   - `lpsArray()` computes the Longest Prefix Suffix (LPS) array for the pattern to skip unnecessary comparisons during the search.
   - `Search()` performs the actual pattern search in the DNA sequence using the `lps` array.

3. **DNA Sequence and Pattern Search**:
   - The DNA sequence is read from a file named `sequence.txt`.
   - The script searches for a hardcoded pattern (`CAGT`) in the sequence using the KMP algorithm.
   - If matches are found:
     - Their total count is displayed.
     - The DNA sequence is printed with matches highlighted (in orange) and the rest in black.
   - If no matches are found, it outputs an appropriate message.

4. **Custom Text Highlighting**:
   - Text matching the pattern is highlighted using the `orange()` function, which formats the text for color printing.

#### Key Functions:
- **`lpsArray(pat, pat_len, lps)`**:
  - Builds the LPS array for the given pattern to optimize the search process.
- **`Search(pat, txt, lps)`**:
  - Uses the LPS array to efficiently locate occurrences of the pattern in the DNA sequence and print the results with highlights.
- **`printc(text, end="\n")`**:
  - Prints text with IDLE highlighting. Handles `{text:color}` formatted input and interprets it according to the `colormap`.

#### Input/Output:
- **Input**:
  - DNA sequence file (`sequence.txt`) containing a string of nucleotides (e.g., `AGTCAGT...`).
  - Pattern to be searched, hardcoded as `"CAGT"`.
- **Output**:
  - Found pattern indices and total matches.
  - Color-highlighted DNA sequence (if matches exist) displayed in IDLE.

#### Workflow:
1. The script initializes the colormap and defines helper functions for colorized output.
2. The DNA sequence is read from the file `sequence.txt`.
3. The `lpsArray()` function precomputes the LPS array for the pattern.
4. The `Search()` function:
   - Locates matches of the pattern in the sequence.
   - Counts and highlights matches.
   - Prints the results with appropriate messages for success or failure.

#### Example Output:
If the DNA sequence in `sequence.txt` is:
```
ACGTACGTCAGTACGT
```
And the pattern is `"CAGT"`, the output might be:
```
Found pattern at index 6
Total number of pattern matches = 1
ACGTACGT{CAGT:orange}ACGT
```
If no matches exist:
```
Pattern is not found in DNA sequences
```

#### Limitations:
- Works only in IDLE due to the use of IDLE-specific highlighting features.
- The pattern is currently hardcoded, but can be modified to accept user input or read from a file.
