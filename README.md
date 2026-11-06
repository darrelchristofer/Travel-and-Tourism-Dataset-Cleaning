# Travel and Tourism Full Dataset Cleaning

A full Data Cleaning Project from a three table data about travel and tourism

---
## 📌 Main Objective

Our main goal and objective of doing this project is based on the phrase where Data Analyst spends around 80% of their time in Cleaning the Data.
After knowing about that information, with the use of AI, we are building a fictional dataset where we can explore mistakes in data and clean it.
On this dataset, we ask the AI to make a messy dataset where we can clean almost every kind of mistakes in data so that we can learn how to deal with messy data in real-work projects.

---
### The Data Understanding Part

Problems found in this dataset:

| Problem type | Examples found in the raw data |
|---|---|
| Structural junk | Title lines above the header, the header repeated mid-file, empty rows, a "Total records" footer |
| Duplicates | Exact duplicate rows, near-duplicate bookings with a new ID, the same person under two customer IDs, the same hotel listed twice |
| Missing values | Many placeholders: `NULL`, `N/A`, `-`, `?`, `unknown`, `#N/A`, blank spaces |
| Inconsistent IDs | `C000123`, `c000123`, `C-000123`, `123`, `C123` for the same customer |
| Mixed formats | 10 date formats, phone numbers with and without country code, amounts like `Rp 1.250.000,-`, `$1,250.50` and `250,50` |
| Inconsistent categories | 48 spellings for 9 sales channels, 23 spellings for 5 booking statuses, country names like `ID`, `INA`, `Indo` |
| Invalid values | Future birth dates, check-out before check-in, 0 or 99 guests, star ratings of 7, ratings of 8 on a 1-5 scale |
| Wrong units and outliers | IDR amounts tagged as USD, prices with extra zeros (×10, ×100), latitude and longitude swapped |
| Messy text | HTML tags, broken characters (`HÃ´tel`), emojis, `Last, First` names, titles like `Mr.` and `Bapak` |
| Hidden patterns | Booking.com writes dates month-first (MM/DD/YYYY) while all other channels write day-first; some timestamps are in UTC and others in local time (WIB) |


---
### The Data Cleaning Part

**Tools:** Python, pandas, NumPy, Jupyter Notebook (VS Code)
 
The cleaning follows the order of the notebook:
 
1. **Import and profile the data:** view heads, shapes, columns, unique values, missing values and duplicates for each table.
2. **Build reusable helpers:** working copies so the raw data stays untouched, a cleaning log, and helper functions for text, labels, dates, money, numbers, IDs and casing, plus mapping dictionaries for every messy category.
3. **Clean the customers table:** remove junk rows, test records and duplicates; standardize IDs, names, emails, phones, dates, gender, nationality, loyalty tier, income, language and city; then merge people registered twice using a rule where at least 2 of 3 identifiers (email, phone, date of birth) must match.
4. **Clean the properties table:** standardize IDs, names, types, cities, regions and countries; parse star ratings, prices, amenities, coordinates, check-in times and scores; fix price outliers and wrong coordinates; remove duplicate listings.
5. **Clean the bookings table:** standardize IDs and link them to the clean customers and properties; map all categories; parse dates using each channel's date order; fix swapped dates, wrong currencies, outliers and logical conflicts; impute missing amounts; remove near-duplicate bookings; add derived columns.
6. **Validate and save:** run 16 validation rules, compare business results before and after cleaning, and save the clean tables, ID maps and cleaning log.
Every cleaning step is recorded in `cleaned/cleaning_log.csv` (77 logged steps), with the table, column, action and number of rows affected.

---
### Key Insights

| Business question | Raw data (naive) | Clean data |
|---|---:|---:|
| Number of bookings | 12,435 | 12,000 |
| Unique customers | 3,707 | 2,802 |
| Sales channels | 48 labels | 9 channels (+ Unknown) |
| Cancellation rate | 9.31% | 13.36% |
| Completed revenue (USD) | 9,744,690,051 | 3,867,041 |
| Average completed booking (USD) | 6,847,990 | 423 |

---
## 🗂️ Project Structure

```
Travel-and-Tourism-Dataset-Cleaning/
├── bookings_raw.csv                         # raw bookings data
├── customers_raw.csv                        # raw customers data
├── properties_raw.csv                       # raw properties data
├── Travel_and_Tourism_Data_Cleaning.ipynb   # full cleaning notebook
├── README.md

```

---

## 👤 Author

**Darrel Christofer**
*(www.linkedin.com/in/darrel-christofer / christoferdarrel@gmail.com)*
