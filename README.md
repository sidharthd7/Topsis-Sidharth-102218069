```markdown
# TOPSIS-Sidharth-102218069

## Overview

This package implements the TOPSIS (Technique for Order of Preference by Similarity to Ideal Solution) method for multi-criteria decision-making. The method ranks alternatives based on their relative closeness to the ideal solution.

## Installation

To install the package, navigate to the root directory of the project (where `setup.py` is located) and run the following command:

```bash
pip install .
```

This will install the package locally.

## Usage

You can use this package from the command line to calculate TOPSIS scores and rankings for a given dataset.

### Command Line

```bash
topsis <InputDataFile> <Weights> <Impacts> <ResultFileName>
```

### Example

```bash
topsis 102218069-data.csv "1,1,1,2" "+,+,-,+" 102218069-result.csv
```

### Parameters

- `<InputDataFile>`: Path to the input CSV file containing the data.
- `<Weights>`: Comma-separated weights for each criterion.
- `<Impacts>`: Comma-separated impacts for each criterion, where each impact is either `+` (beneficial) or `-` (non-beneficial).
- `<ResultFileName>`: The name of the output CSV file where the results will be saved.

### Sample Input File Format

The input CSV file should have the following structure:

| Fund Name | P1  | P2  | P3  | P4  | P5  |
|-----------|-----|-----|-----|-----|-----|
| M1        | 0.84| 0.71| 6.7 | 42.1| 12.59|
| M2        | 0.91| 0.83| 7.0 | 31.7| 10.11|
| ...       | ... | ... | ... | ... | ... |

### Sample Output File Format

The output CSV file will have the following structure:

| Fund Name | P1  | P2  | P3  | P4  | P5  | Topsis Score | Rank |
|-----------|-----|-----|-----|-----|-----|--------------|------|
| M1        | 0.84| 0.71| 6.7 | 42.1| 12.59| 0.3653       | 6    |
| M2        | 0.91| 0.83| 7.0 | 31.7| 10.11| 0.2819       | 8    |
| ...       | ... | ... | ... | ... | ...  | ...          | ...  |

## Error Handling

The program will raise an error and terminate if:

- The input file is not found.
- The number of weights and impacts does not match the number of criteria.
- Impacts contain values other than `+` or `-`.
- Weights are not numeric.

## Dependencies

- `pandas`
- `numpy`

These dependencies are automatically installed when you install the package.

## Author

Sidharth Dhawan

## License

This project is licensed under the MIT License.
```
