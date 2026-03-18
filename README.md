# Fine-tuning-data-XYQX Database Description

This repository stores data related to acoustic valley Hall insulators, as well as datasets used for large language model fine-tuning and testing.

## 1. Overall Database Structure

- `filter_rata_0_3` to `filter_rata_2_2`:
  - Raw and filtered data organized by different lattice constants (e.g., 15.588 mm, 20.785 mm, ..., 114.315 mm).
- `all_filter_sim_str` to `all_filter_com_flot`:
  - Aggregated directories for filtered data across all lattice constants.
- `Training and test datasets`:
  - Datasets used for Designer-LLM fine-tuning and evaluation.

## 2. Description of Lattice-Constant Directories (`filter_rata_x_x`)

Each `filter_rata_x_x` directory contains the following types of files.

### 2.1 Initial Data Files (Unfiltered)

- `TI_data_com_flot_xxx.json`
- `TI_data_com_str_xxx.json`
- `TI_data_sim_flot_xxx.json`
- `TI_data_sim_str_xxx.json`

Definitions:

- `flot`: Data stored in floating-point format.
- `str`: Data stored in string format.
- `com`: Complete coordinate points of the acoustic valley Hall insulator structure.
- `sim`: One-sixth coordinates.

### 2.2 Filtering Script

- `filter-data-num.py`

Purpose:

- Filters the initial data and generates filtered JSON files.

### 2.3 Filtered Output Files

Examples:

- `filter_data_com_flot_0_3.json`
- `filter_data_com_str_0_3.json`
- `filter_data_sim_flot_0_3.json`
- `filter_data_sim_str_0_3.json`
- `filtered_indices_0_3.json`

Note:

- The suffix changes according to the lattice-constant directory (e.g., `_0_4`, `_1_0`, `_2_2`).

## 3. Aggregation Directories

- `all_filter_sim_str`
- `all_filter_sim_flot`
- `all_filter_com_str`
- `all_filter_com_flot`

Purpose:

- Aggregate filtered data across lattice constants by storage format (`str`/`flot`) and coordinate type (`sim`/`com`).

## 4. Training and Test Datasets

Directory: `Training and test datasets`

- `XYQX-Train.json`: Instruction dataset for Designer-LLM fine-tuning.
- `XYQX-test.json`: Test dataset.

## 5. Naming Convention Quick Reference

- `TI_data_*`: Initial data.
- `filter_data_*`: Filtered data.
- `filtered_indices_*`: Retained/corresponding indices generated during filtering.
- `com` / `sim`: Complete coordinates / one-sixth coordinates.
- `flot` / `str`: Floating-point storage / string storage.

## 6. Usage Suggestions

1. Enter the target `filter_rata_x_x` directory according to the desired lattice constant.
2. Confirm the required data type first: `com` or `sim`, `flot` or `str`.
3. To reproduce the filtering process, run `filter-data-num.py` in that directory.
4. For fully aggregated filtered data, use the `all_filter_*` directories.
5. For model training/testing, use the datasets in `Training and test datasets`.
