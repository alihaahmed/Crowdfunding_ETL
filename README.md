# Crowdfunding ETL Project

## Background

The steps taken in this project are divided into the following subsections:

1. Create the Category and Subcategory DataFrames
2. Create the Campaign DataFrame
3. Create the Contacts DataFrame
4. Create the Crowdfunding Database

## Create the Category and Subcategory DataFrames

1. Extracted and transformed the crowdfunding.xlsx file to create a category DataFrame with the following columns:

- A "category_id" column that has entries going sequentially from "cat1" to "catn", where n is the number of unique categories
- A "category" column that contains only the category titles

2. Exported the category DataFrame as category.csv and saved to repository under "Resources" folder

3. Extracted and transformed the crowdfunding.xlsx file to create a subcategory DataFrame with the following columns:

- A "subcategory_id" column that has entries going sequentially from "subcat1" to "subcatn", where n is the number of unique subcategories
- A "subcategory" column that contains only the subcategory titles

4. Exported the subcategory DataFrame as subcategory.csv and saved to repository under "Resources" folder

## Create the Campaign DataFrame

1. Extracted and transformed the crowdfunding.xlsx file to create a campaign DataFrame with the following columns:

- "cf_id" column
- "contact_id" column
- "company_name" column
- "blurb" column, renamed to "description"
- "goal" column, converted to the float data type
- "pledged" column, converted to the float data type
- "outcome" column
- "backers_count" column
- "country" column
- "currency" column
- "launched_at" column, renamed to "launch_date" and with the UTC times converted to the datetime format
- "deadline" column, renamed to "end_date" and with the UTC times converted to the datetime format
- "category_id" column, with unique identification numbers matching those in the "category_id" column of the category DataFrame
- "subcategory_id" column, with the unique identification numbers matching those in the "subcategory_id" column of the subcategory DataFrame

2. Exported the campaign DataFrame as campaign.csv and saved to repository under "Resources" folder

## Create the Contacts DataFrame

1. Used Python dictionary methods to extract and transform the data from the contacts.xlsx file:

- Imported the contacts.xlsx file into a DataFrame
- Iterated through the DataFrame, converting each row to a dictionary
- Iterated through each dictionary and extracted the dictionary values from the keys by using a Python list comprehension, adding the values for each row to a new list
- Created a new DataFrame containing the extracted data
- Split each "name" column value into a first and last name, placing each in a new column
- Cleaned and exported the DataFrame as contacts.csv and saved it to repository under "Resources" folder

## Create the Crowdfunding Database

1. Sketched an ERD of the four files/tables (category.csv, subcategory.csv, campaign.csv, contacts.csv) using [QuickDBD](https://www.quickdatabasediagrams.com/)

2. Used ERD to create a table schema for each CSV file, specifying the appropriate data types, primary keys, foreign keys, and other constraints

3. Saved the database schema as a Postgres file named crowdfunding_db_schema.sql and saved to repository under "Crowdfunding_Database_Schema" folder

4. Created a new Postgres database (crowdfunding_db) 

5. Using the database schema, created the tables in the appropriate order to handle foreign keys

6. Verified table creation by running SELECT statements for each table

7. Imported each CSV file into its corresponding SQL table

8. Verified successful imports by running SELECT statements for each table
