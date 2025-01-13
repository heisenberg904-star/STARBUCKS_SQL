# STARBUCKS_SQL
"SQL query solutions for analyzing Starbucks beverage data, covering calorie, sugar, caffeine, and nutritional insights with diverse complexity."
SQL Query Solutions for Starbucks Dataset

This repository contains solutions to various SQL queries designed to analyze a Starbucks dataset. Each query focuses on extracting valuable insights about beverages, their nutritional values, and preparation methods. Below is the detailed description of the queries:

Query Descriptions

List all the beverages with calories count greater than 100: Retrieves beverage details with calorie counts above 100, sorted by calorie count in descending order.

SELECT BEVERAGE, BEVERAGE_CATEGORY, BEVERAGE_PREP, CALORIES
FROM starbucks
WHERE CALORIES > 100
ORDER BY CALORIES DESC;

Display all distinct beverage categories: Identifies unique beverage categories available in the dataset.

SELECT DISTINCT BEVERAGE_CATEGORY FROM STARBUCKS;

Find all beverages prepared as "Grande": Lists beverages specifically prepared using the "Grande" method.

SELECT BEVERAGE FROM STARBUCKS
WHERE BEVERAGE_PREP = "GRANDE";

Count the number of beverages for each preparation method: Groups beverages by preparation method and counts the number of beverages in each group.

SELECT BEVERAGE_PREP, COUNT(*) AS BEVERAGE_COUNT
FROM STARBUCKS
GROUP BY BEVERAGE_PREP
ORDER BY BEVERAGE_COUNT DESC;

Calculate the average calorie count for each beverage category: Provides the average calorie count for each distinct beverage category.

SELECT BEVERAGE_CATEGORY, AVG(CALORIES)
FROM STARBUCKS
GROUP BY BEVERAGE_CATEGORY;

Retrieve all beverages with calorie counts above the average calorie count: Filters beverages with calorie counts exceeding the average calorie count of all beverages.

SELECT BEVERAGE, CALORIES FROM STARBUCKS
WHERE CALORIES > (SELECT AVG(CALORIES) FROM STARBUCKS);

Retrieve the beverage category that contains the beverage with the highest calorie count: Identifies the beverage category of the item with the highest calorie count.

SELECT BEVERAGE FROM STARBUCKS
WHERE CALORIES = (SELECT MAX(CALORIES) FROM STARBUCKS);


Dataset: A Starbucks dataset file (CSV format) is used for the queries.


Import the provided Starbucks dataset into your SQL database.

Run the queries using your preferred SQL environment.

Review the results and adjust queries as needed for further exploration.

Contribution

Feel free to contribute by adding more queries or improving the current solutions. Submit a pull request or open an issue to get started!




