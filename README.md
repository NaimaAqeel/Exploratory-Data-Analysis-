

#  Restaurant Data Cleaning (Python + Pandas)

This project focuses on cleaning a raw dataset of restaurant information. The dataset contains issues like duplicates, missing values, and unstandardized time formats (e.g., `8:30am – 10:30pm`, `12Midnight`, `12Noon`). Using **Python** and **Pandas**, the data was cleaned and transformed into a structured format for easier analysis.

---

##  Steps Performed

### 1. Data Loading

* Imported dataset into **Pandas DataFrame**.
* Displayed first few rows to understand structure.

### 2. Duplicate & Missing Values

* Identified duplicate rows using `df.duplicated().sum()`.
* Removed duplicates with `df.drop_duplicates()`.
* Checked missing values with `df.isnull().sum()`.

### 3. Cleaning Timings Column

* Original `timings` column had inconsistent formats:

  * Mix of **AM/PM** cases (`8:30am`, `9:30 AM`).
  * Special words like `Midnight`, `Noon`.
  * Multiple time ranges in one string.

* Applied the following transformations:

  * Replaced `Midnight` → `12:00 AM`, `Noon` → `12:00 PM`.
  * Extracted time ranges using **regex**.
  * Converted extracted times into `datetime.time` format.

### 4. Extracting Opening & Closing Times

* Split timings into **two separate columns**:

  * `opening_time`
  * `closing_time`

Example transformation:

| Raw Timings                  | Opening Time | Closing Time |
| ---------------------------- | ------------ | ------------ |
| `8:30am – 10:30pm (Mon-Sun)` | 08:30:00     | 22:30:00     |
| `12:30PM to 12Midnight`      | 12:30:00     | 00:00:00     |
| `9:30 AM to 11 PM`           | 09:30:00     | 23:00:00     |

---

##  Tech Stack

* **Python 3**
* **Pandas**
* **Regex**
* **Jupyter Notebook / Colab**

---

##  How to Run

1. Clone this repository:

   ```bash
   git clone https://github.com/your-username/restaurant-data-cleaning.git
   cd restaurant-data-cleaning
   ```

2. Install required libraries:

   ```bash
   pip install pandas
   ```

3. Open the Jupyter Notebook:

   ```bash
   jupyter notebook
   ```

   or run on **Google Colab**.

---

## Results

* Clean dataset without duplicates and missing values.
* Standardized timings with clear **opening** and **closing** times.
* Ready for further analysis (e.g., busiest hours, average operating hours).

---


 This project demonstrates **data cleaning, preprocessing, and time normalization techniques**.

---

