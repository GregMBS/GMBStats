# GMBSTATS.BAS - Statistics Program (1986)

A comprehensive statistical analysis program written in GW-BASIC by Gregory M. Blumenthal in 1986.

## Overview

GMBSTATS is a text-based statistics calculator providing a full menu of statistical analyses for paired and unpaired data. Originally designed for IBM PC compatibles running GW-BASIC.

## Features

### Data Types
- **Paired Data**: For correlated measurements (X, Y pairs)
- **Unpaired Data**: For independent samples in columnar format
- **Summary Statistics**: For pre-calculated group data

### Statistical Analyses

1. **Mean, Standard Deviation, and Standard Error of the Mean**
2. **Student's t-Test** (paired and unpaired)
3. **Chi-Square Test** (with and without Yates' correction)
4. **Analysis of Variance (ANOVA)** (one-way and two-way)
5. **Third-Order Polynomial Regression**
6. **Linear Regression and Pearson's R**
7. **Spearman's Rho** (rank correlation)
8. **Curvilinear Correlation (eta)**
9. **Error Function Calculation** (standard normal probability)
10. **Data Set Listing** (review entered data)
11. **New Data Set** (reset and start over)
12. **Exit Program**

## Running the Program

### Using GW-BASIC

```
BASIC GMBSTATS
```

or from within BASIC:

```
LOAD "STATS"
RUN
```

### Using a Modern BASIC Interpreter

You can run this on modern systems using emulators or BASIC interpreters that support GW-BASIC syntax.

## Usage Guide

### Step 1: Select Data Type

When the program starts, choose:
- `1` for Paired data
- `2` for Unpaired (columnar) data  
- `3` for Other (summary statistics)

### Step 2: Enter Your Data

**For Paired Data:**
- Specify number of pairs
- Enter X and Y values for each pair
- Verify corrections are needed before continuing

**For Unpaired Data:**
- Specify number of sets and subsets per set
- Enter data for each set/subset
- Press Enter to move to next subset

**For Other Data:**
- Enter n (sample size), mean, and standard deviation for each set

### Step 3: Perform Analyses

After data entry, the main menu appears with 12 analysis options. Select by entering the corresponding number.

### Step 4: Review Results

Results appear on screen. Press SPACE to continue.

## Important Notes

### Data Entry
- **No Error Correction After Entry**: If you make a mistake during data entry, you must restart. Stop entering data and press Enter until you reach the main menu. Select "New Data Set" to start over.
- **Batch Entry**: The program enters data in batches with verification prompts
- **Overflow Messages**: If you see "Overflow" or "Division by zero" during erroneous entry, ignore these—restart the data entry

### Analysis Limitations
- Some tests require specific data types (see analysis descriptions above)
- Chi-square, Pearson's R, linear regression, and Spearman's Rho require paired data
- ANOVA and curvilinear correlation require unpaired (columnar) data
- T-test with unpaired data requires you to specify which sets to compare

### Post-Hoc Tests
- After ANOVA, the program optionally offers Scheffe and Student Newman-Keuls tests
- These are available for identifying specific group differences

## Program Structure (BASIC Code)

The program is organized into logical sections:

- **Lines 1-150**: Menu and main program loop
- **Lines 500-2100**: Data input subroutines
- **Lines 3000-12000**: Statistical analysis subroutines
- **Line 7000+**: Complex calculations (regression, ANOVA, etc.)

## Historical Context

This program was developed in the early microcomputer era when computing resources were limited. The algorithms use:
- Minimal memory footprint
- Efficient numerical methods suitable for hand calculation verification
- Clear, educational approaches to statistical formulas

## File Reference

- `STATS.BAS` - The main program source code
- `STATS.TXT` - Original program instructions
- `XREF.BAS` - Cross-reference file (documentation)

## Algorithm Notes

- **Rounding**: Uses BASIC's FNA function to round to 4 decimal places (INT(X*10000+0.5)/10000)
- **Degrees of Freedom**: Calculated according to statistical conventions (N-1 for sample SD, etc.)
- **Correlation Coefficient**: Pearson's R using sum of products of deviations
- **Polynomial Regression**: Solves 4x4 system via Gaussian elimination
- **ANOVA**: Supports balanced and unbalanced designs with post-hoc comparisons

## Known Limitations

- Interactive data entry only (no file I/O for data import)
- Limited screen real estate for output formatting
- No graphics support
- Input validation is minimal by modern standards

## Modern Usage

For analysis on contemporary systems, consider:
- The JavaScript port (`gmbstats.js`) for Node.js CLI use
- The web version for browser-based access
- Modern statistical software (R, Python, SPSS) for production use

This BASIC version is preserved for educational and historical interest in retro computing and statistics education.

---

**Author**: Gregory M. Blumenthal (1986)
